<template>
  <div class="top" v-if="url.hostname=='www.clevertop.dev'">
  <!-- <div class="top" > -->
    <p><b>Warning!</b> my old domain clevertop.dev (which you're currently visiting from!), is expiring on <b>June 19</b>, to access my site, please use <a href="https://tabbycat.dev">tabbycat.dev</a></p>
  </div>
</template>

<script lang="ts" setup>
  const url = useRequestURL()
  console.log('host name', url.hostname)
</script>

<style scoped>

.top{
  background-color: rgb(255, 92, 92);
  color: black;
  width: 100%;
  padding: 5px;
  text-align: center;
  /* min-height: 100px; */
}

p{
  margin: 0;
}

a{
  color: blueviolet;
}

</style>