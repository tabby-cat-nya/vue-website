<script setup>
const props = defineProps({
  href: String,
  text: String
});
</script>

<template>
    <a class="button" :href="props.href">
        <p>{{ props.text }}</p>
    </a>

   
    
</template>

<style>
    .button {
        background-color: #3f0064; 
        border: none;
        color: white;
        padding: 8px;
        border-radius: 5px;
        text-align: center;
        text-decoration: none;
        display: inline-block;
        font-size: 25px;
        overflow: hidden;
    }

    .button:hover{
        background-color: #e17ff5; 
        color: black
    }

    p{
        font-weight: 100;
        margin: 0;
    }
</style>