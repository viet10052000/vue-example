<template>
  <div class="container">
    <h4>Register</h4>
    <div class="mb-3 row">
      <label for="inputName" class="col-sm-2 col-form-label">Name</label>
      <div class="col-sm-10">
        <input type="text" v-model="user.name" class="form-control" id="inputName">
      </div>
    </div>
    <div class="mb-3 row">
      <label for="inputEmail" class="col-sm-2 col-form-label">Email</label>
      <div class="col-sm-10">
        <input type="email" v-model="user.email" class="form-control" id="inputEmail">
      </div>
    </div>
    <div class="mb-3 row">
      <label for="inputPassword" class="col-sm-2 col-form-label">Password</label>
      <div class="col-sm-10">
        <input type="password" v-model="user.password" class="form-control" id="inputPassword">
      </div>
    </div>
    <div class="col-12">
      <button class="btn btn-primary" type="submit" @click="Register">Submit</button>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
import { useStore } from 'vuex'
import { useRouter } from 'vue-router'
const store = useStore();
const router = useRouter();
const user = ref({})
const message = ref();
const successful = ref(false)
const Register = () => {
  store.dispatch('auth/register',user.value)
}
</script>

<style scoped>

</style>