<template>
  <div>
    <!-- <button @click="$emit('close')"> Close </button> -->
    <img src="/public\img\close.png" class="close-button" @click="$emit('close')">    
    <h2>{{title}}</h2>
    <p>{{description}}</p>
    
    <br>
    <!-- <ClientOnly> -->
      <div class="badges-container">
        <Badge v-for="(data, i) of badges" :key="i" :id="data" />
      </div>
      <div class="buttons">
          <SmallButton v-for="(data, i) of buttons" :key="i" class="button" :text="data.text"
              :href="data.link" />
      </div>
    <!-- </ClientOnly> -->
    <br>
    <p class="multiline-css-fix">{{longDescription}}</p>
        
  </div>
</template>

<script lang="ts" setup>
import {defineProps, defineEmits} from 'vue'
import type { BadgeData } from './ProjectCardV2.vue';

export interface ButtonData {
    text: string,
    link: string,
}

const props = defineProps<{
    title: string,
    description: string,
    longDescription?: string,
    buttons?: Array<ButtonData>,
    badges?: Array<string>,
}>();

defineEmits("close")
</script>

<style scoped>

.close-button{
  float:right;
  /* display: block; */
  /* margin-left: auto; */
  width: 32px;

  &:hover{
    filter: invert();
  }
}

.multiline-css-fix{
  white-space: pre-wrap;
}

.badges-container{
  display:  flex;
  flex-direction: row;
  gap: 5px;
  flex-wrap: wrap;
  margin-bottom: 10px;
}

</style>