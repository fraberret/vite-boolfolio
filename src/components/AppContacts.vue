<script>
export default {
    name: 'AppContacts'
}
</script>

<template>
   <div class="contacts">
    <div class="container">
        <div class="projects_title">
                <h1 class="section_heading">CONTACTS</h1>
                <div class="underline"></div>
                <p>Here you will find my contacts and socials</p>
            </div>

            <div class="contacts_container">
                <div class="container">
                    <div class="button">
                        <a>Send Me an Email</a>
                    </div>

                    <p>Or</p>
                    <div class="socials">
                    <a href="https://github.com/fraberret" target="_blank" rel="noopener noreferrer" > <i class="fa-brands fa-github" aria-hidden="true"></i> GitHub</a>
                    <a href="" target="_blank" rel="noopener noreferrer" ><i class="fa-brands fa-linkedin" aria-hidden="true"></i> Linkedin</a>
                    <a href="" target="_blank" rel="noopener noreferrer" ><i class="fa-brands fa-instagram" aria-hidden="true"></i> Instagram</a>
                    </div>
                </div>
            </div>
    </div>
   </div>
</template>



<style>

.contacts{
    background-image: linear-gradient(225deg, #4158D0 0%, #C850C0 46%, #FFCC70 100%);
    color:white;
    padding: 71px 0;
    background-color: #f3f3f3;
    
}

.contacts_container{
    padding: 2rem 0;
    text-align: center;
color: black;
    background-color:white;
    border-radius:30px;
    box-shadow: 0px 0px 5px 5px rgba(0, 0, 0, 0.1);

    & p{
        padding: 2rem 0;
    }
    

}

.socials{
    
    margin: auto;
    text-align: center;
    display: flex;
    flex-direction: column;
    

    
}
</style>