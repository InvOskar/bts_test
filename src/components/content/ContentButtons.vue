<template>
  <div class="buttuns">
    <div
      class="main-button"
      style="background: #90bc34"
      @click="$emit('openConfirmation')"
    >
      Купить сейчас
    </div>
    <div
      class="main-button"
      style="background: #ef7f1a"
      @click="$emit('openConfirmation')"
    >
      В корзину
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.buttuns {
  display: flex;
  gap: 8px;
  background: white;
  padding: 16px;
  position: absolute;
  width: 100%;
  bottom: 0;
  border-bottom-left-radius: 16px;
  border-bottom-right-radius: 16px;

  border-top: 1px solid #dde1e5;
}
</style>
