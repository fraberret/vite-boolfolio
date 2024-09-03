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
      /*   setActiveRoute(route) {
            this.activeRoute = route;
        },
        isActive(route) {
            return this.$route.name === route || this.activeRoute === route;
        }, */

        toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    }
    }

}
</script>

<template>
    <header>

        <!-- Menu section-->
        <div class="main_menu d-flex justify-between align-center">

            <!-- Logo -->
            <div class="d-flex align-center">
                <img class="main-logo" src="/images/logo.jpg" alt="">
                <strong class="align-center">Francesco Berretta</strong>
            </div>

            <!-- Menu voices -->
             <div class="up-menu">

                <div v-for="item in menu" class="menu_voice">
                    <a :href="'#'+ item.route">{{ item.text }}</a>
                </div>
              
                <div @click="toggleMenu" class="open_menu">
                    <i v-if="!isMenuOpen" class="fa fa-bars" aria-hidden="true"></i>
                    <i v-else class="fa fa-close" aria-hidden="true"></i>
                </div>
            </div>
        </div>

        <div class="sm_menu_section" :class="{ 'menu-open': isMenuOpen, 'menu-closed': !isMenuOpen }">
            <ul>
                <li v-for="item in menu" class="sm_menu_voice">
                   <a :href="'#'+ item.route">{{ item.text }}</a>
                </li>
            </ul>
            

        </div>

    </header>

</template>