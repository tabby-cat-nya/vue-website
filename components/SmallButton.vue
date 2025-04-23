<script setup lang="ts">
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

<style scoped>
    .button {
        background-color: #8904aa; 
        border: none;
        color: white;
        padding: 5px;
        border-radius: 5px;
        text-align: center;
        text-decoration: none;
        display: inline-block;
        font-size: 16px;
        overflow: hidden;
        margin-right: 5px;
    }

    .button:hover{
        background-color: var(--accent); 
        color: black;
    }

    p{
        font-weight: 100;
        margin: 0;
    }
</style>