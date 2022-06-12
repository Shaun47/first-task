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
            <tr v-for="(item,index) in SELECTED_EMPLOYEE" :key="index">
              <th scope="row">{{index+1}}</th>
              <td>{{item.name}}</td>
              <td>{{item.address}}</td>
              <td><button class="btn btn-info" data-bs-toggle="modal" data-bs-target="#exampleModal" @click="editHandler(item)">edit</button> <button class="btn btn-danger" @click="deleteHandler(item)">Delete</button></td>
            </tr>
          </tbody>
        </table>


      <!-- Modal -->
      <div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
        <div class="modal-dialog">
          <div class="modal-content">
            <div class="modal-header">
              <h5 class="modal-title" id="exampleModalLabel">Modal title</h5>
              <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
            </div>
            <div class="modal-body">
                  <div class="input-group flex-nowrap">
                      <span class="input-group-text" id="addon-wrapping">Name</span>
                      <input type="text" class="form-control"  aria-label="Username" aria-describedby="addon-wrapping" v-model="name"> 
                  </div>
                  <div class="input-group flex-nowrap mt-3">
                      <span class="input-group-text" id="addon-wrapping">Address</span>
                      <input type="text" class="form-control"  aria-label="Address" aria-describedby="addon-wrapping" v-model="address">
                  </div>
            </div>
            <div class="modal-footer">
              <button type="button" class="btn btn-secondary" data-bs-dismiss="modal" @click="updatedInfo" >Update</button>
            </div>
          </div>
        </div>
      </div>
        </div>


  
</template>

<script>


export default {
  name: 'BodyCom',
  props: ['SELECTED_EMPLOYEE'],
mounted(){

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
    deleteHandler(item){
      this.$emit('delete-employee', item)
    },
    editHandler(item){
        this.name = item.name;
        this.address = item.address;
       
    },
    updatedInfo(){
      
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
