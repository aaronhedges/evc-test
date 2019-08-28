<template>
  <div class="registration">
    <h1>New User Registration</h1>
    <div class="formHolder">
        <div class="registrationForm">
            <form>
                <div class="row">
                    <label>First Name: </label>
                    <input type="text" name="firstName">
                </div>
                <div class="row">
                    <label>Last Name: </label>
                    <input type="text" name="lastName">
                </div>
                <div class="row">
                    <label>Email: </label>
                    <input type="text" name="email">
                </div>
                <div class="row">
                    <label>Password: </label>
                    <input type="text" name="password">
                </div>
                <div class="row">
                    <label>Confirm Password: </label>
                    <input type="text" name="passwordConfirm">
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