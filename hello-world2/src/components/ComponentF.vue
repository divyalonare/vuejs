<template>
    <div>
        <h2>This is Component F</h2>
        <h2>Injected Username: {{ username }}</h2>
    </div>
</template>

<script>
    export default {
        name: 'ComponentF',
        inject: ['username'],
    }
</script>

<style scoped>

</style>