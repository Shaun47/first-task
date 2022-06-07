<template>
    <ul class="personal_info" >
        <li v-for="(item,index) in list" :key="index">
            
             <span v-if="item != 'mark'">{{item}}</span>
            <span v-if="item =='mark'" ><input class="form-check-input checkInput" @click="changeBody(index)" type="checkbox" value="" id="flexCheckDefault" ></span>
            
        </li>
    </ul>
</template>

<script>
import {bus} from '../main'

export default {
  name: 'SideBar',
  // props: {
  //   msg: String,
  //   fname: String,
  //   lname: String,
    
  // },
  data(){
    return {
      list: '',
      ulLi: ''
      
    }
  },
  methods:{
   changeBody(number){
        // let check = document.getElementsByClassName("checkInput");
        bus.$emit('changeBody',this.list,number);
    }
  },
  mounted(){
      bus.$on('changeTitle',(data)=>{
        this.list = data;

      })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.personal_info{
    list-style-type: none;
    font-weight: bold;
}
</style>
