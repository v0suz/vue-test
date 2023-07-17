<template>
  <div>
    <TheMain></TheMain>
  </div>
</template>

<script>
import TheMain from "./components/TheMain.vue";
export default {
  components: {
    TheMain
  },
  setup() {
    return {};
  },
};
</script>

<style lang="scss">

@font-face {
  font-family: "PPMori";
  src: local("PPMori-Regular"), local("PPMori-Regular"),
    url("./components/fonts/PPMori/PPMori-Regular.otf") format("otf");
  font-weight: 500;
  font-style: normal;
}

@font-face {
  font-family: "PPMori";
  src: local("PPMori-Extralight"), local("PPMori-Extralight"),
    url("./components/fonts/PPMori/PPMori-Extralight.otf") format("otf");
  font-weight: 300;
  font-style: normal;
}
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
body,
html {
  width: 100%;
  height: 100vh;
  font-family: "PPMori";
  font-weight: 500;
}
</style>
