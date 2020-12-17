<template>
    <div class="deleteBtn" @click="deleteInput(index)">
        &times;
    </div>
</template>

<script>
export default {
    name: 'DeleteButton',
    props: ['index'],
    methods: {
        deleteInput(index){
            this.$emit('deleteInput', index)
        }
    }
}
</script>

<style scoped>
  .deleteBtn {
      position: relative;
      left: -28px;
      top: -5px;      
      width: 30px;
      height: 30px;
      align-self: start;
      background-color: red;
      border-radius: 20%;
      color: #fff;
      font-size: 1.5em;
      margin-left: 0;
      cursor: pointer;
  }
</style>