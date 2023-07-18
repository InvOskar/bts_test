<template>
  <div class="content">
    <content-header />
    <div class="content-items">
      <item-images />
      <item-info />
      <item-sizes :choice="size" :sizes="sizes" @changeSize="changeSize" />
      <item-description />
    </div>
    <content-buttons @openConfirmation="isConfirm = true" />
    <div class="confirm" v-if="isConfirm">
      <confirmation-block :size="sizeLetter" @closeConfirmation="isConfirm = false" />
    </div>
  </div>
</template>

<script>
import ContentHeader from "./content/ContentHeader.vue";
import ItemImages from "./content/ItemImages.vue";
import ItemInfo from "./content/ItemInfo.vue";
import ItemSizes from "./content/ItemSizes.vue";
import ItemDescription from "./content/ItemDescription.vue";
import ContentButtons from "./content/ContentButtons.vue";
import ConfirmationBlock from "./content/ConfirmationBlock.vue";

export default {
  components: {
    ContentHeader,
    ItemImages,
    ItemInfo,
    ItemSizes,
    ItemDescription,
    ContentButtons,
    ConfirmationBlock,
  },
  data() {
    return {
      isConfirm: false,
      size: 0,
      sizes: [
        {
          id: 0,
          number: "48-50",
          letter: "M",
        },
        {
          id: 1,
          number: "50-52",
          letter: "L",
        },
        {
          id: 2,
          number: "52-54",
          letter: "XL",
        },
        {
          id: 3,
          number: "54-56",
          letter: "2XL",
        },
      ],
    };
  },
  methods: {
    changeSize(id) {
        this.size = id;
    }
  },
  computed: {
    sizeLetter() {
        return this.sizes.find(item => item.id === this.size).letter
    }
  }
};
</script>

<style lang="scss" scoped>
.content {
  display: flex;
  flex-direction: column;
  padding-bottom: 16px;

  &-items {
    display: flex;
    flex-direction: column;
    gap: 16px;

    height: calc(100vh - 184px);
    overflow-y: auto;
  }
}
.confirm {
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  background: rgba(#000000, 0.24);
  border-radius: 16px;
}
</style>
