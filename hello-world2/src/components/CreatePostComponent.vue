<template>
    <div>
        <form @submit.prevent="createPost">
            <div>
                <label for="userId">User ID:</label>
                <input type="text" id="userId" v-model="formData.userId">
            </div>
            <br>
            <div>
                <label for="title">Title:</label>
                <input type="text" id="title" v-model="formData.title">
            </div>
            <br>
            <div>
                <label for="body">Body:</label>
                <textarea id="body" v-model="formData.body"></textarea>
            </div>
            <br>
            <button>Create Post</button>
        </form>
    </div>
</template>

<script>
    import axios from 'axios';
    export default {
        name: "CreatePostComponent",
        data() {
            return {
                formData :{
                    userId: '',
                    title: '',
                    body: ''
                }
            }
        },
        methods: {
            createPost(){
                axios.post('https://jsonplaceholder.typicode.com/posts', this.formData)
                .then(response => console.log(response))
                .catch(error => console.log(error));
            }
        }
    }
</script>

<style>

</style>