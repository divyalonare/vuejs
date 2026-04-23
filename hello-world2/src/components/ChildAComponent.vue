<template>
    <div>
        <h2>Child A Component</h2>
        <ChildBComponent />
    </div>
</template>

<script>
    import ChildBComponent from './ChildBComponent.vue';
    export default {
        name: 'ChildAComponent',
        components: {
            ChildBComponent,
        },
    }
</script>

<style>

</style>