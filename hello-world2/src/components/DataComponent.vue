<template>
    <div>
        <h2> Options - {{ o_firstName}}</h2>
        <h2>Options - {{ o_firstName }} {{ o_lastName }} A.K.K {{ o_heroname }}</h2>

        <h2>Composition - {{ c_firstName }}</h2>
        <h2>Composition - {{ greet }}</h2>

        <h2>Composition - {{ c_firstName }} {{ c_lastName }} A.K.A {{ c_heroname }}</h2>
        <h2>Composition - {{ greethero }}</h2>

        <h2>Reactive {{ state.firstName }} {{ state.lastName }} A.K.A {{ state.heroname }}</h2>
        <h2>Reactive - {{ reactiveGreet }}</h2>
    </div>
</template>

<script>
    // eslint-disable-next-line no-unused-vars
    import { ref,reactive,computed } from 'vue';
    export default {
        name: 'DataComponent',
        setup () {
            const c_firstName = ref('Jane');
            const c_lastName = ref('Smith');
            const c_heroname = ref('Wonder Woman');

            const greet =`Hello, ${c_firstName.value}!`;
            const greethero =`Hello, ${c_firstName.value} ${c_lastName.value} a.k.a ${c_heroname.value}!`;
            console.log('Composition First Name:', c_firstName.value);

            const state = reactive({
                firstName: 'bruce',
                lastName: 'wayne',
                heroname: 'batman',
            });

            const reactiveGreet =`Hello, ${state.c_firstName} ${state.c_lastName} a.k.a ${state.c_heroname}!`;

            return {
                c_firstName,
                c_lastName,
                c_heroname,
                greethero,
                greet,
                reactiveGreet,
                state,
            };
        },
        data() {
            return {
               o_firstName: 'John',
               o_lastName: 'Doe',
               o_heroname: 'Superman',
            }
        }
    }
</script>

<style>

</style>