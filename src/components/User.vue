<template>
<div id="user">
  <div class="jumbotron ">
    <h1>User Component</h1>
    <p>This is the parent component</p>
        {{name}}
      <button @click="changeName">Change name</button>
{{age}}

    <div class="row" style="margin:20px;">

      <div class="col-sm-6 justify-content-center align-self-center">
        <app-user-details :name="name"
         @nameWasReset="resetName"
         :resetNamefn="resetNameCallBack"
         :age="age"></app-user-details>


      </div>
      <div class="col-sm-6">
        <app-user-edit :age="age"

        ></app-user-edit>

        <h1>Learning about Slot</h1>
        <app-slots>
          <div class="col-sm-8" slot="title"><h1>{{name}}</h1></div>
          <div class="col-sm-8" slot="content"><p>{{age}}</p></div>
        </app-slots>

      </div>
    </div>
  </div>
</div>
</template>

<script>
import UserDetails from './UserDetails.vue';
import UserEdit from './UserEdit.vue';
import AppSlot from  './slots.vue';

export default {
  name: "user",
  components: {
    appUserDetails: UserDetails,
    appUserEdit: UserEdit,
    appSlots:AppSlot
  },
  data() {
    return {
      name:'Juan',
      age:30
    }
  },
  methods:{
    changeName:function(){
      this.name="david";
    },
    resetName(v){
      this.name=v;
    },

    resetNameCallBack(){
      this.name='Max';
    },
    changeAge:function(p){
      this.age=p;
    }

  }
}
</script>
<style scoped>
div{

  justify-content: center;
  align-items: center;
}

</style>
