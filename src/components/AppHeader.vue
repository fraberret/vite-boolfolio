<script>
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
    methods: {
        toggleMenu() {
            this.isMenuOpen = !this.isMenuOpen;
        }
    }

}
</script>

<template>
    <header>

        <!-- Header section-->
        <div class="main_menu">

            <!-- Logo -->
            <div class="logo_container ">
                <img class="main_logo" src="/images/logo.jpg" alt="main website logo">
                <strong >Francesco Berretta</strong>
            </div>

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
        <div class="sm_menu_section" :class="{ 'menu_open': isMenuOpen, 'menu_closed': !isMenuOpen }">
            <ul>
                <li v-for="item in menu" class="sm_menu_voice">
                    <a :href="'#' + item.route">{{ item.text }}</a>
                </li>
            </ul>
        </div>
    </header>
</template>