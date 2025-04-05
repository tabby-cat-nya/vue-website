<template>
  <div class="button-box">
    <a class="big-button" :href="props.href">
      <h2>{{props.text}}</h2>
    </a>
  </div>
</template>

<script lang="ts" setup>
  const props = defineProps({
    href: String,
    text: String
  });
</script>

<style scoped>
  .big-button{
    background-color: var(--accent);
    color: black;
    width: 80%;
    text-decoration: none;
    display: block;
    margin-left: auto;
    margin-right: auto;
    /* justify-self: center; */
    
  }

  .button-box{
    width: 100%;
    
  }

  h2{
    margin: 0;
    text-align: center;
    
  }
</style>