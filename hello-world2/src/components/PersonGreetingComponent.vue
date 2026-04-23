<template>
    <div>
        <h2>Hello, {{ fullname }}!</h2>
        <button @click="sendEvent">Call Heroes</button>
    </div>
</template>

<script>
    import { computed } from 'vue';
    export default {
        name:'PersonGreetingComponent',
        setup(props,context){
            const fullname = computed(() => {
                return `${props.firstName} ${props.lastName}`;
            });

            function sendEvent(){
                context.emit('callheroes', fullname.value);
            }

            return {
                fullname,
                sendEvent,
            }
        },
        props: ['firstName', 'lastName'],
        //computed: {
        //    fullname(){
        //        return`${this.firstName} ${this.lastName}`;
        //    }
        //},
    }
</script>

<style>

</style>