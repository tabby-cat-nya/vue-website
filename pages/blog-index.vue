<template>
  <main>
    <a href="/"><-- Return Home</a>
    <h1>Tom's Blog</h1>
    

    <TextCard v-for="post in data"
        :key="post.id"
        :href="post._path"
        :heading="post.title"
        :subheading="post.date"
        :description="post.description"
        :id="post.id"
      />

    

  </main>
</template>

<script lang="ts" setup>
  var { data } = await useAsyncData('home', () => queryContent('blog').sort({id:-1}).find())
</script>

<style>
  main {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 2rem;
    margin-top: 3.5rem;
    gap: 2rem;
  }
</style>