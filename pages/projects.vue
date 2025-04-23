<template>
  <main>
    <BigButton text="<<< Return Home" href="/"/>
    <h1 class="no-margin">My Projects</h1>
    <hr>
    <div class="featured-container">
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
      />

      <ProjectCardV2 
        src="https://img.itch.zone/aW1nLzE2NTkxMzEyLnBuZw==/315x250%23c/0Y7BUi.png" 
        href="https://clevertop.itch.io/kitten-calamity"
        title="Kitten Calamity"
        description="Cute little game made in about 29 hours for the UTS Tech Fest game jam! Grab a friend and find out who can be the most destructive little kitten in one minute :3"
        long-description=
"This little project was made with a team of 3 for the UTS Tech Fest Game Jam. Using Godot, my main focus was on the player controls, the overall game logic and the user interface. 

At the end of the game jam our game received the Most Intuitive Game award."
        :buttons='[
          { link: "https://clevertop.itch.io/kitten-calamity", text: "Play on Itch.io" }
        ]'
      />

      <ProjectCardV2 
        src="https://img.itch.zone/aW1nLzU3NzU5NTEucG5n/315x250%23c/eQja%2FA.png"
        title="Temple of the Silver Dragon"
        description="You have five minutes on the clock. How much treasure can you collect and escape with before time runs out? While this project is an older one, its also one of my favourites :)"
        long-description=
"Temple of the Silver Dragon is one of my older projects which was made in the Unity game engine before I switched over to Godot.

It's one of my most extensive works as it entirely a solo project, In addition to the main game play components such as: First person camera and movement, level design, enemy logic, game logic, testing and balancing. I also implemented some special features including a 'Ghost' replay system and an online leaderboard using Airtable. Through this leaderboard I've been able to calculate that a total of over 110 hours have been played!"
        :buttons='[
          { link: "https://clevertop.itch.io/temple-of-the-silver-dragon", text: "Play on Itch.io" }
        ]'
      />

      <ProjectCardV2 
        src="https://img.itch.zone/aW1nLzE3MzE3NDAzLnBuZw==/315x250%23c/pxmt%2BB.png"
        title="ChronoChamber"
        description="Complete the level before time catches up to you"
        long-description=
"Short experimental puzzle game where you have to plan your moves before starting each level.

'The Chronos Terminal is a powerful device that executes command blocks based into it as soon as you unseal the chamber. Use it to your advantage to escape the time loop you've been caught in!'

Winner of the Playmakers August Game Jam!"
        :buttons='[
          { link: "https://tabby-cat-nya.itch.io/chronochamber", text: "Play on Itch.io" }
        ]'
      />

      <ProjectCardV2 
        src="https://img.itch.zone/aW1nLzEyNjA2MDI1LnBuZw==/315x250%23c/vaNWSF.png"
        title="Starship Scramble"
        description="Pilot your starship between asteroids and make it home as fast as possible to turn a profit. Watch your fuel gauge; if you run out, you'll float in the abyss of space forever..."
        long-description=
"Made in Unity and Showcased at South By South West 2023 this project was made for Game Design Methodologies at UTS

I implemented the core mechanic of the inside and outside views of the ship and the third level of the game which introduces a much larger ship, moving ship components, and fuel draining zones"
        :buttons='[
          { link: "https://ethan-lucas.itch.io/starship-scramble", text: "Play on Itch.io" }
        ]'
      />

      <ProjectCardV2 
        src="https://img.itch.zone/aW1nLzE0NjYyOTAwLnBuZw==/315x250%23c/UaC28P.png"
        title="Smoothie Maker Pro"
        description="You're running the world's greatest smoothie truck! The customers are waiting... Don't take too long or they'll get angry!"
        long-description=
"Sliding puzzle game made in Godot. Customers will make orders which are made up of patterns of shapes, the player must slide fruits around the grid in order to make the requested patterns

Made for the Pixel Jam 2024 which we scored 1st place in for the overall ranking!

My main focus was on the online leaderboard and login system, After the game jam I also experiemnted with making an android app port"
        :buttons='[
          { link: "https://itch.io/jam/pixel-jam-2024/rate/2469428", text: "Play on Itch.io" }
        ]'
      />

      <ProjectCardV2 
        src=" img\doodleJump.png"
        title="ThreeJS Doodle Jump"
        description="Cute little remake of Doodle Jump in ThreeJS"
        long-description=
"Designed for Computer Graphics, our project was to recreate the mobile game 'Doodle Jump' with ThreeJS

(Note: Game may not load all assets on first play)"
        :buttons='[
          { link: "https://doodle-jump-nya.netlify.app/", text: "Play" }
        ]'
      />

      <ProjectCardV2 
        src=" img\stingray.png"
        title="Team Stingray Website"
        description="Website I made and maintain which we use to display our group and projects at showcases"
        long-description=
"Made in Vue.js and Nuxt, Hosted on Vercel"
        :buttons='[
          { link: "https://teamstingray.dev/", text: "Visit https://teamstingray.dev/" }
        ]'
      />
      
    </div>
    
  </main>
</template>

<script lang="ts" setup>
  useSeoMeta({
    title: "Projects",
    ogTitle: "Projects",
    description: "I make cool stuff!",
    ogDescription: "I make cool stuff!",
  });
</script>

<style scoped>
  main {
    padding: 2rem;
    margin-top: 3.5rem;
  }

  .no-margin{
    margin: 0;
    text-align: center;
  }

  .featured-container{
    display: flex;
    flex-wrap: wrap;
    width: 100%;
    justify-content: center;
  }

  .featured-container>div{
    width:30%;
  }

  @media (max-width: 1000px){
    .featured-container{
        flex-direction: column;
        margin-left: 0%;
        margin-right: 0%;
    }

    .featured-container>div{
    width:100%;
  }
    
}
</style>