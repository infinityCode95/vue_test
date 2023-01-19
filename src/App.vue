<template>
  <div class="app__wrap">
    <Header />
    <FoodsList/>
  </div>
</template>

<script>
import Header from "@/components/Header";
import FoodsList from "@/components/FoodsList";

export default {
  name: "App",
  components: {
    Header,
    FoodsList
  },
  data: () => ({}),
};
</script>

<style lang="scss">
#app {
  font-family: "Trebuchet MS";
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background: linear-gradient(180deg, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 5e-05) 49.88%, rgba(0, 0, 0, 0.5) 100%);
  position: absolute;
  width: 100%;
  height: 100%;
  color: #fff;
}

.app__wrap {
  margin: 36px 80px 67px 80px;
}
</style>
