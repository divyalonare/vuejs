<template>
    <div>
        <h2>Child C Component </h2>
        <h2>Injected Name is: {{ userName }}</h2>
        <h2>Child C Composition username: {{ childuserName }}</h2>

        <h2>Child C Composition Count: {{ childCount }}</h2>
        <h2>Child C Composition Hero: {{ firstname }} {{ lastname }}</h2>

        <button @click="incrementCount">Increment Count from child</button>
    </div>
</template>

<script>
    // eslint-disable-next-line no-unused-vars 
    import { inject, toRefs } from 'vue';
    export default {
        name:'ChildCComponent',
        setup() {
            const childuserName = inject('c_userName','defaultName');
            const userName = inject('userName','defaultUser');
            const childCount = inject('c_count', 0);
            const childhero = inject('c_hero', {});
            const incrementCount = inject('incrementCount', () => {});

            return {
                userName,
                childuserName,
                childCount,
                ...toRefs(childhero),
                incrementCount,
            }
        },
    }
</script>

<style>

</style>