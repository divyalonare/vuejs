<template>
    <div>
        <h2> Demo One Component {{ name }}</h2>
    </div>
</template>

<script>
    import { ref } from 'vue';
    export default {
        name: 'DemoOneComponent',
        setup () {
            // Composition API logic can be added here
            const name = ref('Divya');

            setTimeout(() => {
                name.value = 'Updated Divya';
                console.log('Name updated to:', name.value);
            },4000);
            return {
                // Return reactive references or computed properties here
                name,
            };
        },
    }
</script>

<style>

</style>