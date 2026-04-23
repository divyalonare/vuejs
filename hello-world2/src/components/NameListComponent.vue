<template>
    <div>
        <h3 v-for="name in names" :key="name.firstName">
            <slot :firstName="name.firstName" :lastName="name.lastName"></slot>
        </h3>
    </div>
</template>

<script>
    export default {
        name: "NameListComponent",
        data() {
            return {
                names:[
                    {
                        firstName: 'divya',
                        lastName: 'lonare'
                    },
                    {
                        firstName: 'disha',
                        lastName: 'patil'
                    },
                    {
                        firstName: 'priya',
                        lastName: 'shinde'
                    }
                ]
            }
        }
    }
</script>

<style scoped>

</style>