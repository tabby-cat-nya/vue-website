<template>
  <main>
    <a href="/"><-- Return Home</a>
    <h1>Tom's Blog</h1>
    
    <p>Tag Search: 
      <a v-if="qSupplied" href="blog-index">Clear Search</a> - 
      <a href="blog-index?tag=Programming">Programming</a> - 
      <a href="blog-index?tag=GameDev">Game Dev</a> - 
      <a href="blog-index?tag=Queer">Queer Stuff</a>
    </p>

    <TextCard v-for="post in data"
        :key="post.id"
        :href="post._path"
        :heading="post.title"
        :subheading="post.date"
        :description="post.description"
        :id="post.id"
        :tags="post.tags"
      />

    

  </main>
</template>

<script lang="ts" setup>
  // const route = useRoute()
  // const { data: tagSearch } = await useFetch(`/api/mountains/${route.params.slug}`)
  var query : string = String(useRoute().query.tag)
  var qSupplied : boolean = false
  console.log (query == 'undefined')
  if (query == 'undefined'){
    query = ''
    console.log('no tag supplied')
  }
  else{
    console.log('tag successful')
    qSupplied = true
  }
  var { data } = await useAsyncData('home', () => queryContent('blog').where({ tags: { $contains: query } }).sort({id:-1}).find())
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