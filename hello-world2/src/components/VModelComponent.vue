<template>
    <div>
        <input type="text" placeholder="First Name" v-model="fname" /><br>
        <input type="text" placeholder="Last Name" v-model="lname" /><br><br>

        <input type="text" placeholder="reactive First Name" v-model="firstname" /><br>
        <input type="text" placeholder="reactive Last Name" v-model="lastname" /><br>
        <input type="text" placeholder="reactive Hero Name" v-model="heroName" /><br>
        
    </div>
</template>

<script>
    // eslint-disable-next-line no-unused-vars 
    import {ref, reactive, toRefs} from 'vue';
    export default {
        name:'VModelComponent',

        setup(){
            const heroName = ref('')
            const state = reactive({
                firstname: '',
                lastname: ''
            })

            return {heroName,...toRefs(state)};
        },

        data() {
            return {
                fname: '',
                lname: ''
            }
        },
    }
</script>

<style>

</style>