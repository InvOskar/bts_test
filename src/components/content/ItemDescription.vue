<template>
  <item-block :title="'Описание'">
    <v-clamp
      autoresize
      :max-lines="5"
      :expanded="!isHide"
      class="text"
      :class="{ 'text-hide': isHide }"
    >
      ERG Футболка. 100%-й хлопок надолго сохраняет форму и цвет благодаря
      тщательно продуманной толщине полотна и плотности плетения нитей. В основе
      коллекции – внимание к деталям и стремление создать простой современный
      дизайн. В основе коллекции – внимание к деталям и стремление создать
      простой современный дизайн.
    </v-clamp>
    <div class="hider" @click="isHide = !isHide">
      <p class="hider-text">{{ isHide ? "Подробнее" : "Скрыть" }}</p>
      <div class="hider-arrow" :class="{ 'hider-arrow-rotated': !isHide }">
        <img src="@/assets/img/arrow.svg" />
      </div>
    </div>
  </item-block>
</template>

<script>
import ItemBlock from "../UI/ItemBlock.vue";
import VClamp from "vue-clamp";

export default {
  components: { ItemBlock, VClamp },
  data() {
    return {
      isHide: true,
    };
  },
};
</script>

<style lang="scss" scoped>
.text {
  font-size: 16px;
  font-style: normal;
  font-weight: 400;
  line-height: 24px;
  letter-spacing: 0.32px;
  color: #101828;
}
.hider {
  display: flex;
  padding-top: 2px;
  cursor: pointer;

  &-text {
    color: #8e8e93;
    font-size: 14px;
    font-weight: 400;
    line-height: 20px;
    letter-spacing: 0.28px;

    &-hide {
      display: -webkit-box;
      -webkit-line-clamp: 5;
      -webkit-box-orient: vertical;
      overflow: hidden;
    }
  }
  &-arrow {
    width: 20px;
    height: 20px;
    display: flex;
    justify-content: center;
    align-items: center;
    transition: 0.3s linear;

    &-rotated {
      transform: rotate(180deg);
    }
  }
}
</style>
