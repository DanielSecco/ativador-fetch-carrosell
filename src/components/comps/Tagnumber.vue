<template>
  <div  class="tagnumber">
    <h1>{{ msg }}</h1>
      <p>
    Informe o número da tag ou utilize o Leitor
    </p>
   <input id="tagNum" v-on:change="sendop" type="number" v-model.number="num"/>
      <br/>
    <button class="btreader" @click="showreader">QR CAM</button>
      <br/>
    <button class="btavancar" @click="avancar">AVANÇAR</button>
  </div>
</template>

<script>
    var $ = require('jquery');
 import Swiper from 'swiper'
export default {
  name: 'tagnumber',
  data () {
    return {
      
        msg: 'TAG #',
		num: ''
		
    }
  },
    methods: {
       sendop: function(event){

         window.tagNum1 = this.num;
        console.log(window.tagNum1);
    return window.tagNum1;
    
    },showreader() {
                $(".qrcode-reader").css('display', 'block')
                $(".btreader").css('display', 'none')
                console.log('content');
            },
        avancar () {
            
              var mySwiper = new Swiper('.swiper-container', {

});
        mySwiper.slideTo(2);
            
        }
        
        
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
    color:black;
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