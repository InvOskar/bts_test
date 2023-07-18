<template>
  <item-block>
    <div class="info">
      <p class="info-title">В наличии</p>
      <p class="info-name">Футболка белая ERG</p>
      <div class="info-items">
        <div class="info-items-left">
          <p class="info-items-price">15 000 E</p>
          <div class="info-items-stars">
            <img v-for="i in 5" :key="i" src="@/assets/img/star.svg" />
          </div>
        </div>
        <div class="info-items-like" @click="isLike = !isLike">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="20"
            height="18"
            viewBox="0 0 20 18"
            :fill="isLike ? '#EF7F1A' : 'none'"
          >
            <path
              d="M2.3314 9.04738L10 17L17.6686 9.04738C18.5211 8.16332 19 6.96429 19 5.71405C19 3.11055 16.9648 1 14.4543 1C13.2487 1 12.0925 1.49666 11.24 2.38071L10 3.66667L8.75997 2.38071C7.90749 1.49666 6.75128 1 5.54569 1C3.03517 1 1 3.11055 1 5.71405C1 6.96429 1.47892 8.16332 2.3314 9.04738Z"
              :stroke="isLike ? '#EF7F1A' : '#8E8E93'"
              stroke-width="1.5"
              stroke-linecap="round"
              stroke-linejoin="round"
            />
          </svg>
        </div>
      </div>
    </div>
  </item-block>
</template>

<script>
import ItemBlock from "../UI/ItemBlock.vue";
export default {
  components: { ItemBlock },
  data() {
    return {
      isLike: false,
    };
  },
};
</script>

<style lang="scss" scoped>
.info {
  display: flex;
  flex-direction: column;

  &-title {
    color: #8e8e93;
    font-size: 14px;
    font-weight: 400;
    line-height: 20px;
    letter-spacing: 0.28px;
  }
  &-name {
    color: #101828;
    font-size: 16px;
    font-weight: 400;
    line-height: 24px;
    letter-spacing: 0.32px;
  }

  &-items {
    margin-top: 6px;
    display: flex;
    justify-content: space-between;
    align-items: center;

    &-left {
      display: flex;
      gap: 4px;
      flex-direction: column;
    }

    &-price {
      color: #151c22;
      font-size: 28px;
      font-weight: 400;
      line-height: 32px;
      letter-spacing: 0.56px;
    }
    &-stars {
      display: flex;
      gap: 6px;
    }
    &-like {
      cursor: pointer;
    }
  }
}
</style>
