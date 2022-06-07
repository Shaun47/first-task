<template>
<div class="col-md-12 header">
    <div class="input-group flex-nowrap">
        <span class="input-group-text" id="addon-wrapping">Name</span>
        <input type="text" class="form-control" v-model="fname" placeholder="Username" aria-label="Username" aria-describedby="addon-wrapping"> 
    </div>
    <div class="input-group flex-nowrap mt-3">
        <span class="input-group-text" id="addon-wrapping">Address</span>
        <input type="text" class="form-control" v-model="lname" placeholder="Address" aria-label="Address" aria-describedby="addon-wrapping">
    </div>
    <!-- <button class="btn btn-primary mt-3" @click="$emit('submit',fname,lname)">Save</button> -->
     <button class="btn btn-primary mt-3" @click="changeTitle">Save</button>
</div>
</template>

<script>
import {bus} from '../main'


export default {
  name: 'HeaderCom',
//   emits: ['submit'],
//   props: {
//     name: String
//   },
  data(){
      return {
          fname: '',
          lname: '',
          list: [],
          object:{}
      }
  },
  methods:{
    //   changeName(){
    //       this.$emit('changeName','Hossain')
    //   }
    changeTitle(){

        

        this.list.push(this.fname)
        this.list.push(this.lname)
        this.list.push("mark")
        bus.$emit('changeTitle',this.list);
    }
  },

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.header{
    border: 1px solid black;
    padding: 35px;
}

.personal_info{
    list-style-type: none;
    font-weight: bold;
}
</style>
