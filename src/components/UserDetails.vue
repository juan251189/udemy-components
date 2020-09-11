<template>
  <div id="Udetails" >

    <h3 >User Details</h3>
    <p>{{switchName()}}</p>
    <button @click="resetName">ResetName</button>
    <button @click="resetNamefn()"> Reset Name Call Back</button>
  </div>
</template>

<script>
  export default{
    name:'user-details',
    props:{
      name:String,
      resetNamefn:Function
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
