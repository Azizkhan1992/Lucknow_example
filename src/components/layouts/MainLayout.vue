<template>
  <div class="mainLayout">
    <Header />

    <router-view />
  </div>
</template>
<script>
import Header from "../Header.vue";
export default {
  name: "main-layout",
  components: { Header },
};
</script>
