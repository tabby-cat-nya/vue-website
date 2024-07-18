<script setup>
const props = defineProps({
  src: String,
  href: String,
});
</script>

<template>
  <a :href="props.href" class="icon2">
    <img :src="props.src" class="icon" />
  </a>
</template>

<style scoped>
.icon {
  width: 48px;
  
}

.icon2{
  width: 48px;
  
}
</style>