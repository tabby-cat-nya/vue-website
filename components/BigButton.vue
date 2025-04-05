<template>
  <a class="big-button" :href="props.href">
    <h2>{{props.text}}</h2>
  </a>
</template>

<script lang="ts" setup>
  const props = defineProps({
    href: String,
    text: String
  });
</script>

<style>
  .big-button{
    background-color: var(--accent);
    color: black;
    width: 80%;
    text-decoration: none;
    
  }

  h2{
    margin: 0;
    text-align: center;
    
  }
</style>