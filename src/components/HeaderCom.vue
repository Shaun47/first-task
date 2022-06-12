<template>
<div class="col-md-12 header">
    <div class="input-group flex-nowrap">
        <span class="input-group-text" id="addon-wrapping">Name</span>
        <input type="text" class="form-control" v-model="name" placeholder="Username" aria-label="Username" aria-describedby="addon-wrapping"> 
    </div>
    
    <div class="input-group flex-nowrap mt-3">
        <span class="input-group-text" id="addon-wrapping">Address</span>
        <input type="text" class="form-control" v-model="address" placeholder="Address" aria-label="Address" aria-describedby="addon-wrapping">
    </div>
    <!-- <button class="btn btn-primary mt-3" @click="$emit('submit',fname,lname)">Save</button> -->
     <button class="btn btn-primary mt-3" @click="saveHandler">Save</button>
</div>
</template>

<script>



export default {
  name: 'HeaderCom',

  data(){
      return {
          name: '',
          address: '',
          list: [],
          object:{}
      }
  },
  methods:{

    saveHandler(){
        let empInfo = {
            name: this.name,
            address: this.address
        }
        this.$emit('save-new-employee', empInfo);

        this.name = '';
        this.address = '';
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
