<template>
<div id="user">
  <div class="jumbotron ">
    <h1>User Component</h1>
    <p>This is the parent component</p>
        {{name}}
      <button @click="changeName">Change name</button>


    <div class="row" style="margin:20px;">

      <div class="col-sm-6 justify-content-center align-self-center">
        <app-user-details :name="name"
         @nameWasReset="resetName"
         :resetNamefn="resetNameCallBack"></app-user-details>


      </div>
      <div class="col-sm-6">
        <app-user-edit></app-user-edit>
      </div>
    </div>
  </div>
</div>
</template>

<script>
import UserDetails from './UserDetails.vue';
import UserEdit from './UserEdit.vue'

export default {
  name: "user",
  components: {
    appUserDetails: UserDetails,
    appUserEdit: UserEdit
  },
  data() {
    return {
      name:'Juan'
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
