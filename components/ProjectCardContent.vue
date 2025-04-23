<template>
  <div>
    <!-- <button @click="$emit('close')"> Close </button> -->
    <img src="public\img\close.png" class="close-button" @click="$emit('close')">    
    <h2>{{title}}</h2>
    <p>{{description}}</p>
    
    <br>
    <!-- <ClientOnly> -->
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

export interface ButtonData {
    text: string,
    link: string,
}

const props = defineProps<{
    title: string,
    description: string,
    longDescription?: string,
    buttons?: Array<ButtonData>,
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

</style>