<template>
  <div class="main" ref="main">
    <div class="first__page">
      <TheNavbar style="position: fixed;"></TheNavbar>
      <h1 class="first__page-text">Digitally crafted</h1>
      <h2 class="first__page-text">brand experiences</h2>
      <div class="video__block">
        <div class="row">
          <p class="left__text"><span>creative digital agency</span></p>
          <p class="right__text"><span>based in washington,dc</span></p>
        </div>
        <TheVideo></TheVideo>
      </div>
    </div>
    <TheSecond></TheSecond>
    <TheThird></TheThird>
  </div>
</template>

<script>
import gsap from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);
import LocomotiveScroll from "locomotive-scroll";
import "locomotive-scroll/dist/locomotive-scroll.css";

import TheThird from "./ThirdPage/TheThird.vue";
import TheVideo from "./MainPage/TheVideo.vue";
import TheNavbar from "./MainPage/TheNavbar.vue";
import TheSecond from "./SecondPage/TheSecondPage.vue";
export default {
  components: {
    TheNavbar,
    TheVideo,
    TheSecond,
    TheThird,
  },
  setup() {
    return {};
  },
  mounted() {
    const _self = this;
    _self.initLocomotiveScroll();
    _self.initScrollTriger();
    _self.initGsapMain();
  },
  methods: {
    initLocomotiveScroll() {
      const _self = this;
      _self.scroll = new LocomotiveScroll({
        el: _self.$refs.main,
        smooth: true,
      });
      _self.scroll.on("scroll", ScrollTrigger.update);
    },
    initScrollTriger() {
      const _self = this;
      ScrollTrigger.scrollerProxy(".main", {
        scrollTop(value) {
          return arguments.length
            ? _self.scroll.scrollTo(value, 0, 0)
            : _self.scroll.scroll.instance.scroll.y;
        },
        getBoundingClientRect() {
          return {
            top: 0,
            left: 0,
            width: window.innerWidth,
            height: window.innerHeight,
          };
        },
        pinType: document.querySelector(".main").style.transform
          ? "transform"
          : "fixed",
      });
      ScrollTrigger.addEventListener("refresh", () => _self.scroll.update());

      ScrollTrigger.refresh();
    },
    initGsapMain() {
      gsap.from("h1.first__page-text,h2.first__page-text", {
        y: 10,
        rotate: 10,
        opacity: 0,
        delay: 0.3,
        duration: 0.7,
      });

      let tl = gsap.timeline({
        scrollTrigger: {
          trigger: "h1.first__page-text",
          scroller: ".main",
          start: "top 30%",
          end: "top 0",
          scrub: 3,
        },
      });
      tl.to(
        "h1.first__page-text",
        {
          x: -100,
        },
        "anim"
      );
      tl.to(
        "h2.first__page-text",
        {
          x: 100,
        },
        "anim"
      );
      tl.to(
        ".first__page video",
        {
          width: "90%",
        },
        "anim"
      );
      let tl_second = gsap.timeline({
        scrollTrigger: {
          trigger: "h1.first__page-text",
          scroller: ".main",
          start: "top -115%",
          end: "top -120%",
          scrub: 3,
        },
      });
      tl_second.to(".main", {
        backgroundColor: "#fff",
      });
    },
  },
};
</script>

<style lang="scss" scoped>
.main {
  background-color: #111;
  color: #fff;
  .first__page {
    min-height: 100vh;
    width: 100%;
    position: relative;
    z-index: 9;

    h1.first__page-text {
      position: relative;
      font-size: 8vw;
      font-weight: 500;
      top: 14vw;
      margin-left: 8vw;
      transform-origin: left;
    }
    h2.first__page-text {
      position: relative;
      font-size: 8vw;
      font-weight: 500;
      margin-top: 14vw;
      margin-left: 28.5vw;
      transform-origin: left;
    }

    .video__block {
      width: 100%;
      height: 100vh;
      display: flex;
      flex-direction: column;
      margin-top: 8vw;
      .row {
        position: relative;
        display: flex;
        justify-content: space-between;
        margin: 0 auto 0.5em;

        .left__text {
          position: relative;
          text-transform: uppercase;
          font-size: 12px;
        }
        .right__text {
          position: relative;
          text-transform: uppercase;
          font-size: 12px;
        }
      }
    }
  }
}

</style>
