<template>
    <div>
        <div>Child Component</div>
    </div>
</template>

<script>
    export default {
        name: "ChildComponent",
        beforeCreate() {
            console.log('ChildComponent beforeCreate ()');
        },
        created() {
            console.log('ChildComponent created ()');
        },
        beforeMount() {
            console.log('ChildComponent beforeMount ()');
        },
        mounted() {
            console.log('ChildComponent mounted ()');
        },
        beforeUpdate() {
            console.log('ChildComponent beforeUpdate ()');
        },
        updated() {
            console.log('ChildComponent updated ()');
        },
    }
</script>

<style>

</style>