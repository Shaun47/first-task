<template>
  <div id="app">
        <div class="container-fluid">
        <div class="row ">
            <div class="col-md-4 sidebar">
                <SideBar :fname="firstname" :lname="lastname"></SideBar>

            </div>
            <div class="col-md-8">
                  
                <div class="row">
                  <HeaderCom :name="name" @submit="test"></HeaderCom>
                  <BodyCom></BodyCom>

                </div>
            </div>

        </div>
    </div>














  </div>
</template>

<script>
import SideBar from './components/SideBar.vue'
import HeaderCom from './components/HeaderCom.vue'
import BodyCom from './components/BodyCom.vue'


export default {
  name: 'App',
  
  components: {
    SideBar,
    HeaderCom,
    BodyCom
},
 data(){
   return {
     name: 'Shaun',
     firstname: '',
     lastname: '',
   }
 },
 methods:{
   test(fname,lname){
     console.log(fname,lname);
     this.firstname = fname;
     this.lastname = lname;
   }
 }
}
</script>

<style>
.sidebar{
    border: 1px solid black;
    padding: 35px;
}


</style>
