<template>
  <div class="wrapper">
    <h3>LOGIN</h3>
    <div class="mt-6">
      <h5 class="email">Email Address</h5>
      <v-text-field placeholder="Enter your email address" type="email" />
    </div>
    <div>
      <h5 class="password">Password</h5>
      <v-text-field placeholder="Enter your password"
                    :append-icon="value ? 'mdi-eye' : 'mdi-eye-off'"
                    @click:append="() => (value = !value)"
                    :type="value ? 'text' : 'password'"
                    id="password"/>

    </div>
    <AppButton text="Submit"/>



  </div>
</template>

<script>
  import AppButton from "../components/resusable/App-button";
  export default {
    name: 'Login',
    components: {AppButton},
    data: ()=>{
      return{
        value: false
      }
    }
  }
</script>
<style>
.wrapper{
  margin: 10rem auto;
  max-width: 400px;
  padding: 1rem;

}
</style>
