<template>
    <div>
        <h2>This is Component C</h2>
        <ComponentE />
    </div>
</template>

<script>
    import ComponentE from './ComponentE.vue'
export default {
    name:'ComponentC',
    components: {
        ComponentE,
    },
}
</script>

<style>

</style>