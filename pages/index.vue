<template>
  <div>
    <h1 class="listTitle">Posts</h1>
    <div class="posts">
      <Post
        v-for="post in res"
        :key="post.id"
        :url="`/${post.id}`"
        :title="post.title.rendered"
        :date="formatDate(post.date)"
      />
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator';
import axios from 'axios';
import { formatDate } from '@/utils';
import Post from '@/components/Post.vue';

@Component({
  components: {
    Post
  }
})
export default class Home extends Vue {
  async asyncData () {
    const res = await axios.get('https://blog-funxion.herokuapp.com/wp-json/wp/v2/posts?per_page=100');
    return { res: res.data };
  }

  private formatDate (date: string) {
    return formatDate(date);
  }
}
</script>

<style>
.listTitle {
  font-size: 24px;
  color: #555;
  margin-bottom: 24px;
  letter-spacing: 0.1em;
}
</style>
