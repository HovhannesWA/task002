<template>
    <div class="main">
        <div class="input_container"  v-for="(item, index) in radioButtonsValues" :key="item.key">
            <RadioButton :value="item.value" :name="radioButtonsName" />
            <InputComponent/>
            <DeleteButton :index="index" @deleteInput="deleteInputHundler"/>            
        </div>
        <p class='emptyMessage' v-show="!radioButtonsValues.length">Click plus button to add input fields</p>
        <div class="addNewInput" @click="addNewinput">+</div>    
    </div>
</template>


<script>
import RadioButton from './RadioButton'
import InputComponent from './InputComponent'
import DeleteButton from './DeleteButton'

export default {
    name: 'Container',
    components: {
        InputComponent,
        RadioButton,
        DeleteButton        
    },

    data: () => {        
        return {
            radioButtonsName: 'myradioButton',
            forUniqueId: Date.now(),
            radioButtonsValues: [{
                value: 10,
                key: 1
            },{
                value: 20,
                key: 2
            },
            {
                value: 30,
                key: 3
            },
            {
                value: 40,
                key: 4
            }]            
        }        
  },

  methods: {
      addNewinput(){
          let newInput = {
              value: Math.floor(Math.random() * 100 ),
              key: this.forUniqueId
          }
          this.radioButtonsValues.push(newInput)                  
      },
      deleteInputHundler(index){        
        //   this.radioButtonsValues.splice(index, 1)
          this.$delete(this.radioButtonsValues, index)           
      }
  },
  beforeUpdate(){
      this.forUniqueId = Date.now()
      for(let i in this.radioButtonsValues){
          console.log(this.radioButtonsValues[i].key)
      }
  }
}
</script>

<style scoped>
  .main {
      /* display: flex; */
      /* flex-direction: column; */
  }

  .input_container {
  display: grid;
  grid-template-columns: 1fr 10fr 1fr;
  justify-content: center;
  align-items: center;
}

.addNewInput {
    display: flex;
    justify-content: center;
    align-items: center;
    margin: auto 25px auto auto;    
    border-radius: 100%;
    color: white;
    font-size: 2em;
    /* background-color: #20dbeb; */
    background: linear-gradient(#20dbeb, #26c7fe);
    width: 50px;
    height: 50px;
    cursor: pointer;
}

.emptyMessage {
    color: red;
    font-size: 2em;;
}
</style>