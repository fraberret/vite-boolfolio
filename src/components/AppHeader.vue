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
                    'route': 'about'
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
            activeRoute: ''
        }
    },
    methods: {
        setActiveRoute(route) {
            this.activeRoute = route;
        },
        isActive(route) {
            return this.$route.name === route || this.activeRoute === route;
        }
    }

}
</script>

<template>
    <header>

        <!-- Menu section-->
        <nav class="main_menu">
            <div class="container d-flex justify-between align-center">

                <!-- Logo -->
                <div class="logo">
                    <img src="/images/logo.jpg" alt="">
                </div>

                <!-- Menu voices -->
                <div class="up-menu">
                    <div v-for="item in menu" :key="item.route" :class="{ active: isActive(item.route) }"
                        @click="setActiveRoute(item.route)" class="menu_voice">
                        <router-link :to="{ name: item.route }">
                            {{ item.text }}
                        </router-link>
                    </div>

                    <div class="underline"></div>
                </div>
            </div>
        </nav>
    </header>

</template>