<template>
  <div class="badge" :style="badges[props.id].color" v-if="badges[props.id]">
  <!-- <div class="badge" v-if="badges[props.id]"> -->
    <img :src=badges[props.id].icon class="icon"  />
    <p class="text">{{ badges[props.id].name }}</p>
  </div>
</template>

<script lang="ts" setup>
  
 

  // methods:{
  //   meow()
  //     {
  //       return "color : blue;" 
  //     }
  // }
  


  const props = defineProps<{
    id: string,
    // text: string,
    // icon: string,
  }>();

  type IBadge = {
   name: string;
   icon: string;
   color: string;
  }

  function meow() {
    return 1;
  }

  //todo: in future make the icons local instead of links
  const badges: { [id: string]: IBadge; } = {
    "godot4": { name: "Godot 4", color:"background-color : white", icon: "img/badges/godot.png"},
    "unity": { name: "Unity", color:"background-color : white", icon: "img/badges/unity.png"},
    "gamejam": { name: "Game Jam!", color:"background-color : yellow", icon: "img/badges/gamejam.webp"},
    "vue": { name: "Vue", color:"background-color : white", icon: "img/badges/vue.png"},
    "nuxt": { name: "Nuxt", color:"background-color : white", icon: "img/badges/nuxt.svg"},
    "my-linkedin": { name: "Tom Howarth", color:"background-color : white", icon: "https://upload.wikimedia.org/wikipedia/commons/thumb/c/ca/LinkedIn_logo_initials.png/960px-LinkedIn_logo_initials.png"},
    "my-email": { name: "tomhowarth23@gmail.com", color:"background-color : white", icon: "https://static-00.iconduck.com/assets.00/email-circle-fill-icon-2048x2048-pa63yusl.png"},
    "airtable": { name: "Airtable", color:"background-color : white", icon: "img/badges/airtable.svg"},
    "threejs": { name: "Three.js", color:"background-color : white", icon: "img/badges/three.png"},
    "steam": { name: "Steam API", color:"background-color : white", icon: "img/badges/steam.png"},
    "prototype":{name: "Prototype", color:"background-color : CornflowerBlue", icon:"img/badges/prototype.png"},
    "rust":{name: "Rust", color:"background-color : White", icon:"img/badges/rust.png"},
  };

  // i wanna add some sort of data here, likely a dictionary, that matches a string to a Display name, Icon and Color for a badge
  // match the given id to the dictionary, then load its values into the html

</script>

<style scoped>
  .badge{
    display: flex;
    flex-direction: row;
    background-color: rgb(255, 255, 255);
    color: black;
    border-radius: 10px;
    align-items: center;
    padding: 5px;
    gap: 5px;
    
  }

  .icon{
    width: 20px;
    height: 20px;
  }

  .text{
    margin: 0;
    font-size: 14px;
  }
</style>