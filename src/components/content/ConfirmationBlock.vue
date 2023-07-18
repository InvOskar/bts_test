<template>
  <div class="confirmation">
    <div class="line"></div>
    <div class="close">
      <img @click="$emit('closeConfirmation')" src="@/assets/img/close.svg" />
    </div>
    <div class="confirmation-info">
      <div class="confirmation-info-img">
        <img src="@/assets/img/Tshirt.png" />
      </div>
      <div class="confirmation-info-details">
        <p class="confirmation-info-details-title">В наличии</p>
        <p class="confirmation-info-details-name">Футболка белая ERG</p>
        <div class="confirmation-info-details-amount">
          <div
            @click="counter > 1 ? counter-- : (counter = 1)"
            class="count-btn"
          >
            <p>-</p>
          </div>
          <p>{{ counter }} шт.</p>
          <div @click="counter++" class="count-btn">
            <p>+</p>
          </div>
          <p>({{size}})</p>
        </div>
      </div>
      <p class="confirmation-info-price">15 000 E</p>
    </div>
    <div
      class="main-button"
      style="background: #ef7f1a"
      @click="$emit('closeConfirmation')"
    >
      Добавить в корзину
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      counter: 1,
    };
  },
  props: {
    size: {
      type: String,
      required: true,
    }
  }
};
</script>

<style lang="scss" scoped>
.confirmation {
  position: absolute;
  bottom: 0;
  width: 100%;
  padding: 6px 16px 32px 16px;
  border-radius: 16px;
  background: white;

  &-info {
    display: flex;
    gap: 8px;
    padding-bottom: 16px;

    &-img {
      width: 80px;
      height: 80px;
      display: flex;
      align-items: center;
      justify-content: center;

      & > img {
        width: 100%;
      }
    }

    &-details {
      display: flex;
      flex-direction: column;
      margin-top: 4px;

      &-title {
        color: #8e8e93;
        font-size: 14px;
        font-weight: 400;
        line-height: 20px;
        letter-spacing: 0.28px;
      }
      &-name {
        color: #101828;
        font-weight: 400;
        line-height: 120%;
        letter-spacing: 0.32px;
      }
      &-amount {
        display: flex;
        gap: 8px;
        align-items: center;
        color: #101828;
        font-size: 14px;
        font-weight: 500;
        letter-spacing: 0.28px;
        text-align: center;
      }
    }
    &-price {
      display: flex;
      align-items: center;
      margin-left: auto;

      color: #151c22;
      font-size: 18px;
      font-weight: 500;
      line-height: 26px;
      letter-spacing: 0.36px;
    }
  }
}
.line {
  background: #f5f5f5;
  height: 4px;
  width: 32px;
  border-radius: 3px;
  margin: auto;
}
.close {
  height: 24px;
  display: flex;
  align-items: center;
  justify-content: end;

  & > img {
    cursor: pointer;
  }
}
.count-btn {
  padding: 4px 12px;
  display: flex;
  align-items: center;
  border-radius: 8px;
  border: 1px solid #dde1e5;
  cursor: pointer;

  & > p {
    color: #101828;
    font-size: 24px;
    font-weight: 400;
    letter-spacing: 0.48px;
    text-align: center;
  }
}
</style>
