<template>
  <div class="ev-login col-sm-4 offset-sm-4">
   <!-- <spinner v-show="loggingIn" message="Logging in..."></spinner>-->
    
    <div class="alert alert-danger" v-if="error">
      <p>{{ error }}</p>
    </div>
    <div class="form-group ">
      <input 
        type="text"
        data-id="login.username" 
        class="form-control js-login__username w33"
        placeholder="Enter your username"
        v-model="credentials.username"
      >
    </div>
    <div class="form-group">
      <input
        type="password"
        class="form-control js-login__password w33 "
        placeholder="Enter your password"
        v-model="credentials.password"
      >
    </div>
    <button 
      data-id="login.submit"
      class="btn btn-primary solid black js-login__submit" 
      @click="submit()"
    >
      Login &nbsp; <i class="fa fa-arrow-circle-o-right"></i>
    </button>
    <br><br><br>
    <a href="#">Forgot your password?</a><br>
    Don’t have an account? &nbsp;<a href="#">Sign up here.</a>

  </div>
</template>

<script>
import Spinner from '@/components/comps/Spinner'
    
import {
        swiper,
        swiperSlide
    } from 'vue-awesome-swiper'
    import Swiper from 'swiper'
export default {
  name: 'login',
  components: { Spinner, swiper, swiperSlide },

  data () {
    return {
      credentials: {
        username: '',
        password: ''
      },
      loggingIn: false,
      error: ''
    }
  },
      
   
  methods: {
    submit () {
      this.loggingIn = true
      const credentials = {
        username: this.credentials.username,
        password: this.credentials.password
      }
      console.log(credentials);
     var mySwiper = new Swiper('.swiper-container', {
  // ...
  on: {
    init: function () {
      console.log('swiper initialized');
    },
  },
});
        mySwiper.slideTo(1);

      // Auth.login() returns a promise. A redirect will happen on success.
      // For errors, use .then() to capture the response to output
      // error_description (if exists) as shown below:
    /*  this.$auth.login(credentials, 'dashboard').then((response) => {
        this.loggingIn = false
          
        this.error = utils.getError(response)
      });*/
        
    }
  }
}
</script>

<style lang="scss" scoped>
    .form-group{
        position: relative;
     top: -50px;
        
        margin: 1em;
    }
    
.ev-login {
  margin-top: 100px;
}
button {
    color: aliceblue;
background-color: #000;
	font-size: 2em;
	padding: 1em 2em;
	border: none !important;
	border-radius: 5em;
	box-shadow: none;
}
</style>
