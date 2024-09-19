<script>
import gsap from 'gsap';
export default {
    name: 'AppSkills',

    data() {
        return {
            skills: [
                {
                    'name': 'HTML',
                    'image': '/images/logo-html.svg'
                },
                {
                    'name': 'CSS',
                    'image': '/images/logo-css.svg'
                },
                {
                    'name': 'Bootstrap',
                    'image': '/images/logo-bootstrap.svg'
                },
                {
                    'name': 'JavaScript',
                    'image': '/images/logo-javascript.svg'
                },
                {
                    'name': 'Vue',
                    'image': '/images/logo-vue.svg'
                },
                {
                    'name': 'WordPress',
                    'image': '/images/logo-wordpress.svg'
                },
                {
                    'name': 'PHP',
                    'image': '/images/logo-php.svg'
                },
                {
                    'name': 'Laravel',
                    'image': '/images/logo-laravel.svg'
                },
                {
                    'name': 'MySQL',
                    'image': '/images/logo-mysql.svg'
                },
                {
                    'name': 'SASS',
                    'image': '/images/logo-sass.svg'
                },
                {
                    'name': 'GSAP',
                    'image': '/images/logo-gsap.svg'
                },
            ],
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
                        xPercent: xPercent => logosWrap(parseFloat(xPercent))
                    }
                })
            }
        }
    }
}
</script>

<template>
    <div class="skills">
        <div class="container">
            <h3>My Skills</h3>
        </div>
        <!-- Skills Section -->
        <div class="skills-container">

            <!-- Skills Logos -->
            <div v-for="skill in skills" class="wrapper" ref="logoWrapper">
                <div class="logo">
                    <img :src=skill.image :alt="skill.name + ' logo'">
                    <h4>{{ skill.name }}</h4>
                </div>
            </div>
        </div>
    </div>
</template>
