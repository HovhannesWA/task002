<template>
  <div class="all_input_container">
    <div class="input_container">      
      <input type="text"/>      
    </div>  
  </div>  
</template>

<script>
export default {
  name: "InputComponent"  
};
</script>

<style scoped>

.input_container {
  display: flex;
  justify-items: flex-end;
  align-items: center;
}

input {
  display: block;
  width: 90%;
  margin: 20px 0 20px auto;
  height: 40px;
  border: 2px solid #00BFFF;
  color: #00BFFF;
  font-size: 1.5em;
  text-align: center;
}

input:focus {
    outline: none;
    border: 2px solid gold;    
}
</style>