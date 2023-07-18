<template>
  <div class="item-images">
    <img :src="require(`@/assets/img/${getImage}`)" />
    <div class="roller">
      <div
        class="roller-item"
        v-for="item in images"
        :key="item.id"
        :class="{ 'roller-item-active': item.id === image }"
        @click="image = item.id"
      ></div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      image: 0,
      images: [
        {
          id: 0,
          img: "Tshirt.png",
        },
        {
          id: 1,
          img: "Tshirt.png",
        },
        {
          id: 2,
          img: "Tshirt.png",
        },
      ],
    };
  },
  computed: {
    getImage() {
      return this.images.find((img) => img.id === this.image).img;
    },
  },
};
</script>

<style lang="scss" scoped>
.item-images {
  background: white;
  padding: 16px 0;

  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 12px;

  border-bottom-left-radius: 12px;
  border-bottom-right-radius: 12px;
}
.roller {
  display: flex;
  gap: 8px;

  &-item {
    border: 1px solid #d9d9d9;
    width: 8px;
    height: 8px;
    border-radius: 50%;
    cursor: pointer;

    &-active {
      background: #d9d9d9;
    }
  }
}
</style>
