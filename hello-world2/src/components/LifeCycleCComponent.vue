<template>
    <div>

    </div>
</template>

<script>
    import { onMounted, onbeforeMount, onbeforeUpdate, onUpdated, onUnmounted } from 'vue';
    export default {
        name:'lifeCycleCComponent',
        setup() {
            onbeforeMount(() => {
                console.log('LifeCycleCComponent - onBeforeMount()');
            })
            onMounted(() => {
                console.log('LifeCycleCComponent - onMounted()');
            })
            onbeforeUpdate(() => {
                console.log('LifeCycleCComponent - onBeforeUpdate()');
            })
            onUpdated(() => {
                console.log('LifeCycleCComponent - onUpdated()');
            })
            onUnmounted(() => {
                console.log('LifeCycleCComponent - onUnmounted()');
            })
    }
    }
</script>

<style lang="scss" scoped>

</style>