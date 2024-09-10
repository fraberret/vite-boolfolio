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

                        <a href="https://www.instagram.com/_.cccesco/" target="_blank" rel="noopener noreferrer"><i class="fa-brands fa-instagram"
                                aria-hidden="true"></i></a>

                        <a href="https://www.facebook.com/francesco.berretta.90" target="_blank"
                            rel="noopener noreferrer"><i class="fa-brands fa-facebook" aria-hidden="true"></i></a>

                        <a href="https://github.com/fraberret" target="_blank" rel="noopener noreferrer"><i
                                class="fa-brands fa-github" aria-hidden="true"></i></a>

                        <a href="https://www.linkedin.com/in/francesco-berretta-dev/" target="_blank" rel="noopener noreferrer"><i class="fa-brands fa-linkedin"
                                aria-hidden="true"></i></a>

                        <a href="https://stackoverflow.com/users/27203265/francesco-berretta" target="_blank" rel="noopener noreferrer"><i class="fa-brands fa-stack-overflow"
                                aria-hidden="true"></i></a>
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


