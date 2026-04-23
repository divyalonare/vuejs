<template>
    <div>
        <h2> Demo Two Component {{ state.firstName }} {{ state.lastName }}</h2>
        <h2>{{ state.firstName }} {{ state.lastName }}</h2>
    </div>
</template>

<script>
    import { reactive } from 'vue';
    export default {
        name: 'DemoTwoComponent',
        setup () {
            // Composition API logic can be added here
            const state = reactive({
                firstName: 'Demo',
                lastName: 'Two',
            })
            return {
                // Return reactive references or computed properties here
                state,
            };
        },
        data() {
            return {
               firstName: this.state.firstName,
               lastName: this.state.lastName,
            }
        }
    }
</script>

<style>

</style>