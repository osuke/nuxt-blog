<template>
  <div :class="className">
    <nuxt-link :to="url">
      <svg width="46" height="46" viewBox="0 0 46 46" fill="none" xmlns="http://www.w3.org/2000/svg">
        <circle cx="23" cy="23" r="22.5" fill="white" stroke="#555555" />
        <rect
          x="28.8995"
          y="22.4854"
          width="12"
          height="2"
          rx="1"
          transform="rotate(135 28.8995 22.4854)"
          fill="#555555"
        />
        <rect
          x="20.4142"
          y="14"
          width="12"
          height="2"
          rx="1"
          transform="rotate(45 20.4142 14)"
          fill="#555555"
        />
      </svg>
    </nuxt-link>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class PaginationButton extends Vue {
  @Prop() private url!: string;
  @Prop({ default: 'next' }) private type!: 'next' | 'previous';
  @Prop({ default: true }) private isActive!: boolean;

  get className (): string {
    const classes = ['button'];

    if (!this.isActive) {
      classes.push('deActive');
    }

    if (this.type === 'previous') {
      classes.push('previous');
    }

    return classes.join(' ');
  }
}
</script>

<style scoped>
.button {
  width: 46px;
  height: 46px;
  background: #fff;
}

.previous {
  transform: rotate(180deg);
}

.deActive circle {
  stroke: #c7cfcf;
}

.deActive rect {
  fill: #c7cfcf;
}

.button a {
  display: block;
  height: 100%;
}
</style>
