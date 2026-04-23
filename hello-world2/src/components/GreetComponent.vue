<template>
    <div>
        <h2>hello {{ name }} a.k.a {{ heroName }}</h2>
    </div>
</template>

<script>
    export default {
        name: 'GreetComponent',
        props: ['name', 'heroName'],
    }
</script>

<style scoped>

</style>