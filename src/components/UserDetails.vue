<template>
  <div id="Udetails" >

    <h3 >User Details</h3>
    <p>{{name}}</p>
  </div>
</template>

<script>
  export default{
    name:'user-details',
    props:['name'],
    data(){
      return{

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
