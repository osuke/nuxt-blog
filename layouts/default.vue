<template>
  <div class="layout">
    <Header />
    <nuxt />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Header from '@/components/Header.vue';

@Component({
  components: {
    Header
  }
})
export default class Layout extends Vue {
}
</script>
<style>
html {
  font-family: 'ヒラギノ角ゴ Pro W3', 'Hiragino Kaku Gothic Pro', 'メイリオ', Meiryo, sans-serif;
}

.layout {
  padding: 0 16px 40px;
  margin: 0 auto;
  max-width: 680px;
}

</style>
