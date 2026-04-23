<template>
    <div>
        <h2>This is Component E</h2>
        <ComponentF />
    </div>
</template>

<script>
import ComponentF from './ComponentF.vue'
export default {
    name:'ComponentE',
    components: {
        ComponentF,
    },
}
</script>

<style>

</style>