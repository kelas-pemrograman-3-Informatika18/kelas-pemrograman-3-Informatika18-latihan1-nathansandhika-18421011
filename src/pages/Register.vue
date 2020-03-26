<template>
    <q-page>
    Register page
    <q-form
      @submit="onSubmit"
      @reset="onReset"
      class="q-gutter-md"
    >
      <q-input
        filled
        v-model="Name"
        label="Name *"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Type your Name']"
      />

      <q-input
        filled
        v-model="Username"
        label="Username *"
        lazy-rules
        :rules="[val => val !== null && val.length > 0 || 'Type your Username']"
      />
      <q-input
        filled
        type="Password"
        v-model="Password"
        label="Password *"
        lazy-rules
        :rules="[
          val => val !== null && val.length > 0 || 'Type your Password'
        ]"
      />
      <q-input
        filled
        v-model="CPassword"
        label="Confirm password *"
        lazy-rules
        :rules="[
          val => val !== null && val.length > 0 || 'Confirm your password'
        ]"
      />
      <q-input
        filled
        v-model="Address"
        label="Address *"
        lazy-rules
        :rules="[
          val => val !== null && val.length > 0 || 'Type your Address'
        ]"
      />
      <q-input
        filled
        v-model="Phone"
        label="Phone *"
        lazy-rules
        :rules="[
          val => val !== null && val.length > 0 || 'Type your Phone'
        ]"
      />
      <div>
        <q-btn label="Enter" type="enter" color="primary"/>
        <q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />
      </div>
    </q-form>
    </q-page>
</template>
<script>
export default {
  data () {
    return {
      Name: null,
      Username: null,
      Password: null,
      CPassword: null,
      Address: null,
      Phone: null
    }
  },
  methods: {
    onSubmit () {
      console.log('Submit')
    },
    onReset () {
      console.log('Reset')
    }
  }
}
</script>
