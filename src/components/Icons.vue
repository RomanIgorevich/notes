<template>
  <div class="icons">
    <svg
      :class="{ active: grid }"
      @click="gridActive"
      xmlns="http://www.w3.org/2000/svg"
      width="24"
      height="24"
      viewBox="0 0 24 24"
      fill="none"
      stroke="currentColor"
      stroke-width="2"
      stroke-linecap="round"
      stroke-linejoin="round"
    >
      <rect x="3" y="3" width="7" height="7"></rect>
      <rect x="14" y="3" width="7" height="7"></rect>
      <rect x="14" y="14" width="7" height="7"></rect>
      <rect x="3" y="14" width="7" height="7"></rect>
    </svg>
    <svg
      :class="{ active: !grid }"
      @click="gridNoActive"
      xmlns="http://www.w3.org/2000/svg"
      width="24"
      height="24"
      viewBox="0 0 24 24"
      fill="none"
      stroke="currentColor"
      stroke-width="2"
      stroke-linecap="round"
      stroke-linejoin="round"
    >
      <line x1="8" y1="6" x2="21" y2="6"></line>
      <line x1="8" y1="12" x2="21" y2="12"></line>
      <line x1="8" y1="18" x2="21" y2="18"></line>
      <line x1="3" y1="6" x2="3" y2="6"></line>
      <line x1="3" y1="12" x2="3" y2="12"></line>
      <line x1="3" y1="18" x2="3" y2="18"></line>
    </svg>
  </div>
</template>

<script>
export default {
  props: {
    grid: {
      type: Boolean,
      required: true,
    },
  },
  methods: {
    gridActive() {
      this.$emit("gridActive");
    },
    gridNoActive() {
      this.$emit("gridNoActive");
    },
  },
};
</script>

<style lang="scss">
.icons {
  display: flex;
  align-items: center;
  justify-content: flex-end;
}
svg {
  margin-right: 10px;
  color: #999;
  cursor: pointer;
  &.active {
    color: #494ce8;
  }
  &:last-child {
    margin-right: 0;
  }
}
</style>
