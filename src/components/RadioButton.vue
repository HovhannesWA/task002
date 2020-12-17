<template>
    <label class="rb_container" id='l'> 
        <input type="radio" :name="name" :value="value" class="rb">
        <span class="rb_span"></span>
    </label>
</template>

<script>
export default {
    name: 'RadioButton',
    props: ['value', 'name']    
}
</script>

<style scoped>

.rb_container {
    display: flex;
    border: 2px solid #00BFFF;
    border-radius: 100%;
    width: 40px;
    height: 40px;
}

.rb, .rb_span {
    display: none;
}

.rb:checked + .rb_span{
    display: block;
}

.rb_span {
    width: 30px;
    height: 30px;
    margin: auto  auto;
    background-color: #00BFFF;
    border-radius: 100%;
}


</style>