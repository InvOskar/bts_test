<template>
  <div class="item">
    <p v-if="title.length > 0" class="item-title">{{ title }}</p>
    <div class="item-block">
        <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: "",
    },
  },
};
</script>

<style lang="scss" scoped>
.item {
    display: flex;
    flex-direction: column;
    gap: 4px;

    &-title {
        color: #8E8E93;
        font-weight: 400;
        line-height: 20px;
        padding-left: 16px;
        letter-spacing: 0.32px;
    }

    &-block {
        padding: 14px 16px;
        background: white;
        border-radius: 12px;
    }
}
</style>
