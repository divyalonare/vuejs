<template>
  <div>
    <h2>This is an article component</h2>
    <h2>{{ title }}</h2>
    <h2>Likes: {{ likes }}</h2>
    <h2>Published: {{ isPublished ? 'Yes' : 'No' }}</h2>
  </div>
</template>

<script>
export default {
    name:'ArticleComponent',
    props: {
      title: {
        type: String,
        required: true,
      },
      likes: Number,
      isPublished: Boolean,
    }
}
</script>

<style>

</style>