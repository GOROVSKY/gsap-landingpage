<template>
  <div class="hero">
    <h1 class="hero__title">
      <span class="letter letter--first">H</span>ell<span class="letter letter-o">o</span> <span class="letter letter-w">w</span>orl<span
        class="letter letter--last"
        >d</span
      >
    </h1>
    <div class="hero__author">Developed by Guillaume Laville</div>
  </div>
</template>

<script>
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);

export default {
  name: "HeroApp",

  mounted() {
    gsap.registerPlugin(ScrollTrigger);

    let timeline = gsap.timeline({
      scrollTrigger: {
        trigger: ".hero",
        pin: true, 
        start: "top top", 
        end: "bottom bottom",
        scrub: 1
      },
    });

    timeline
      .addLabel("start")
      .to(".hero__title", { letterSpacing: "100px" }, "start")
      .to(".hero__title", { color: "red" }, "start")
      .to(".letter-w", { scale: 2 }, "start")
      .to(".letter--last", { marginLeft: "-100px" }, "start")
      .to(".letter-o", { opacity: 0, delay: -0.3 }, "start")
      .to(".letter--first", { rotate: "90deg" }, "start")
      .to(".letter--last", { rotate: "-180deg"}, "start");
  },
};
</script>

<style lang="scss">
$green: #05ab60;

.hero {
  width: 100%;
  height: 200vh;
  color: white;
  position: relative;
  overflow: hidden;

  background-color: $green;
  background: linear-gradient(
    -45deg,
    rgba(5, 171, 96, 1) 0%,
    rgba(31, 91, 29, 1) 20%,
    rgba(10, 94, 83, 1) 40%,
    rgba(14, 158, 139, 1) 60%,
    rgba(14, 136, 158, 1) 80%,
    rgba(4, 119, 198, 1) 100%
  );
  background-size: 600% 600%;
  animation: gradientBg 20s infinite ease-in-out;

  &__title {
    font-size: 5rem;
    position: sticky;
    white-space: nowrap;
    top: 50vh;

    .letter {
      display: inline-block;
    }
  }

  &__author {
    position: absolute;
    bottom: 20vh;
    left: 50%;
    transform: translateX(-50%);
  }
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