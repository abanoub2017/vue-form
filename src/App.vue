<template>
    <div class="vue-form py-5">
      <div class="container">
        <!-- Title -->
        <h1 class="text-center text-info border-bottom py-2 w-25 m-auto">Vue Form</h1>
        <!-- Form -->
          <form @submit.prevent="addUser()" class="row g-3 w-50 m-auto p-3 shadow mt-5 rounded">
            <!-- First Name -->
            <div class="col-md-6">
              <label for="inputFirstName" class="form-label">First Name</label>
              <input v-model="userInfo.firstName" required type="text" class="form-control" id="inputFirstName">
            </div>
             <!-- Last Name -->
            <div class="col-md-6">
              <label for="inputLastName" class="form-label">Last Name</label>
              <input v-model="userInfo.lastName" required type="text" class="form-control" id="inputLastName">
            </div>
             <!-- Email  -->
            <div class="col-md-6">
              <label for="inputEmai" class="form-label">Email</label>
              <input v-model="userInfo.email" required type="email" class="form-control" id="inputEmai">
            </div>
             <!-- Password -->
            <div class="col-md-6">
              <label for="inputPassword" class="form-label">Password</label>
              <input v-model="userInfo.password" required type="password" class="form-control" id="inputPassword">
            </div>
             <!-- Address -->
            <div class="col-12">
              <label for="inputAddress" class="form-label">Address</label>
              <input  v-model="userInfo.address" required type="text" class="form-control" id="inputAddress" placeholder="1234 Main St">
            </div>
            <div class="col-12 text-center">
              <button type="submit" class="btn btn-primary ">Submit</button>
            </div>
          </form>
        <!-- List User Information -->
         <div v-show="showUserInfo" class="user-info mt-4  w-50 m-auto">
           <h3 class="text-info border-bottom py-2  m-auto">User Information</h3>
           <ul class="list-unstyled">
             <li> <strong>Name</strong> : {{userInfo.firstName}}</li>
             <li> <strong>Email</strong> : {{userInfo.lastName}} </li>
             <li> <strong>Password</strong> : {{userInfo.password}} </li>
             <li> <strong>Address</strong>  : {{userInfo.address}} </li>
           </ul>
         </div>
      </div>
    </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      userInfo:{
        firstName:'',
        lastName:'',
        email:'', 
        password:'',
        address:'',
      },
      showUserInfo: false
    }
  },
  methods : {
    addUser(){
      this.showUserInfo = true;
    }
  }
};
</script>

<style>
</style>
