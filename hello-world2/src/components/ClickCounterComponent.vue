<template>
  <div>
    <button @click="incrementCount">
      Clicked {{ count }} times
    </button>
  </div>
</template>


<script>
    // eslint-disable-next-line no-unused-vars 
    import Counter from '@/mixins/Counter';
    export default {
        name: 'ClickCounterComponent',
        mixins: [Counter],
    }
</script>

<style>

</style>