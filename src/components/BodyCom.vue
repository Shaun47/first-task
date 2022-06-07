<template>
                    <div class="col-md-12 body">
                        <table class="table">
                            <thead>
                              <tr>
                                <th scope="col">#</th>
                                <th scope="col">Name</th>
                                <th scope="col">Address</th>
                                <th scope="col">Action</th>
                              </tr>
                            </thead>
                            <tbody>
                              <tr v-for="(item,index) in list" :key="index">
                                <th scope="row">{{index+1}}</th>
                                <td>{{item.name}}</td>
                                <td>{{item.address}}</td>
                                <td><button class="btn btn-info">edit</button> <button class="btn btn-danger" @click="remove_item(index)">Delete</button></td>
                              </tr>
                            </tbody>
                          </table>
                    </div>
</template>

<script>
import {bus} from '../main'

export default {


  
  name: 'BodyCom',
  props: {
    msg: String
  },
mounted(){
      bus.$on('changeBody',(data,num)=>{
        // this.list.push(data[num-2]);
        // this.list.push(data[num-1]);
        this.element.name = data[num-2];
        this.element.address = data[num-1];
        console.log(this.element);
        this.list.push(this.element);
      })
  },
  data(){
    return {
      name:'',
      address:'',
      list: [],
      element: {}
    }
  },
  methods:{
    remove_item(index){
      this.list.splice(index,1);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.body{
    border: 1px solid black;
    padding: 35px;
}

.personal_info{
    list-style-type: none;
    font-weight: bold;
}

</style>
