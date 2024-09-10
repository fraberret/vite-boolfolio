        <script>
        export default {
            name: 'AppFooter',

            data() {
    return {
      currentYear: new Date().getFullYear()
    };
  }
        }
</script>

<template>

    <!-- Footer Section -->
    <footer>
        <div class="container">

            <!-- Footer Info -->
            <div class="footer_upper">

                <!-- Footer Socials -->
                <div class="footer_social_section">
                    <h3 class="footer_heading">SOCIAL</h3>
                    <div class="footer_social_icon">
                        <a href=""><i class="fa-brands fa-instagram" aria-hidden="true"></i></a>
                        <a><i class="fa-brands fa-facebook" aria-hidden="true"></i></a>
                        <a><i class="fa-brands fa-github" aria-hidden="true"></i></a>
                        <a><i class="fa-brands fa-linkedin" aria-hidden="true"></i></a>
                        <a><i class="fa-brands fa-stack-overflow" aria-hidden="true"></i></a>
                    </div>
                </div>

                <!-- Footer Name -->
                <div class="footer_name_section">
                    <h3 class="footer_heading">FRANCESCO BERRETTA</h3>
                    <p>A Result-Oriented Web Developer building and managing Websites and Web Applications that leads to
                        the success of the overall product</p>
                </div>

            </div>

            <!-- Footer Copyright -->
            <div class="footer_lower">
            <p>
          © Copyright {{ currentYear }}. Made By Francesco Berretta
          </p>
            </div>
        </div>
    </footer>
</template>


<style>
footer {
    background-color: #000;
    
    color: white;
}

.footer_social_section{
    margin-bottom: 3rem;
}

.footer_upper{
    width: 100%;
    padding: 4rem 0;

   
}



.footer_lower{
    text-align: center;
    border-top: 1px solid #ffffff;
    padding: 4rem 0;
}

.footer_social_icon {
    font-size: 20px;
   
    display: flex;
    gap: 0.7rem;

    & a i {
        color: white;
    }

    

    

}
.footer_heading{
        margin-bottom: 1rem;
    }

</style>