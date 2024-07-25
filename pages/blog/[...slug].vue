<script>
  export default {
    async asyncData({ $content, params }) {
      const post = await $content('blog', params.slug).fetch()

      return { post }
    }
  }
</script>

<template>
    <main>
      <ContentDoc />
    </main>
  </template>
  