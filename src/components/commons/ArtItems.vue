<template>
  <div class="artItemContent" :class="this.name + 'Item'">
    <img
      src="../../assets/images/cook.png"
      v-if="name === 'cook'"
      alt=""
      class="cookImg"
    />
    <img
      src="../../assets/images/corona.png"
      v-if="name === 'corona'"
      alt=""
      class="coronaImg"
    />
    <img
      src="../../assets/images/chocolate.png"
      v-if="name === 'donut'"
      alt=""
      class="chocoImg"
    />
    <img
      src="../../assets/images/cheez.png"
      v-if="name === 'popcorn'"
      alt=""
      class="cheezImg"
    />
  </div>
</template>
<script>
export default {
  name: "app-art",
  props: {
    name: {
      type: String,
      default: "cook",
    },
  },
};
</script>
<style lang="scss">
.artItemContent {
  width: 60px;
  height: 60px;
  border-radius: 15px;
  display: flex;
  align-items: center;
  justify-content: center;

  &.cookItem {
    background: #fff0a5;
  }
  &.coronaItem {
    background: #d6f5ff;
  }
  &.donutItem {
    background: #ffddf0;
  }
  &.popcornItem {
    background: #c1fff4;
  }
}
</style>
