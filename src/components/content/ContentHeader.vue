<template>
  <div class="content-header">
    <div class="content-header-title">
      <div class="content-header-title-back">
        <img src="@/assets/img/Back.svg" />
      </div>
      <p>Футболка белая ERG</p>
    </div>
    <div class="content-header-balance">10 000 E</div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.content-header {
  height: 52px;
  border-bottom-left-radius: 18px;
  border-bottom-right-radius: 18px;
  background: white;
  padding: 10px 16px;

  display: flex;
  justify-content: space-between;
  align-items: center;

  &-title {
    display: flex;
    align-items: center;
    gap: 8px;

    &-back {
      width: 24px;
      height: 24px;
      cursor: pointer;
    }

    & > p {
      width: 180px;
      white-space: nowrap;
      overflow: hidden;
      text-overflow: ellipsis;

      color: #151c22;
      font-size: 20px;
      font-weight: 600;
      line-height: 24px;
      letter-spacing: 0.4px;
    }
  }

  &-balance {
    border-radius: 10px;
    height: 32px;
    padding: 6px 12px;
    background: #a1d8ff;
    color: #3d7caf;
    font-size: 14px;
    font-weight: 500;
    line-height: 20px;
    letter-spacing: 0.28px;
  }
}
</style>
