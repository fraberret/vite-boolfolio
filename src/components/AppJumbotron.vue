<template>
    <!-- Jumbotron con lo sfondo dinamico -->
    <div class="jumbotron" ref="jumbotron">
      <div class="color-ball" ref="colorBall"></div>
      <div class="jumbotron_content" ref="jumbotronContent">

        <!-- Jumbotron Title -->
        <h1>Hi, I'm Francesco Berretta</h1>

        <!-- Jumbotron Info -->
        <div class="jumbotron_info">
          <p>A Result-Oriented Web Developer building and managing Websites and Web Applications that leads to
            the success of the overall product</p>
        </div>

        <!-- Jumbotron Button -->
        <div class="button">
          <a href="#projects">Projects</a>
        </div>
      </div>
    </div>
  
</template>

<script>
import { gsap } from "gsap";

export default {
  mounted() {
    this.animateColorExplosion();
  },
  methods: {
    animateColorExplosion() {
      let colorBall = this.$refs.colorBall
      let jumbotron = this.$refs.jumbotron
      let jumbotronContent = this.$refs.jumbotronContent
      let tl = gsap.timeline();
      
      tl.to(colorBall, {
        duration: 1.3,
        top: "50%",
        background: "linear-gradient(43deg, #4158D0 0%, #C850C0 46%, #FFCC70 100%)",
        ease: "power3.inOut",
      });

      tl.to(colorBall, {
        duration: 0.3,
        scale: 50,
        ease: "power3.in",
        onComplete: () => {
          tl.to(jumbotron, {
            duration: 0.3,
            background: "linear-gradient(43deg, #4158D0 0%, #C850C0 46%, #FFCC70 100%)",
            ease: "power3.in"
          })
          gsap.to(jumbotronContent, {
            duration: 0.5,
            opacity: 1,
            ease: "power3.inOut"
          })
          tl.to(colorBall, {
            duration: 0.5,
            opacity: 0,
            ease: "power3.Out"
          })
          tl.to(colorBall, {
            display: "none"
          })
        }
      });
    }
  }
};
</script>
