<template>
    <div>
        <h2>Provide Inject Component {{ Name }}</h2>
        <h2>Provide Inject Count {{ count }}</h2>
        <h2>Provide Inject hero {{ firstname}} {{ lastname }}</h2>
        <button @click="incrementCount">Increment Count</button>

        <ChildAComponent />
    </div>
</template>

<script>
    // eslint-disable-next-line no-unused-vars 
    import { provide, ref, reactive, toRefs } from 'vue';
    import ChildAComponent from './ChildAComponent.vue';
    export default {
        components: {
            ChildAComponent,
        },
        name: 'ProvideInjectComponent',
        setup() {
           provide('c_userName', 'Disha');

           const count = ref(0);
           function incrementCount() {
               count.value++;
           }
           const state = reactive({
               firstname: 'bruce',
                lastname: 'wayne',
           });

           provide('c_count', count);
           provide('c_hero', state);
           provide('incrementCount', incrementCount);

           return {
               ...toRefs(state),
                count,
                incrementCount,
           }
        },
        data() {
            return {
                Name: 'Divya',
            }
        },
        provide() {
            return {
                userName: this.Name,
            }
        },
    }
</script>

<style>

</style>