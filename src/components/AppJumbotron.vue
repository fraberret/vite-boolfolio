<template>
  <div>
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

    <!-- Palla iniziale al centro dello schermo -->
  </div>
</template>

<script>
import { gsap } from "gsap";

export default {
  mounted() {
    // Quando la pagina si carica, avviamo l'animazione
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
            duration: 0.5,
            background: "linear-gradient(43deg, #4158D0 0%, #C850C0 46%, #FFCC70 100%)",
            ease: "power3.inOut"
          })
          gsap.to(jumbotronContent, {
            duration:0.5,
            opacity: 1,
            ease: "power3.inOut"

          })
          tl.to(colorBall, {
            duration: 0.5,
            opacity: 0,
            ease: "power3.Out"
          })


        }


      });





    }

  }
};
</script>

<style scoped>
/* Stili di base */


.jumbotron {

  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  overflow: hidden;
  /* Jumbotron a tutta altezza */
  background-color: #fff;
  /* Colore iniziale di sfondo */
  transition: background 1s ease;
  /* Transizione morbida dello sfondo */
}

h1 {
  font-size: 4rem;

}

/* La palla iniziale */
.color-ball {

  max-width: 100%;
  position: absolute;
  top: 0;
  left: 50%;
  transform: translate(-50%, -50%) scale(1);
  width: 100px;
  height: 100px;
  background-color: #ff0000;
  /* Colore iniziale della palla */
  border-radius: 50%;
  z-index: 10;
  transition: scale 1s ease;
}
</style>