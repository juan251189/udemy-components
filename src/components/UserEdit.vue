<template>
  <div id="UserEdit">
    <button @click="editAge">Edit Age</button>    {{age}}
    <br><hr>
    <span>this will only change age in the component edit age</span>
<div>
<button @click="editAgeChildComponent">Edit Age in user details too</button>
{{age}}
</div>
  </div>
</template>
<script>
export default {
  name: "user-edit",
  props:{
    age: Number
  },
  methods:{
    editAge:function(){
      this.age="31";

    },
    editAgeChildComponent:function(){
      this.age="31";
      this.$emit('ageWasChanged',this.age)
    }
  }

}
</script>
<style scoped>
div{
  background: #c85454;
  height: 150px;
  border: 1px solid;

  display: flex;
  flex:nowrap;
  justify-content: center;
  align-items: center;

}

</style>
