<template>
  <div class="registration">
    <h1>New User Registration</h1>


    <div class="formHolder">
      <div class="registrationForm">
        <form
          id="app"
          @submit="checkForm"
        >
          <div class="row" v-if="errors.length">
            <p>
              <b>Please correct the following error(s):</b>
              <ul>
                <li v-for="error in errors">{{ error }}</li>
              </ul>
            </p>
          </div>
          <div class="row">
            <label for="firstName">First Name: </label>
            <input
              id="firstName"
              v-model="firstName"
              name="firstName"
              type="text"
            >
          </div>
          <div class="row">
            <label for="lastName">Last Name: </label>
            <input
              id="lastName"
              v-model="lastName"
              name="lastName"
              type="text"
            >
          </div>
          <div class="row">
            <label for="email">Email: </label>
            <input
              id="email"
              v-model="email"
              name="email"
              type="text"
            >
          </div>
          <div class="row">
            <label for="password">Password: </label>
            <input
              id="password"
              v-model="password"
              name="password"
              type="password"
            >
          </div>
          <div class="row">
            <label for="passwordConfirm">Confirm Password: </label>
            <input
              id="passwordConfirm"
              v-model="passwordConfirm"
              name="passwordConfirm"
              type="password"
            >
          </div>
          <div class="row">
            <input type="submit" value="Submit">
            <input type="reset" value="Clear Form" >
          </div>
      </form>
        </div>
    </div>
  </div>
</template>

<script>
// import { REGISTER } from "@/store/actions.type";

export default {
  name: 'Register',
  data() {
    return {
      errors: [],
      firstName: null,
      lastName: null,
      email: null,
      password: null,
      passwordConfirm: null,
    };
  },
  methods: {
    checkForm: function (e) {
      if (
        (this.firstName && this.lastName && this.email && this.password) && (this.password === this.passwordConfirm)) {
          this.$store
            .dispatch(REGISTER, { firstName, lastName, email, password })
            .then(() => this.$router.push({ name: "home" }));
        return true;
      }

      this.errors = [];

      if (!this.firstName) {
        this.errors.push('First name required.');
      }

      if (!this.lastName) {
        this.errors.push('Last name required.');
      }

      if (!this.email) {
        this.errors.push('Email required.');
      }

      if (!this.password) {
        this.errors.push('Password required.');
      }

      if (this.password !== this.passwordConfirm) {
        this.errors.push('Password and confirm password do not match.');
      }

      e.preventDefault();

      return false;
    },
  },
};
</script>

<style scoped>
.formHolder {
  display: flex;
  align-items: center;
  justify-content: center;
}
.registrationForm {

}
.row {
    margin: 10px;
    text-align: left;
}
</style>
