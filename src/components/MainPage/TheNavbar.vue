<template>
  <div class="navbar">
    <img
      src="https://d33wubrfki0l68.cloudfront.net/439bf938233c24af021ffe6d206cd42f546e1143/ff4ed/assets/logo.svg"
      alt=""
    />
    <div class="nav__links">
      <ThePageLinkVue style="border-bottom: 1.3px solid #fff"
        >Home</ThePageLinkVue
      >
      <ThePageLinkVue>Work</ThePageLinkVue>
      <ThePageLinkVue>Studio</ThePageLinkVue>
      <ThePageLinkVue>Contact</ThePageLinkVue>
    </div>
    <div class="nav__circle">
      <div class="circle"></div>
    </div>
  </div>
</template>

<script>
import ThePageLinkVue from "../UI/ThePageLink.vue";
export default {
  components: {
    ThePageLinkVue,
  },
  setup() {
    return {};
  },
  mounted() {},
  methods: {},
};
</script>

<style lang="scss" scoped>
.navbar {
  width: 100%;
  height: 55px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 30px;
  position: fixed;
  mix-blend-mode: difference;
  z-index: 102;

  img {
    height: 23px;
  }

  .nav__links {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 20px;
  }
  .nav__circle {
    height: 20px;
    width: 20px;
    border-radius: 50%;
    background-color: #fff;
  }
}
</style>
