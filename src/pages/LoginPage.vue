<template>
  <q-page class="">
    <q-form @submit="register" action="/tes">

      <q-input v-model="formData.email" label="Email" />
      <q-input v-model="formData.password" type="password" label="Password" />
      <q-btn type="submit" label="Login" color="primary" />
    </q-form>

  </q-page>
</template>

<script setup>
defineOptions({
  name: 'LoginPage'
});


</script>

<script>
import axios from 'axios';
// import { $api } from 'boot/axios';

export default {
  data () {
    return {
      formData: {
      email :'',
      password:''
      }
    }
  },
  methods: {
    register () {

      axios.post('http://127.0.0.1:8000/api/savedatanew', this.formData)
        .then(response => {
          // Handle the response
        })
        .catch(error => {
          // Handle the error
        })
    }
  }
}
</script>

<template>
  <q-page>
    <div class="row">
      <div class="col-12 col-md-4 col-lg-4 q-pa-md">
        <div class="text-h4 text-bold">Login</div>
        <!-- <div class="text-grey-7">Please Login Your Account Below</div> -->
        <div class="column">
          <q-input
          outlined
          label="Enter email *"
          v-model="form.email.value"
          :error="form.email.error"
          :error-message="form.email.msg">
            <template v-slot:prepend>
              <q-icon name="email"> </q-icon>
            </template>
          </q-input>
          <q-input
          class="q-mt-sm"
          label="Enter password *"
          outlined
          v-model="form.password.value"
          :error="form.password.error"
          :error-message="form.password.msg">
            <template v-slot:prepend>
              <q-icon name="lock"></q-icon>
            </template>
            <template v-slot:append>
              <q-icon name="visibility_off"></q-icon>
            </template>
          </q-input>
        </div>
        <div class="column q-mt-sm">
            <q-btn
            color="indigo"
            @click="submitLogin">
            Login
          </q-btn>
        </div>
      </div>
    </div>
  </q-page>
</template>

<script setup>
import { ref } from 'vue'
const form = ref({
  email: {
    value: '',
    email: true,
    required: true
  },
  password: {
    value: '',
    required: true
  }
})
const submitLogin = () => {}
</script>
