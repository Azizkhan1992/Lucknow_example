<template>
  <div class="sliceContainer">
    <SliceItems />

    <div class="homeSliceLogo">
      <SliceLogo />
    </div>
  </div>
</template>
<script>
import SliceItems from "./sliceItems.vue";
import SliceLogo from "./SliceLogo.vue";
export default {
  name: "home-slice",
  components: { SliceItems, SliceLogo },
};
</script>
<style lang="scss">
.sliceContainer {
  width: 100%;
  height: 160px;
  margin-top: 28px;
  display: flex;
  justify-content: space-between;
}

@media screen and (max-width: 1198px) and (min-width: 768px) {
  .sliceContainer {
    .sliceItemsContainer {
      width: 100% !important;
    }

    .homeSliceLogo {
      display: none;
    }
  }
}

@media screen and (min-width: 1441px) {
  .sliceContainer {
    .sliceItemsContainer {
      justify-content: space-between;

      .sliceItems {
        h5.descPSM {
          font-size: 1.5rem;
        }
      }
    }
  }
}
</style>
