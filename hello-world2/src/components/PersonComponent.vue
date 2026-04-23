<template>
    <div>
        <div>
            <input type="text" v-model="firstName" placeholder="First Name" />
            <input type="text" v-model="lastName" placeholder="Last Name" />
        </div>
        <PersonGreetingComponent :firstName="firstName" :lastName="lastName" @callheroes="CallHeroes"/>
    </div>
</template>

<script>
    import { ref } from 'vue';
    import PersonGreetingComponent from './PersonGreetingComponent.vue';
    export default {
        name: 'PersonComponent',
        components: {
            PersonGreetingComponent,
        },
        setup(){
            const firstName = ref('');
            const lastName = ref('');

            function CallHeroes(hero){
                alert(`Calling ${hero}`);
            }

            return {
                firstName,
                lastName,
                CallHeroes,
            }
        }
    }
</script>

<style>

</style>