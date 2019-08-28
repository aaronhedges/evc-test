<template>
  <div class="registration">
    <h1>New User Registration</h1>


    <div class="formHolder">
      <div class="registrationForm">
        <form
          id="app"
          @submit="checkForm"
          action="registerSubmit"
          method="post"
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

<style scoped>
.formHolder {
  display: flex;
  align-items: center;
  justify-content: center;
}
.registrationForm {
    text-align: left;
}
.row {
    margin: 10px;
}
</style>