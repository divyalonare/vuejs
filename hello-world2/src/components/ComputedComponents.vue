<template>
    <div>
        <input type="text" v-model="fname" placeholder="First Name"/><br>
        <input type="text" v-model="lname" placeholder="Last Name"/>
        <h2>Computed Component: {{ fullName }}</h2>

        <input type="text" v-model="refFirstName" placeholder="First Name"/><br>
        <input type="text" v-model="refLastName" placeholder="Last Name"/>
        <h2>Computed Ref Component: {{ refFullName }}</h2>

        <input type="text" v-model="reactiveFirstName" placeholder="First Name"/><br>
        <input type="text" v-model="reactiveLastName" placeholder="Last Name"/>
        <h2>Reactive Ref Component: {{ reactiveFullName }}</h2>
    </div>
</template>

<script>
    // eslint-disable-next-line no-unused-vars 
    import {ref,computed, reactive, toRefs} from 'vue';
    export default {
        name:'ComputedComponents',
        setup(){
            const refFirstName = ref('');
            const refLastName = ref('');

            const refFullName = computed(function(){
                return `${refFirstName.value} ${refLastName.value}`;
            });

            const state = reactive({
                reactiveFirstName:'',
                reactiveLastName:''
            });

            const reactiveFullName = computed(function(){
                return `${state.reactiveFirstName} ${state.reactiveLastName}`;
            });

            return {refFirstName, refLastName, refFullName,...toRefs(state), reactiveFullName};
        },
        data(){
            return{
                fname:'',
                lname:'',
            }
        },
        computed:{
            fullName(){
                return `${this.fname} ${this.lname}`;
            }
        }   
    }
</script>

<style>

</style>