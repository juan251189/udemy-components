<template>
  <div id="Udetails" >

    <h3 >User Details</h3>
    <p>{{switchName()}}</p>
    {{age}}
    <button @click="resetName">ResetName</button>
    <button @click="resetNamefn()"> Reset Name Call Back</button>





  </div>
</template>

<script>
import { eventBus } from "../main";
  export default{
    name:'user-details',
    props:{
      name:String,
      resetNamefn:Function,
      age:Number
    },
    data(){
      return{

      }
    },
    methods: {
      switchName() {
        return this.name.split("").reverse().join("");

      },
      resetName(){

        var newName= 'Max';
        this.$emit('nameWasReset',newName);
      }
    },
    created() {
      //do something after creating vue instance
      eventBus.$on('ageWasEdited',(data) =>{
        this.age=data;
      })
    }

  }
</script>

<style scoped>
div{
  background: #66f07c;
  height: 150px;
  border: 1px solid;


}

</style>
