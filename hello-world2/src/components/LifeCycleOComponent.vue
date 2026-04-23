<template>
    <div>
        <h2>Options API Lifecycle Hooks</h2>
    </div>
</template>

<script>
    export default {
        name:'lifeCycleOComponent',
        beforeCreate() {
            console.log('LifeCycleOComponent - beforeCreate()');
        },
        created() {
            console.log('LifeCycleOComponent - created()');
        },
        beforeMount() {
            console.log('LifeCycleOComponent - beforeMount()');
        },
        mounted() {
            console.log('LifeCycleOComponent - mounted()');
        },
        beforeUpdate() {
            console.log('LifeCycleOComponent - beforeUpdate()');
        },
        updated() {
            console.log('LifeCycleOComponent - updated()');
        },
        beforeUnmounted() {
            console.log('LifeCycleOComponent - beforeUnmounted()');
        },
        unmounted() {
            console.log('LifeCycleOComponent - unmounted()');
        },
    }
</script>

<style lang="scss" scoped>

</style>