<template>
    <div>
        <input type="text" ref="inputRef" />
        <PostListComponent ref="postListRef" />
    </div>
</template>

<script>
    // eslint-disable-next-line no-unused-vars 
    import PostListComponent from './PostListComponent.vue';
    export default {
    name: 'TemplateRefComponent',
    components: {
        PostListComponent,
    },
    mounted() {
  console.log('PostList ref:', this.$refs.postListRef);  
  this.$refs.inputRef.focus();
}
}
</script>

<style >

</style>