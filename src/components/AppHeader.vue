<script>
import gsap from 'gsap';
import { ref } from 'vue';
export default {
    name: 'AppHeader',
    data() {
        return {
            menu: [
                {
                    'text': 'Home',
                    'route': 'home'
                },
                {
                    'text': 'About',
                    'route': 'aboutme'
                },
                {
                    'text': 'Projects',
                    'route': 'projects'
                },
                {
                    'text': 'Contacts',
                    'route': 'contacts'
                }
            ],
            activeRoute: '',
            isMenuOpen: false,

        }
    },

    mounted(){
        this.logoRotation();

    },

    methods: {
        toggleMenu() {
            this.isMenuOpen = !this.isMenuOpen
            console.log(this.isMenuOpen);
            let mobileMenu = this.$refs.mobileMenu;
            let voice = this.$refs.menuVoice
            let tl = gsap.timeline();

            if (this.isMenuOpen) {
                tl.to(mobileMenu, {
                    display: "block",
                    opacity: 1,
                    height: 292,
                    duration: 0.3,
                    ease: "power3.inOut"
                }).to(voice, {
                    duration: 0.3,
                    opacity: 1,
                    height: "25%",
                    ease: "power3.inOut"
                }, "-=0.3")

            } else {
                tl.to(mobileMenu, {
                    duration: 0.3,
                    height: 0,
                    opacity: 0,
                    display: "block",
                    ease: "power3.out"
                }).to(voice, {
                    duration: 0.3,
                    opacity: 0,
                    height: 0,
                    ease: "power3.out"
                }, "-=0.3")
            }
        },

        logoRotation(){
            let tl=gsap.timeline();
            let logo = this.$refs.mainLogo;

            tl.to(logo,{
                duration:1,
                left:0,
                rotation:720,
                
            })

        }
    }
}
</script>

<template>
    <header>

        <!-- Header section-->
        <div class="main_menu">

            <!-- Logo -->
            <a href="#home"><div class="logo_container ">
                <img class="main_logo" src="/images/logo.jpg" ref="mainLogo" alt="main website logo">
                <strong>Francesco Berretta</strong>
            </div></a>

            <!-- Menu Section -->
            <ul class="up-menu">

                <!-- Menu voices -->
                <li v-for="item in menu" class="menu_voice">
                    <a :href="'#' + item.route">{{ item.text }}</a>
                </li>

                <!-- Mobile Menu Buttons -->
                <div @click="toggleMenu" class="open_menu">
                    <i v-if="!isMenuOpen" class="fa fa-bars" aria-hidden="true"></i>
                    <i v-else class="fa fa-close" aria-hidden="true"></i>
                </div>
            </ul>
        </div>

        <!-- Mobile Menu -->
        <div class="sm_menu_section" ref="mobileMenu">

            <div @click="toggleMenu()" v-for="item in menu" class="sm_menu_voice" ref="menuVoice">
                <a :href="'#' + item.route">{{ item.text }}</a>
            </div>
        </div>
    </header>
</template>