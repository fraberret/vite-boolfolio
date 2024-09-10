<script>
import AppSkills from './AppSkills.vue';

export default {
    name: 'AppAbout',

    components: {
        AppSkills
    }

}
</script>

<template>

    <!-- About Me Section -->
    <div id="aboutme" class="aboutme">
        <div class="container">

            <!-- About Me Title -->
            <div class="sections_title">
                <h1 class="section_heading">ABOUT ME</h1>
                <div class="underline"></div>
                <p>Here you will find more information about me</p>
            </div>

            <!-- About Me Indo -->
            <div class="aboutme_info">
                <h3>Get to know me!</h3>

                <p>I have always been a very curious person and passionate about <strong>Problem
                        Solving</strong> With a background in the world of audio as a sound engineer, I have
                    honed my skills in solving complex problems and adapting to new challenges with creativity
                    and determination. In 2024 I decided to make a <strong>change</strong> in my life and
                    embarked on this fantastic path as a <strong>Web Developer</strong> which allowed me to
                    learn many skills and <strong>another</strong> great passion.</p>
                <br>
                <p>I'm open to <strong>Job </strong>opportunities where I can contribute, learn and grow. If you
                    have a good opportunity that matches my skills and experience then don't hesitate to
                    <strong>contact</strong> me.
                </p>
            </div>
        </div>
        <AppSkills></AppSkills>
    </div>
</template>


