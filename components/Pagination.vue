<template>
  <div class="container">
    <div class="item">
      <PaginationButton
        :url="nextUrl"
        :is-active="false"
        type="previous"
      />
    </div>
    <div class="item">
      <PaginationButton
        :url="previousUrl"
      />
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import PaginationButton from '@/components/PaginationButton.vue';

@Component({
  components: {
    PaginationButton
  }
})
export default class Pagination extends Vue {
  @Prop() private nextUrl!: string;
  @Prop() private previousUrl!: string;
}
</script>

<style scoped>
.container {
  display: flex;
  justify-content: center;
  padding: 28px 0 0;
}

.item {
  margin: 0 40px;
}
</style>
