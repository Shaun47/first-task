<template>
  <div id="app">
        <div class="container-fluid">
        <div class="row ">
            <div class="col-md-4 sidebar">
                <SideBar :EMPLOYEE_INFO="employeeList" @selected_employee="selectedEmployee"></SideBar>
            </div>
            <div class="col-md-8">
                  
                <div class="row">
                  <HeaderCom @save-new-employee="saveEmployeeHandler"></HeaderCom>
                  <BodyCom :SELECTED_EMPLOYEE="selected_employee" @delete-employee="deleteHandler"></BodyCom>
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

     employeeList:[],
     selected_employee: []
   }
 },
 methods:{
   test(fname,lname){
     console.log(fname,lname);
     this.firstname = fname;
     this.lastname = lname;
   },

   saveEmployeeHandler(value){
    value.id = this.employeeList.length +1;
    this.employeeList = [...this.employeeList, ...[value]];
   },

   selectedEmployee(value) {
      this.selected_employee = value;
   },

   deleteHandler(value){
    console.log(value)
    let findIndex = this.employeeList.findIndex(item => item.id == value.id);
    let findselectedIndex = this.selected_employee.findIndex(item => item.id == value.id);
    if(findIndex > -1){
      this.employeeList.splice(findIndex, 1);
      this.selected_employee.splice(findselectedIndex,1);
    }
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
