<template>
  <div>
    <HeroApp />
  </div>
</template>

<script>
import HeroApp from "@/components/heroApp/heroApp.vue";

export default {
  components: {
    HeroApp,
  },
};
</script>

<style lang="scss">
@font-face {
  font-family: OpenDyslexic;
  src: url("./assets/fonts/OpenDyslexic-Regular.otf");
}

* {
  margin: 0;
  padding: 0;
}

*,
*:before,
*:after {
  box-sizing: border-box;
}

html,
body {
  height: 100%;
  margin: 0;
  position: relative;
  text-align: center;
  font-family: OpenDyslexic;
}
</style>
