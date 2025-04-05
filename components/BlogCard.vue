<script setup>
const props = defineProps({
  href: String,
  heading: String,
  description: String,
  subheading: String,
  id: Number,
  tags: String
});
</script>

<template>
    <a class="blog-card" :href="props.href">
      <div class="blog-header">
        <h2> {{props.heading}}</h2>
        <p v-if="tags===''" class="blog-subheading">{{props.subheading}} - #{{ props.id }}</p>
          <p v-else class="blog-subheading">{{props.subheading}} - #{{ props.id }} - {{ props.tags }}</p>
      </div> 
      <div class="blog-content">
          <!-- <h2 class="heading"> {{props.heading}}</h2> -->
          
          <p>{{props.description}}</p>
      </div>
    </a>
    
</template>

<style scoped>
  .blog-card{
    border-color:  var(--accent);
    border-width: 3px;
    border-style: solid;
    background-color: rgb(36, 36, 36);
    text-decoration: none;
    margin-bottom: 10px;
  }

  h2{
    margin: 0;
  }

  .blog-header{
    background-color: var(--accent);
    color: black;
    padding-left: 10px;
    border-style: none none dotted none;
    border-color: var(--accent);
    border-width: 3px;
  }

  .blog-content{
    padding: 10px;
    margin: 0;
    color: var(--fg);
  }

  p{
    margin: 0;
  }

  .blog-subheading{
    margin: 0;
    text-align: center;
  }

</style>

<!-- <style scoped>
  :root {
    --bg: #351d3a;
    --fg: white;

    --accent: #e17ff5;
    --accent-dark: #630063;

    --max-width: 70rem;
}

    .card{
        /* position: relative; */
        /* text-align: center; */
        /* margin: 10px; */
        border-radius: 5px;
        overflow: hidden;
        color: white;
        background-color: rgb(62, 0, 104);
        background-color: rgb(62, 0, 104);
        width: 100%;
        text-decoration: none;
        height: 100px;
        
    }

    .text-content{
        position: absolute;
        top: 8px;
        left: 16px;
        text-align: left ;
        
    }

    .header{
      background-color: var(--accent);
      color:black;
    }

    .text-image{  
        /* filter: brightness(50%) blur(0px); */
        /* filter: blur(2px); */
    }
    .content{
            /* visibility:visible; */
    }

    .text-container:hover{
        background-color: var(--accent-dark);
        .text-content{
            visibility:visible;
        }
        
    }

    .subheading{
        color: grey;
        margin: 0;
        font-size: small;
    }

    h2{
        margin: 0;
    }
</style> -->