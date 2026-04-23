<template>
    <div>
        <h2>Child B Component</h2>
        <ChildCComponent />
    </div>
</template>

<script>
    import ChildCComponent from './ChildCComponent.vue';
    export default {
        name: 'ChildBComponent',
        components: {
            ChildCComponent,
        },
    }
</script>

<style>

</style>