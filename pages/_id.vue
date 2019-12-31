<template>
  <div>
    <h1 class="articleTitle">{{res.title.rendered}}</h1>
    <div class="articleDate">{{formatDate(res.date)}}</div>
    <div class="articleContent" v-html="res.content.rendered"></div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator';
import axios from 'axios';
import { formatDate } from '@/utils';

@Component
export default class index extends Vue {
  async asyncData (context: any) {
    const { params } = context;
    const res = await axios.get(`https://blog-funxion.herokuapp.com/wp-json/wp/v2/posts/${params.id}`);
    return { res: res.data };
  }

  private formatDate (date: string) {
    return formatDate(date);
  }
}
</script>

<style>
.articleTitle {
  font-size: 20px;
  font-weight: bold;
  color: #555;
  line-height: 1.5;
  letter-spacing: 0.1em;
  margin-bottom: 16px;
}

.articleDate {
  font-size: 14px;
  color: #808080;
  margin-bottom: 32px;
}

.articleContent {
  font-size: 16px;
  color: #555;
  line-height: 1.7;
}

.articleContent img {
  max-width: 100%;
  height: auto;
}

.articleContent h2 {
  font-size: 18px;
  color: #555;
  font-weight: bold;
  margin: 0 0 16px;
  padding: 28px 0 0;
}

.articleContent h3 {
  font-size: 16px;
  color: #555;
  font-weight: bold;
  margin: 0 0 12px;
  padding: 20px 0 0;
}

.articleContent a {
  color: #555;
}

.articleContent p {
  margin-bottom: 32px;
}

.articleContent pre {
  background: #333;
  padding: 20px;
  margin-bottom: 32px;
  overflow-x: scroll;
}

.articleContent code {
  width: 100%;
  color: #fff;
}
</style>
