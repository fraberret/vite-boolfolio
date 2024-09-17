<script>
import { left } from '@popperjs/core';
import gsap from 'gsap';
export default {
    name: 'AppSkills',

    data() {
        return {

            skills: [

                {
                    'name': 'html',
                    'image': '/images/logo-html.svg'
                },

                {
                    'name': 'css',
                    'image': '/images/logo-css.svg'
                },

                {
                    'name': 'bootstrap',
                    'image': '/images/logo-bootstrap.svg'
                },

                {
                    'name': 'javascript',
                    'image': '/images/logo-javascript.svg'
                },

                {
                    'name': 'vue',
                    'image': '/images/logo-vue.svg'
                },

                {
                    'name': 'wordpress',
                    'image': '/images/logo-wordpress.svg'
                },

                {
                    'name': 'php',
                    'image': '/images/logo-php.svg'
                },

                {
                    'name': 'laravel',
                    'image': '/images/logo-laravel.svg'
                },

                {
                    'name': 'mysql',
                    'image': '/images/logo-mysql.svg'
                },

                {
                    'name': 'sass',
                    'image': '/images/logo-sass.svg'
                },

                {
                    'name': 'gsap',
                    'image': '/images/logo-gsap.svg'
                },



            ],
            // Questo conterrà i riferimenti agli elementi DOM


        }
    },

    mounted() {

        this.scroll();

    },

    methods: {

        scroll() {
            let wrapper = this.$refs.logoWrapper;
            gsap.set(wrapper, {
                autoAlpha: 1
            })

            wrapper.forEach((logo, i) => {

                gsap.set(logo, { xPercent: 100 * i });

            });

            if (wrapper.length > 5) {
                let logosWrap = gsap.utils.wrap(-100, ((wrapper.length - 1) * 100));
                let duration = wrapper.length * 2.5;
                gsap.to(wrapper, {
                    xPercent: `-=${wrapper.length * 100}`,
                    duration,
                    repeat: -1,
                    ease: 'none',
                    modifiers: {
                        // run xPercent through the wrap function
                        xPercent: xPercent => logosWrap(parseFloat(xPercent))
                    }

                })
            }
        }

    }



}
</script>

<template>

    <!-- Skills Section -->
    <div class="skills">


        <!-- Skills Logos -->
        <div v-for="skill in skills" class="wrapper" ref="logoWrapper">
            <div class="logo">
                <img :src=skill.image alt="">
            </div>
        </div>





    </div>
</template>

<style>

.skills {
  width: 100%;
  height: 100px; 
  position: relative;
  display: flex;
  align-items: center;
  overflow: hidden; 

}

.wrapper {
  width: 20%; 
  height: 100%;
  position: absolute;
  top: 0;
  left: 0; 

 
}

.wrapper::after {
  content: "";
  display: block;
  width: 100%;
  height: 100%;
  padding-bottom: 100%; 
 
}

.logo {
  display: flex; 
  justify-content: center;
  align-items: center;
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;

}

.logo img {
  width: 50px; 
  height: auto; 
  display: block; 
}


</style>
