<!-- <script>
  export default {
    async asyncData({ $content, params }) {
      const post = await $content('blog', params.slug).fetch()

      return { post }
    }
  }
</script> -->

<template>
    <main>
      <a href="/"><-- Return Home</a>
      <ContentDoc v-slot="{ doc }">
        <article class="post">
          <h1>{{ doc.title }}</h1>
          <p>Date Posted: {{ doc.date }}</p>
          <hr/>
          <ContentRenderer :value="doc" />
        </article>
      </ContentDoc> 
    </main>
    
    
    <!-- <main>
      <ContentSlot :use="$slots.title" unwrap="p" />
      <ContentDoc />
    </main> -->
</template>
  
<style>
  .post{
    width: 80%;
  }

</style>