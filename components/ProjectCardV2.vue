<template>
  <div class="top-level">
    <!-- <button @click="isOpen=true">Open</button> -->
    <!-- Project Card -->
    <div @click="isOpen=true" class="card">
      <!-- <div class="project-image"></div> -->
      <img class="project-image" :src="props.src">
      <div class="content">
          <h2>{{props.title}}</h2>
          <p>{{props.description}}</p>
          <div class="badges-container">
            <!-- <Badge text="Godot" icon="https://upload.wikimedia.org/wikipedia/commons/thumb/6/6a/Godot_icon.svg/2048px-Godot_icon.svg.png" />
            <Badge text="Badge2" icon="https://upload.wikimedia.org/wikipedia/commons/thumb/6/6a/Godot_icon.svg/2048px-Godot_icon.svg.png" />
            <Badge text="Badge3" icon="https://upload.wikimedia.org/wikipedia/commons/thumb/6/6a/Godot_icon.svg/2048px-Godot_icon.svg.png" /> -->
            <Badge v-for="(data, i) of badges" :key="i" :id="data" />
          </div>
      </div>
    </div>
    
    <!-- Popup Modal -->
    <Teleport to="body">
      <div class="modal" v-if="isOpen">
        <div>
          <ProjectCardContent
            @close="isOpen = false"
            :title=props.title
            :description=props.description
            :long-description=props.longDescription
            :buttons=props.buttons
            :badges=props.badges
          />
        </div>
      </div>
    </Teleport> 
  </div>
</template>

<script lang="ts" setup>

import {ref, defineProps} from 'vue'
import ProjectCardContent from './ProjectCardContent.vue';
const isOpen = ref(false)

export interface ButtonData {
    text: string,
    link: string,
}

export interface BadgeData {
  text: string,
  icon: string,
}

const props = defineProps<{
    title: string,
    description: string,
    longDescription?: string,
    src: string,
    buttons?: Array<ButtonData>,
    badges?: Array<string>, //just the id's
}>();


</script>

<style scoped>
.root{
  position:relative
}

.top-level{
  margin-right: 10px;
  margin-bottom: 5px;
}

.card{
  position: relative;
  text-align: center;
  overflow: hidden;
  border-color: var(--accent);
  border-width: 3px;
  border-style: solid;
  width: 100%;
  /* overflow: auto; */
  height: max-content;

  &:hover{
    border-color: white;
    cursor: pointer;
    
  }
}

.project-image{
  width: 100%;
  /* height: 100px; */
  object-fit: cover;
  background-color: aqua;
  margin-bottom: -7px;
}

.content{
  position: absolute;
  bottom: 8px;
  left: 16px;
  text-align: left ;
  visibility:hidden;
  /* font-size: 14px; */
  margin-right: 10px;

  /* &:hover{
    visibility: visible;
  } */

}


.card>img:hover{
  /* filter: brightness(40%) blur(2px); */

  
}

.card:hover, .content:hover{

  border-color: white;
  cursor: pointer;
  
  
}

@media (min-width: 1000px){
  .card:hover, .content:hover{
  .content{
    visibility: visible;
  }

  .project-image{
    filter: brightness(40%) blur(2px);
  }
  }
}


.modal {
  position: fixed;
  top: 0;
  left: 0;
  z-index: 100;
  background-color: rgba(0,0,0,0.1);
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal > div{
  background-color: rgb(53, 53, 53);
  padding: 50px;
  border-radius: 10px;
  margin: 10%;
  max-height: calc(100vh - 210px);
  overflow-y: auto;
}

.badges-container{
  display:  flex;
  flex-direction: row;
  gap: 5px;
  flex-wrap: wrap;
}
</style>