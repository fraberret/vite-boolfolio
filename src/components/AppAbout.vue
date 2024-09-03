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
    <div class="aboutme">
        <div class="container">
           <div class="aboutme_title">
            <h1>ABOUT ME</h1>
            <div class="underline"></div>
            <p>Here you will find more information about me</p>
        </div>


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
        <AppSkills></AppSkills> 
        </div>
        
    </div>






</template>



<style>
.underline {

    width: 30px;
    border-radius: 25%;
    height: 4px;
    margin: 1rem auto;
    background-color: red;
}

.aboutme {
   padding: 4rem 0;
    background-color: #e7e6e6;;

}

.aboutme_title {
    margin-bottom: 4rem ;
    text-align: center;


}

.aboutme_info {
    & h3 {
        margin-bottom: 1.5rem;
    }
}
</style>