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
      <!-- <a href="javascript:window.history.back();"><-- Go Back</a> -->
      <BigButton text="<<< Return to blog listing" href="/blog-index"/>
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
  
<style scoped>
  .post{
    width: 50%;
    
  }

  /* i wonder if this will cause issues */
  img{ 
    width: 100%;
    
  }

  @media (max-width: 1000px){
    .post{
      width: 80%;
    }

    img{
      width: 100%;
    }
  }

  main {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 2rem;
    margin-top: 3.5rem;
    /* gap: 2rem; */
  }

</style>