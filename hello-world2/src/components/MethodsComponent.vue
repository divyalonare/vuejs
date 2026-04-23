<template>
    <div>
        <h2> {{ name }} </h2>
        <button @click="setName">Update Name</button>

        <h2>Count: {{ count }}</h2>
        <button @click="incrementCount">Increment Count</button>

        <h2>First Name: {{ first }} , last Name: {{ last }}</h2>
        <button @click="changeName">Change Name</button>
        

    </div>
</template>

<script>
    import {ref,reactive,toRefs} from 'vue';
    export default {
        name:'MethodsComponent',
        setup(){
            const count = ref(0);
            const state = reactive({
                first:'divya',
                last:'lonare'
            })

            function incrementCount(){
                count.value++;
            }

            function changeName(){
                state.first = 'Updated First Name';
                state.last = 'Updated Last Name';
            }

            return {count, incrementCount,...toRefs(state), changeName};
        },
        data() {
            return {
                name: 'Methods Component',
            }
        },
        methods:{
            setName(){
                this.name = 'Updated Methods Component';
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>