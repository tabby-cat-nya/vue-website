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
    "godot4": { name: "Godot 4", color:"background-color : white", icon: "https://upload.wikimedia.org/wikipedia/commons/thumb/6/6a/Godot_icon.svg/2048px-Godot_icon.svg.png"},
    "unity": { name: "Unity", color:"background-color : white", icon: "https://static-00.iconduck.com/assets.00/unity-icon-999x1024-kgzo1ar1.png"},
    "gamejam": { name: "Game Jam!", color:"background-color : yellow", icon: "https://static-00.iconduck.com/assets.00/timer-icon-512x512-vrl212i7.png"},
    "vue": { name: "Vue", color:"background-color : white", icon: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSvsXyz8eDobC4MvaRkM3zmOZ9ETdrS0ozGCQ&s"},
    "nuxt": { name: "Nuxt", color:"background-color : white", icon: "https://nuxt.com/assets/design-kit/icon-green.svg"},
    "my-linkedin": { name: "Tom Howarth", color:"background-color : white", icon: "https://upload.wikimedia.org/wikipedia/commons/thumb/c/ca/LinkedIn_logo_initials.png/960px-LinkedIn_logo_initials.png"},
    "my-email": { name: "tomhowarth23@gmail.com", color:"background-color : white", icon: "https://static-00.iconduck.com/assets.00/email-circle-fill-icon-2048x2048-pa63yusl.png"},
    "airtable": { name: "Airtable", color:"background-color : white", icon: "https://www.svgrepo.com/show/353383/airtable.svg"},
    "threejs": { name: "Three.js", color:"background-color : white", icon: "https://canada1.discourse-cdn.com/flex035/uploads/threejs/optimized/2X/e/e4f86d2200d2d35c30f7b1494e96b9595ebc2751_2_1016x1024.png"},
    "steam": { name: "Steam API", color:"background-color : white", icon: "https://upload.wikimedia.org/wikipedia/commons/thumb/8/83/Steam_icon_logo.svg/2048px-Steam_icon_logo.svg.png"},
    "prototype":{name: "Prototype", color:"background-color : CornflowerBlue", icon:"https://cdn-icons-png.flaticon.com/512/6941/6941302.png"},
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