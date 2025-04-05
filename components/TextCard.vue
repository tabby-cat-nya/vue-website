<script setup>
const props = defineProps({
  href: String,
  heading: String,
  description: String,
  subheading: String,
  id: Number,
  tags: String
});
</script>

<template>
    <a class="text-container" :href="props.href">
        
        <div class="text-content">
            <h2 class="heading"> {{props.heading}}</h2>
            <p v-if="tags===''" class="subheading">{{props.subheading}} - #{{ props.id }}</p>
            <p v-else class="subheading">{{props.subheading}} - #{{ props.id }} - {{ props.tags }}</p>
            <p>{{props.description}}</p>
        </div>
    </a>
    
</template>

<style scoped>
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

    .subheading{
        color: grey;
        margin: 0;
        font-size: small;
    }

    .heading{
        margin: 0;
    }
</style>