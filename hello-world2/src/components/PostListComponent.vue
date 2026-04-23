<template>
    <div>
        <button @click="getPosts">Load Posts</button>
        <p v-if="errorMsg">{{ errorMsg }}</p>
        <div v-for="post in posts" :key="post.id">
            <h2>{{post.id}} {{ post.title }}</h2>
            <h2>{{ post.body }}</h2>
            <hr />
        </div>
    </div>
</template>

<script>
    // eslint-disable-next-line no-unused-vars 
        import axios from 'axios';  
        export default {
        name: 'PostListComponent',
        //created() {
           // this.getPosts();
        //},
        data() {
            return {
                posts: [],
                errorMsg: ''
            }
        },
        methods: {
            getPosts() {
                axios.get('https://jsonplaceholder.typicode.com/posts')
                .then((response) => {
                    console.log(response.data)
                    this.posts = response.data;
                })
                .catch(error => {
                    console.log(error);
                    this.errorMsg = 'Error retrieving posts'
                });
            }
        }
    }
</script>

<style>

</style>