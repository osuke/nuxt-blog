<template>
  <div class="post">
    <h2 class="postTitle"><nuxt-link :to="url">{{title}}</nuxt-link></h2>
    <div class="postDate">{{date}}</div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class Post extends Vue {
  @Prop() private title!: string;
  @Prop() private url!: string;
  @Prop() private date!: string;
}
</script>

<style>
.post {
  margin-bottom: 24px;
  line-height: 1.5;
  letter-spacing: 0.1em;
}

.postTitle {
  font-weight: bold;
  margin-bottom: 6px;
}

.postTitle a {
  font-size: 18px;
  color: #555;
  text-decoration: none;
}

.postDate {
  font-size: 14px;
  color: #808080;
}
</style>
