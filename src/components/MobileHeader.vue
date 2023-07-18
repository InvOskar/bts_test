<template>
  <div class="mobile-header">
    <img src="@/assets/img/mobileHeader.svg" />
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.mobile-header {
  height: 44px;
  display: flex;
  justify-content: center;
  align-items: center;
  background: white;
  border-top-left-radius: 16px;
  border-top-right-radius: 16px;

  & > img {
    pointer-events: none;
  }
}
</style>
