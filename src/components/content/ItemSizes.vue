<template>
  <item-block :title="'Размеры'">
    <div class="list">
      <div
        class="list-item"
        v-for="size in sizes"
        :key="size.id"
        :class="{ 'list-item-active': size.id === choice }"
        @click="$emit('changeSize', size.id)"
      >
        <p class="list-item-number">{{ size.number }}</p>
        <p class="list-item-letter">{{ size.letter }}</p>
      </div>
    </div>
  </item-block>
</template>

<script>
import ItemBlock from "../UI/ItemBlock.vue";
export default {
  components: { ItemBlock },
  props: {
    choice: {
        type: Number,
        required: true,
    },
    sizes: {
        type: Array,
        required: true,
    }
  }
};
</script>

<style lang="scss" scoped>
.list {
  display: flex;
  gap: 8px;

  &-item {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;

    padding: 8px 16px;
    border: 1.5px solid #dde1e5;
    border-radius: 8px;

    font-weight: 400;
    letter-spacing: 0.32px;

    cursor: pointer;

    &-active {
      border: 1.5px solid #3376f6;
    }

    &-number {
      color: #101828;
    }
    &-letter {
      color: #8e8e93;
    }
  }
}
</style>
