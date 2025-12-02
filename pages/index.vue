<script setup lang="ts">
// import ProjectCard from '~/components/ProjectCard.vue';


// const route=useRoute();
// const path = computed(() =>route.path);
// const path = ref(window.location.pathname);
// console.log("starting meow");
// console.log(path);



useSeoMeta({
  title: "Home",
  ogTitle: "Home",
  description: "My personal website.",
  ogDescription: "My personal website.",
});

var { data } = await useAsyncData('home', () => queryContent('blog').where({hidden : {$not : true}}).sort({id:-1}).limit(3).find())

</script>

<template>
  <main>

    <div class="container">
        <div class="left-col">
            <img src="https://avatars.githubusercontent.com/u/41929769" class="pfp" />
            <div class="aboutme">
            <h1>About Me</h1>
              <ul>
                  <li>i use they/she pronouns</li>
                  <li>studying games development</li>
                  <!-- <li>linux initiate, currently using Mint 22</li> -->
                  <li>Favourite game engine: <Purple>Godot!</Purple></li>
                  <li>Terrified of big numbers</li>
                  <li>meow meow~ nya!!! :3</li>
              </ul>
            </div>
        </div>
        <div class="right-col">
            <h1>Heyo! I'm <Purple>Tabby</Purple> 👋</h1>
            <p>I'm a Games Developer from Sydney, Australia.</p>
            <!-- <p>I've been programming since 2015 and am currently in my final year of the Games Development degree at UTS</p> -->
            <!-- <p>Currently I'm teaching Programming Fundamentals and Programming 1 at UTS as a Casual Academic, In my free time I'm working on side projects which I sometimes post about on my <a href="https://bsky.app/profile/tabbycat.dev">Bluesky page</a> </p> -->
            <p>In my free time I'm working on side projects which I sometimes post about on my <a href="https://bsky.app/profile/tabbycat.dev">Bluesky page!</a> </p>
            <!-- <a href="https://oldweb.tabbycat.dev">dont mind me, just testing something</a> -->
            <!-- <a href="meowwalking://oldweb.tabbycat.dev">dont mind me, just testing something</a> -->
            <!-- <p>Currently im working with my group, <a href="https://teamstingray.dev">Team Stingray</a>, to finish up our uni project <a href="https://teamstingray.dev/arcane-raiders">Arcane Raiders</a> and release it on Steam! Feel free to join our <a href="https://discord.gg/3BPYMHqNve">discord server</a> if you'd like to follow along with development!</p> -->
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
            <!-- <h2>Tech i've got experience with:</h2>
            <img class="" src="https://skillicons.dev/icons?i=git,androidstudio,arduino,bash,blender,cs,cloudflare,css,fediverse,github,godot,html,idea,js,linux,lua,md,netlify,nextjs,nodejs,npm,nuxtjs,obsidian,php,postgres,py,react,sass,supabase,ts,unity,unreal,vercel,vscode,vue,processing&perline=12" /> -->
        </div> 
    </div>
    <hr/>
    <h1>Current Projects</h1>
    <div class="featured-container">

      <ProjectCardV2
          src="img\adventofcode.png"
          title="Advent of Code 2025"
          description="Annual programming challenge"
          long-description=
"Advent of Code is an Annual programming challenge, you can use whatever language you want to try and solve each days puzzle.

This year I'm attempting the challenge in Rust"
          :buttons='[
          {link:"https://github.com/tabby-cat-nya/advent-of-code-2025",text:"Visit Reposity"},
        ]'
        :badges='["rust"]'
      />

      <ProjectCardV2
          src="img\fabcatAlpha.png"
          title="Fabcat"
          description="Fabsoc Discord Bot"
          long-description=
"Discord bot I programmed for fabrication society to help manage the status of the printers and track the inventory of spools"
          :badges='["godot4"]'
          :buttons= '[
            {link:"http://tiny.cc/FabSocDiscord",text:"Join Fabsoc"},
            {link:"https://utsfabsoc.github.io/Docs/Technician-Zone/Fabcat-Discord-Bot",text:"Read the Docs"},
          ]'
      />

      

      <ProjectCardV2
          src="img\lunar.png"
          title="Super Lunar (Working Title)"
          description="Cross between lunar lander and balloon trip breeze"
          long-description=
"Im working on a new prototype game idea, no idea if it will come to anything but figured i might aswell try it out. Basically its a cross between balloon Trip Breeze from Nintendo Land and Lunar Lander - the arcade game. Players will have to navigate their fragile little ship around obstacles with limited fuel reserves to reach the end. "
          :buttons='[
          
        ]'
        :badges='["godot4","prototype"]'
      />

      

      <!-- <div class="featured-text">
        <p>Pikmin Bloom is one of the funny little geospatial games that Niantic made with Nintendo</p>
        <p>I'm trying to figure out how many of the games mechanics work in relation to event rewards and what the best way to manage pikmin and mushrooms are especially early each month</p>
        <p>Follow updates and findings on my <a href="https://bsky.app/profile/tabbycat.dev">Bluesky</a>!</p>
      </div> -->
    </div>
    <!-- seperator -->
    <hr/>
    <!-- featured projects, link to all? -->
    <h1>Featured Projects</h1>
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
        :badges='[ "godot4", "steam"]'
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
        :badges='["godot4","gamejam"]'
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
        :badges='["unity","airtable"]'
      />
      
    </div>
    <BigButton text="View Entire Portfolio >>>" href="/projects"/>
    
    <!-- seperator -->
    <hr/>
    <!-- latest blog posts, link to all? -->
    <h1 class="no-margins">Latest Blog Posts</h1>
    
    <!-- <p>Coming Soon!</p> -->

    <div class="blog-container">
      
      <BlogCard v-for="post in data"
        :key="post.id"
        :href="post._path"
        :heading="post.title"
        :subheading="post.date"
        :description="post.description"
        :id="post.id"
        :tags="post.tags"
      />
      
      
      
    </div>
    <!-- <a class="no-margins" href="/blog-index">View All >>></a> -->
    <BigButton text="View All >>>" href="/blog-index"/>
    
     
  </main>
</template>

<style scoped>
h1{
  text-align: center;
}



.container {
  display: flex;
  margin-left: 10%;
  margin-right: 10%;
  justify-content: center;
    
}

@media (max-width: 1000px){
  .container{
    margin: 0;
  }
  
}

.featured-container{
  display: flex;
  width: 100%;
  justify-content: center;
}

.featured-container>div{
  width:30%;
}

@media (max-width: 1000px){
  
  .featured-container>div{
    width:80%;
    align-self: center;
  }
}
.blog-container{
  display: flex;
  flex-direction: column;
  width: 80%;
  justify-content: center;
  margin-left: auto;
  margin-right: auto;
}

.small-image-pls {
  height: 20%;
}

.left-col {
    flex:1;
    width: 50%;
    padding: 20px;
    align-self: center;
    /* background-color: purple; */
}

.right-col {
    padding: 20px;
    width: 50%;
    flex: 2;
    align-self: center;
    /* background-color: blueviolet; */
}

.featured-text {
    padding: 0px;
    width: 100%;
    flex: 2;
    align-self: center;
    /* background-color: blueviolet; */
}

.cute-box{
  width: 350px;
  flex:2;
  background-color: pink;
}

@media (max-width: 1000px){
    .container{
        flex-direction: column;
    }
    .featured-container{
        flex-direction: column;
        margin-left: 0%;
        margin-right: 0%;
    }
    .aboutme{
      display: none;
    }
    
}

.pfp {
  width: 100%;
  aspect-ratio: 1/1;
  border-radius: 100%;
  box-shadow:
    0 20px 25px -5px rgb(0 0 0 / 0.1),
    0 8px 10px -6px rgb(0 0 0 / 0.1);
}
.short {
  width: 50%;
}
@media screen and (max-width: 600px) {
  .short {
    width: 100%;
  }
}
</style>

<style scoped>
main {
  /* display: flex;
  flex-direction: column;
  align-items: center; */
  /* padding: 2rem; */
  /* margin-top: 3.5rem; */
  /* gap: 2rem; */
}

.container > div {
  /* display: flex;
  flex-direction: column; */
  /* gap: 1rem; */
}
/* @media (prefers-color-scheme: light) {
  hr {
    filter: invert();
  }
} */

/* .no-margins{
  margin: -10px;
} */
</style>