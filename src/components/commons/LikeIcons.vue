<template>
  <div
    class="likeContainer"
    :class="
      likeName === 'fire'
        ? 'fire'
        : '' || likeName === 'like'
        ? 'like'
        : '' || likeName === 'star'
        ? 'star'
        : ''
    "
  >
    <img
      src="../../assets/images/fire.png"
      v-if="likeName === 'fire'"
      alt=""
      class="likeF"
    />
    <img
      src="../../assets/images/like.png"
      v-if="likeName === 'like'"
      alt=""
      class="likeL"
    />
    <img
      src="../../assets/images/star.png"
      v-if="likeName === 'star'"
      alt=""
      class="starL"
    />
  </div>
</template>
<script>
export default {
  name: "app-like",
  props: {
    likeName: {
      type: String,
      default: "fire",
    },
  },
};
</script>
<style lang="scss">
.likeContainer {
  width: 24px;
  height: 24px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;

  &.fire {
    background: #ffd1d1;
  }
  &.like {
    background: rgba(255, 193, 7, 0.16);
  }
  &.star {
    background: rgba(255, 193, 7, 0.16);
  }
}
</style>
