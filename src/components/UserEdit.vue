<template>
  <div id="UserEdit">
    <button @click="editAge">Edit Age</button>    {{age}}
    <br><hr>
    <span>this will only change age in the component edit age</span>
<div>
<button @click="editAgeChildComponent">EditAge user details too</button>
<button @click="editAgeBus">clickMe</button>
{{age}}
</div>
  </div>
</template>
<script>
import { eventBus } from "../main";
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
     this.$emit('ageWasEdited',this.age)
    eventBus.$emit('ageWasEdited',this.age);
  },
editAgeBus(){
  this.age=31;
  eventBus.$emit('ageWasEdited',this.age);
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
