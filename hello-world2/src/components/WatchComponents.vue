<template>
    <div>
        <input type="text" v-model="name" placeholder="Enter your name" /><br>

        <input type="text" v-model="firstname" placeholder="Enter your first name" /><br>
        <input type="text" v-model="lastname" placeholder="Enter your last name" /><br><br>

        <input type="text" v-model="fname" placeholder="Enter your reactive first name" /><br>
        <input type="text" v-model="lname" placeholder="Enter your reactive last name" />
    </div>
</template>

<script>
    // eslint-disable-next-line no-unused-vars
    import {ref, watch, reactive, toRefs} from 'vue';
    export default {
        name:'WatchComponents',
        setup(){

            const state = reactive({
                fname: '',
                lname: ''
            });

            watch(() => {
                return{...state}
            },  function(newVal, oldVal){
                console.log('Reactive First name changed from', oldVal.fname,) 
                console.log('to', newVal.fname);
                console.log('Reactive Last name changed from', oldVal.lname,) 
                console.log('to', newVal.lname);
            }),
            { immediate: true }

            const firstname = ref('');
            const lastname = ref('siris');

            watch([firstname, lastname], (newVal, oldVal) => {
                console.log('First name changed from', oldVal[0],) 
                console.log('to', newVal[0]);
                console.log('Last name changed from', oldVal[1],) 
                console.log('to', newVal[1]);
            }, 
            { immediate: true }
        )

            return {firstname, lastname,...toRefs(state)};
        },
        data(){
            return{
                name:'',
            }
        },
        watch:{
            name(newVal, oldVal){
                console.log('Name changed from', oldVal,) 
                console.log('to', newVal);
            },
        },
    }
</script>

<style>

</style>