<script setup lang="ts">

    // when theres an event or something, comment this out so users dont get sent to the homepage
    navigateTo('/')


    useSeoMeta({
    title: "hi from Smash!",
    ogTitle: "hi from Smash!",
    description: "meow meow meow!!",
    ogDescription: "meow meow meow!!",
    });

</script>

<template>
    <main>
        <h1>Welcome!  <Purple>miaw!!</Purple></h1>
        <img src="/img/cat.png" class="pfp" />
        
        <hr>
        <p>Coming here from Smash and wanna play the games I was showcasing? Check them out below!</p>

        <div class="container">
            <ProjectCardV2 
                src="https://img.itch.zone/aW1nLzE3MzE3NDAzLnBuZw==/315x250%23c/pxmt%2BB.png"
                title="ChronoChamber"
                description="Complete the level before time catches up to you"
                long-description=
        "Short experimental puzzle game where you have to plan your moves before starting each level.

        'The Chronos Terminal is a powerful device that executes command blocks based into it as soon as you unseal the chamber. Use it to your advantage to escape the time loop you've been caught in!'

        - Winner of the Playmakers August Game Jam! 
        - Showcased at the playmakers booth for Smash 2025!"
                :buttons='[
                { link: "https://tabby-cat-nya.itch.io/chronochamber", text: "Play on Itch.io" }
                ]'
                :badges='["godot4","gamejam"]'
            />

            <ProjectCardV2
                src="https://img.itch.zone/aW1nLzE2Mjg0ODg2LnBuZw==/315x250%23c/6FRKz0.png"
                title="Arcane Raiders"
                description="Fight to the top of the tower with up to 4 players and an arsenal of powerful spells! Now available to play on Steam!"
                long-description=
        "Initially, This project was a part of Game Design Studio 1 at UTS where we worked in teams of 5 people to create a game through the semester. 

        During the assignment, my main contributions were general programming and game logic as well as some of the back-end code for the local and online multiplayer systems and UI.

        After the completion of the subject, our group continued to work on the project in our own time to further improve it and showcase it at future events such as the UTS Tech Fest where we received the Best Student Game award, and also South By South West where we were nominated for Best Student Game.

        In these later stages of development my focus shifted more to project management in addition building the Steam page and finalizing the integration of services such as achievements, cloud saves and discord rich presence into the game.

        On the 19th of February the game was released and since then we have had over 4200 unique players!"
                :buttons='[
                { link: "https://store.steampowered.com/app/2899410/Arcane_Raiders/", text: "Play on Steam" },
                { link: "https://discord.com/invite/3BPYMHqNve", text: "Join Discord" },
                { link: "https://cookiespl.itch.io/arcane-raiders", text: "View Itch.io page (Outdated)" }
                ]'
                :badges='[ "godot4", "steam"]'
            />
        </div>

        <hr>
        <p>Wanna check out the rest of my portfolio and website, press this button:</p>
        <BoldButton 
            href="https://tabbycat.dev"
            text="Go to tabbycat.dev!"
        />

        <hr>

        <!-- <h2 class="no-margin">Contact Details</h2>
        <div class="no-margin">
            <p>Email: <a href="mailto:tabby@tabbycat.dev">tabby@tabbycat.dev</a></p>
            <p>Linkedin: <a href="https://www.linkedin.com/in/tom--howarth/">https://www.linkedin.com/in/tom--howarth/</a></p>
        </div> -->

        <Socials>
              <Social 
                    src="img/bluesky.png" 
                    href="https://bsky.app/profile/tabbycat.dev" 
                />  
              <Social 
                    src="img/github.svg" 
                    href="https://github.com/tabby-cat-nya" 
                />
                <Social
                    src="img/itch-io.svg"
                    href="https://tabby-cat-nya.itch.io/"
                />
                <Social
                    src="img/steam.svg"
                    href="https://store.steampowered.com/search/?developer=Tabby"
                />
                <Social
                    src="img/backlogged.png"
                    href="https://backloggd.com/u/tabby_cat/games/user-rating/type:played"
                />
                <Social
                    src="img/furry.png"
                    href="https://www.furaffinity.net/user/fuzzysparkles/"
                />
                
                
            </Socials>
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
        /* gap: 2rem; */
    }

    .pfp{
        border-color: --accent;
        border-radius: 10px;
        border: 7px solid #e17ff5;
        width: 80%;
        max-width: 300px;
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