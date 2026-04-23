<template>
  <div>
    <div @mouseenter="incrementCount" @mouseleave="resetCount">
      <h2>Hovered {{ count }} times</h2>
    </div>
  </div>
</template>


<script>
    // eslint-disable-next-line no-unused-vars 
    import Counter from '@/mixins/Counter';
    export default {
        name: 'HoverCounterComponent',
        mixins: [Counter],
    }
</script>

<style>

</style>