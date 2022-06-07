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
                              <tr>
                                <th scope="row">1</th>
                                <td>Anisur Rahman</td>
                                <td>Dhaka</td>
                                <td><button class="btn btn-info">edit</button> <button class="btn btn-danger">Delete</button></td>
                              </tr>
                            </tbody>
                          </table>
                    </div>
</template>

<script>
export default {
  name: 'BodyCom',
  props: {
    msg: String
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
