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


        <nav class="main_menu">

            <div class="container">
                <div class="up-menu">
                    <div v-for="item in menu" :key="item.route" :class="{ active: isActive(item.route) }"
                        @click="setActiveRoute(item.route)" class="menu_voice">
                        <router-link :to="{ name: item.route }">
                            {{ item.text }}
                        </router-link>
                    </div>
                    <div class="underline" :style="underlineStyle"></div>
                </div>
                <div class="logo">
                    LOGO
                </div>

            </div>
        </nav>


    </header>

</template>