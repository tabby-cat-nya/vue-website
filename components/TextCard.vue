<script setup>
const props = defineProps({
  href: String,
  heading: String,
  description: String
});
</script>

<template>
    <a class="text-container" :href="props.href">
        
        <div class="text-content">
            <h2>{{props.heading}}</h2>
            <p>{{props.description}}</p>
        </div>
    </a>
    
</template>

<style>
    .text-container{
        position: relative;
        text-align: center;
        margin: 10px;
        border-radius: 5px;
        overflow: hidden;
        color: white;
        background-color: rgb(62, 0, 104);
        width: 300px;
        height: 200px
        
    }

    .text-content{
        position: absolute;
        bottom: 8px;
        left: 16px;
        text-align: left ;
        
    }

    .text-image{
        filter: brightness(100%) blur(0px);
        /* filter: blur(2px); */
    }
    .text-content{
            visibility:visible;
    }

    .text-container:hover{
        background-color: var(--accent-dark);
        .text-content{
            visibility:visible;
        }
        
    }
</style>