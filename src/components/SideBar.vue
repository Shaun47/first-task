<template>
  <div class="sidebarr">
        <ul class="personal_info" v-for="(item,index) in EMPLOYEE_INFO" :key="index">
        <li style="font-weight:bolder;">
             {{item.name}}
             
            
        </li>
        <li ><span style="margin-right:5px;">{{item.address}}</span><span><input class="form-check-input checkInput" @change="checkHandler" v-model="addedList" :value="item" type="checkbox" id="flexCheckDefault" ></span></li>
    </ul>
  </div>
</template>

<script>


export default {
  name: 'SideBar',
  props:['EMPLOYEE_INFO'],
  data(){
    return {
      addedList: []
    }
  },
  methods:{

      checkHandler(){
        this.$emit('selected_employee', this.addedList);
        console.log(this.addedList)
      },
  },
  mounted(){
    
      
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.personal_info{
    list-style-type: none;
   
}
</style>
