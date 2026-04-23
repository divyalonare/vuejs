<template>
    <div >
        <div class="card">
        <div id="card-header">
          <slot name="header"></slot>
        </div>
        <div id="card-content">
          <slot>Default Card Content</slot>
        </div>
        <div id="card-footer">
          <slot name="footer"></slot>
        </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "CardComponent",
        
    }
</script>

<style scoped>

.card-container {                 
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 200px;
}

.card {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  transition: 0.3s;
  width: 40%;
  margin: 20px auto;     
  border-radius: 5px;
  padding: 20px;
  text-align: center;  
  
  &:hover {
    box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
  }
}
</style>