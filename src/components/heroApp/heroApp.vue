<template>
  <div class="hero">
    <h1>Hello world</h1>
  </div>
</template>

<script>
export default {
  name: "HeroApp",
};
</script>

<style lang="scss">
$green: #05ab60;
$greenDark: #1f5b1d;

.hero {
  width: 100%;
  height: 100vh;
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;

  background-color: $green;
  background: linear-gradient(-45deg, rgba(5,171,96,1) 0%, rgba(31,91,29,1) 20%, rgba(10,94,83,1) 40%, rgba(14,158,139,1) 60%, rgba(14,136,158,1) 80%, rgba(4,119,198,1) 100%);
  background-size: 600% 600%;

  animation: gradientBg 20s infinite ease-in-out;
}

@keyframes gradientBg {
  
    0% {
        background-position: 0% 50%;
    }
    50% {
        background-position: 100% 100%;
    }
    100% {
        background-position: 0% 50%;
    }
}
</style>