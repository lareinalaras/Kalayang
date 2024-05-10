<template>
  <q-page>
    <div class="row">
      <div class="col-12 col-md-4 col-lg-4 q-pa-md">
        <div class="text-h4 text-bold">Satu Kalayang</div>
        <div class="text-grey-7">Please Login Your Account Below</div>
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
