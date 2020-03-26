<template>
    <q-page class="bg-grey-3">
      <div class="row">
        <q-card class="fixed-center col-md-4 col-xs-12 bg-white" flat>
          <q-card-section>
            <div class="text-h6 q-pb-md">
              Login page
    </div>
    <q-form
      @submit="onSubmit"
      @reset="onReset"
      class="q-gutter-md"
    >
      <q-input
        filled
        v-model="username"
        label="Username *"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Type your username']"
      />

      <q-input
        filled
        type="Password"
        v-model="password"
        label="Password *"
        lazy-rules
        :rules="[
          val => val !== null && val.length > 0 || 'Type your password']"
      />
      <div>
        <q-btn label="Enter" type="enter" color="primary"/>
        <q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />
      </div>
    </q-form>
    </q-card-section>
    </q-card>
    </div>
    </q-page>
</template>
<script>
export default {
  data () {
    return {
      username: null,
      password: null
    }
  },
  methods: {
    onSubmit () {
      if (this.username === 'Nathan' && this.password === '18421011') {
        this.$q.notify({
          type: 'positive',
          message: 'Login Successful!'
        })
        this.$router.push('/home')
      } else {
        this.$q.notify({
          type: 'negative',
          message: 'Login Failed, try again!'
        })
      }
    },
    onReset () {
      this.username = null
      this.password = null
    }
  }
}
</script>
