<template>
  <div>
    <!-- Jumbotron con lo sfondo dinamico -->
    <div class="jumbotrono" ref="jumbotron">
      <div class="color-ball" ref="colorBall"></div>
      <h1>Benvenuti!</h1>
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

      let tl = gsap.timeline();

      tl.to(colorBall, {

        duration: 1.3,
        top: "50%",
        background: "linear-gradient(43deg, #4158D0 0%, #C850C0 46%, #FFCC70 100%)",
        ease: "power3.inOut",

       


      });

      tl.to(colorBall, {

        duration: 0.5,
        scale: 50,
       
        ease: "power3.inOut",

     

        onComplete: () => {
          tl.to(colorBall, {
            duration: 0.5,
            opacity: 0,
            ease: "power3.Out"
          })


        }


      });

      tl.to(jumbotron, {
        duration: 0,
        background: "linear-gradient(43deg, #4158D0 0%, #C850C0 46%, #FFCC70 100%)",
        ease: "power3.inOut"
      })



    }

  }
};
</script>

<style scoped>
/* Stili di base */
html,
body {
  margin: 0;
  padding: 0;
  height: 100%;

}

.jumbotrono {
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
  color: #fff;
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