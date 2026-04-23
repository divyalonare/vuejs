<template>
    <div>
        parent Component
        <button @click="showChild = !showChild">Toggle Child Component</button>
        <ChildComponent v-if="showChild" />
    </div>
</template>

<script>
    import ChildComponent from './ChildComponent.vue';
    export default {
        components: {
            ChildComponent
        },
        name: 'ParentComponent',
        data() {
            return {
                showChild: true,
            }
        },
        beforeCreate() {
            console.log('ParentComponent beforeCreate ()');
        },
        created() {
            console.log('ParentComponent created ()');
        },
        beforeMount() {
            console.log('ParentComponent beforeMount ()');
        },
        mounted() {
            console.log('ParentComponent mounted ()');
        },
        beforeUpdate() {
            console.log('ParentComponent beforeUpdate ()');
        },
        updated() {
            console.log('ParentComponent updated ()');
        },
        beforeUnmount() {
            console.log('ParentComponent beforeUnmount ()');
        },

    }
</script>

<style lang="scss" scoped>

</style>