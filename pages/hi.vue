<script setup lang="ts">

useSeoMeta({
  title: "hi from SXSW!",
  ogTitle: "hi from SXSW!",
  description: "Landing page for visitors who scanned my business card",
  ogDescription: "Landing page for visitors who scanned my business card",
});

</script>

<template>
    <main>
        <h1>Welcome!</h1>
        <img src="/img/Tabby.JPG" class="pfp" />
        
        <hr>
        <p>Coming here from SXSW and wanna check out the games I was showcasing? Check them out below!</p>

        <div class="container">
            <ProjectCard 
                src="https://img.itch.zone/aW1nLzE2Mjg0ODg2LnBuZw==/315x250%23c/6FRKz0.png" 
                href="https://teamstingray.dev/arcane-raiders"
                heading="Arcane Raiders"
                description="Fight to the top of the tower with up to 4 players and an arsenal of powerful spells! We'll be showcasing it at SXSW Sydeny and its already avilable to wishlist on Steam!"
            />

            <ProjectCard 
                src="https://img.itch.zone/aW1nLzE2NTkxMzEyLnBuZw==/315x250%23c/0Y7BUi.png" 
                href="https://clevertop.itch.io/kitten-calamity"
                heading="Kitten Calamity"
                description="Cute little game made in about 29 hours for the UTS Tech Fest game jam! Grab a friend and find out who can be the most destructive little kitten in one minute :3"
            />
        </div>

        <hr>
        <p>Wanna check out the rest of my portfolio and website, press this button:</p>
        <BoldButton 
            href="https://tabbycat.dev"
            text="Go to tabbycat.dev!"
        />

        <hr>
        <h2 class="no-margin">Contact Details</h2>
        <div class="no-margin">
            <p>Email: <a href="mailto:tabby@tabbycat.dev">tabby@tabbycat.dev</a></p>
            <p>Linkedin: <a href="https://www.linkedin.com/in/tom--howarth/">https://www.linkedin.com/in/tom--howarth/</a></p>
        </div>
        <hr>
    </main>
    
</template>

<style scoped>
    main{
        text-align: center;
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 2rem;
        margin-top: 3.5rem;
        gap: 2rem;
    }

    .pfp{
        border-color: --accent;
        border-radius: 10px;
        border: 7px solid #e17ff5;
        width: 80%;
        max-width: 600px;
    }

    @media (max-width: 1000px){
        .container{
            flex-direction: column;
        }
    }

    .container {
        display: flex;
    }

    .no-margin{
        margin: 0;
    }

  
    hr {
        width: 100%;
        border: 1px dashed var(--accent-dark);
        max-width: var(--max-width);
    }

</style>