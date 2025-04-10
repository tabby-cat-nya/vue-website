<template>
  <main>
    <!-- <a href="/"><-- Return Home</a> -->
    <BigButton text="<<< Return Home" href="/"/>
    <h1 class="no-margin">Tom's Blog</h1>
    
    <p class="no-margin" v-if="qSupplied">Selected Tag: <strong>{{query}}</strong> <a v-if="qSupplied" href="blog-index">(Clear Search)</a></p>
    <p class="no-margin">Tag Search:
      <a href="blog-index?tag=Programming">Programming</a> - 
      <a href="blog-index?tag=Godot">Godot</a> - 
      <a href="blog-index?tag=Tech">Tech</a> - 
      <a href="blog-index?tag=Queerness">Queerness</a>
      <!-- <a class="no-posts" href="blog-index?tag=Mental Health">Mental Health</a> -->
    </p>

    <hr>
    <div>
      <BlogCard v-for="post in data" class="posts-list"
          :key="post.id"
          :href="post._path"
          :heading="post.title"
          :subheading="post.date"
          :description="post.description"
          :id="post.id"
          :tags="post.tags"
        />
    </div>
    

  </main>
</template>

<script lang="ts" setup>
  useSeoMeta({
    title: "Blog",
    ogTitle: "Blog",
    description: "I write about random things sometimes",
    ogDescription: "I write about random things sometimes",
  });
  // const route = useRoute()
  // const { data: tagSearch } = await useFetch(`/api/mountains/${route.params.slug}`)
  var query : string = String(useRoute().query.tag)
  var qSupplied : boolean = false
  // console.log (query == 'undefined')
  if (query == 'undefined'){
    query = ''
    // console.log('no tag supplied')
  }
  else{
    // console.log('tag successful')
    qSupplied = true
  }
  var { data } = await useAsyncData('home', () => queryContent('blog').where({ tags: { $contains: query },hidden: {$not : true}},).sort({id:-1}).find())
</script>

<style scoped>
  main {
    /* display: flex; */
    /* flex-direction: column; */
    /* align-items: center; */
    padding: 2rem;
    margin-top: 3.5rem;
    /* gap: 0rem; */
    /* width: 80%; */
    
  }
  
  .posts-list{
    width: 80%;
    display: block;
    margin-left: auto;
    margin-right: auto;
  }



  .no-margin{
    margin: 0;
    text-align: center;
  }

  .no-posts{
    color: gray;
  }
</style>