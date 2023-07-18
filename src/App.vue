<template>
  <div
    class="app"
    :style="{ transform: 'scale(' + ratio + ') translate(-50%, -50%)' }"
  >
    <div class="main">
      <mobile-header />
      <content-block />
    </div>
  </div>
</template>

<script>
import MobileHeader from "./components/MobileHeader.vue";
import ContentBlock from "./components/ContentBlock.vue";
export default {
  components: { MobileHeader, ContentBlock },
  data() {
    return {
      ratio: 1,
    };
  },
  methods: {
    resize: function () {
      let sw = 375;
      let sh = window.innerHeight;
      let factor = sw / sh;
      let bw = window.innerWidth;
      let bh = window.innerHeight;

      if (bw / bh < factor) {
        this.ratio = bw / sw;
      } else {
        this.ratio = bh / sh;
      }
    },
    unmounted() {
      window.removeEventListener("resize", this.resize);
    },
  },
  created() {
    window.addEventListener("resize", this.resize);
    this.resize();
  },
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "TT Commons";
}
@font-face {
  font-family: "TT Commons";
  src: local("TT Commons"),
   url(./assets/font/TT\ Commons\ Regular.otf);
}
.app {
  position: absolute;
  left: 50%;
  top: 50%;
  width: 375px;
  height: 100vh;
  transform-origin: 0 0;
  overflow: hidden;
}
.main {
  width: 100%;
  height: 100%;
  background: #f9f9f9;
  border-radius: 16px;
  overflow: hidden;
}
::-webkit-scrollbar {
  width: 0;
}
.main-button {
  height: 56px;
  width: 100%;
  padding: 16px;
  border-radius: 16px;
  border: 0;

  display: flex;
  justify-content: center;
  align-items: center;

  color: white;
  font-size: 20px;
  font-weight: 500;
  line-height: 24px;
  letter-spacing: 0.4px;

  cursor: pointer;
}
</style>
