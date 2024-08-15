<script setup lang="ts">
// import ProjectCard from '~/components/ProjectCard.vue';

useSeoMeta({
  title: "Home",
  ogTitle: "Home",
  description: "My personal website.",
  ogDescription: "My personal website.",
});

var { data } = await useAsyncData('home', () => queryContent('blog').sort({id:-1}).limit(3).find())

</script>

<template>
  <main>

    <div class="container">
        <div class="left-col">
            <img src="https://avatars.githubusercontent.com/u/41929769" class="pfp" />
            <div class="aboutme">
            <h1>About Me</h1>
              <ul>
                  <li>20 years old, born in 2003</li>
                  <li>i use she/they pronouns</li>
                  <li>studying games development @ UTS</li>
                  <li>linux initiate, currently using Kunbuntu</li>
                  <li>Favourite game engine: <Purple>Godot!</Purple></li>
                  <li>meow meow~ nya!!! :3</li>
              </ul>
            </div>
        </div>
        <div class="right-col">
            <h1>Heyo! I'm <Purple>Tom</Purple> 👋</h1>
            <p>I'm a Games Developer from Sydney, Australia.</p>
            <p>I've been programming since 2015 and am currently in my final year of the Games Development degree at UTS</p>
            <p>Currently im working with my group, <a href="https://discord.gg/3BPYMHqNve">Team Stingray</a>, to create <a href="https://teamstingray.dev/arcane-raiders">Arcane Raiders</a>! Feel free to join our discord server if you'd like to follow along with development!</p>
            <Socials>
                <Social 
                    src="img/github.svg" 
                    href="https://github.com/Clevertop" 
                />
                <Social
                    src="img/itch-io.svg"
                    href="https://clevertop.itch.io/"
                />
                <Social
                    src="img/steam.svg"
                    href="https://store.steampowered.com/search/?developer=Clevertop"
                />
                <Social 
                    src="img/linkedin.svg" 
                    href="https://www.linkedin.com/in/tom--howarth/" 
                />
                
            </Socials>
            <h2>Tech i've got experience with:</h2>
            <img class="" src="https://skillicons.dev/icons?i=git,androidstudio,arduino,bash,blender,cs,cloudflare,css,fediverse,github,godot,html,idea,js,linux,lua,md,netlify,nextjs,nodejs,npm,nuxtjs,obsidian,php,postgres,py,react,sass,supabase,ts,unity,unreal,vercel,vscode,vue&perline=12" />
        </div> 
    </div>
    <hr/>
    <h1>Latest Project</h1>
    <div class="container">
      <ProjectCard
          class="left-col"
          src="https://img.itch.zone/aW1nLzE3MzE3NDAzLnBuZw==/315x250%23c/pxmt%2BB.png"
          href="https://clevertop.itch.io/chronochamber "
          heading="Chrono Chamber"
          description="Complete the level before time catches up to you"
      />
      <div class="right-col">
        <p>Released! - 14/8/2024</p>
        <p>3D Puzzle Game made for the <a href="https://itch.io/jam/playmakers-august-game-jam">Playmakers August Jam</a>!</p>
        <p>In each level you are given a number of "Command Blocks" to use which can be placed into the pedestals, After starting the level the pedestals are activated one by one in a clockwise order, when a pedestal is activated it will execute the command placed upon it (if any) such as "Jump", "Dash", or "Phase. Use these to reach each levels exit!"</p>
      </div>
      
      <!-- <div class="right-col">
        
      </div>
      <div class="right-col">
        
      </div> -->

    </div>
    <!-- seperator -->
    <hr/>
    <!-- featured projects, link to all? -->
    <h1>Featured Projects</h1>
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

      <ProjectCard 
        src="https://img.itch.zone/aW1nLzU3NzU5NTEucG5n/315x250%23c/eQja%2FA.png" 
        href="https://clevertop.itch.io/temple-of-the-silver-dragon"
        heading="Temple of the Silver Dragon"
        description="You have five minutes on the clock. How much treasure can you collect and escape with before time runs out? While this project is an older one, its also one of my favourites :)"
      />
      
    </div>
    
    <!-- seperator -->
    <hr/>
    <!-- latest blog posts, link to all? -->
    <h1 class="no-margins">Latest Blog Posts</h1>
    <a class="no-margins" href="/blog-index">View All</a>
    <!-- <p>Coming Soon!</p> -->

    <div class="container">
      
      <TextCard v-for="post in data"
        :key="post.id"
        :href="post._path"
        :heading="post.title"
        :subheading="post.date"
        :description="post.description"
        :id="post.id"
        :tags="post.tags"
      />
      
      
      
    </div>

    
     
  </main>
</template>

<style scoped>
.container {
    display: flex;
    
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

.cute-box{
  width: 350px;
  flex:2;
  background-color: pink;
}

@media (max-width: 1000px){
    .container{
        flex-direction: column;
    }
    .aboutme{
      visibility: collapse;
    }
    
}

.pfp {
  width: auto;
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

<style>
main {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 2rem;
  margin-top: 3.5rem;
  gap: 2rem;
}
hr {
  width: 100%;
  border: 1px dashed var(--accent-dark);
  max-width: var(--max-width);
}
.container > div {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
@media (prefers-color-scheme: light) {
  hr {
    filter: invert();
  }
}

.no-margins{
  margin: -10px;
}
</style>