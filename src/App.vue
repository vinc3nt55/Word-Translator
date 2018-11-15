<template>
  <div class="text-center" id="app">
  	<div>
	  	<h1>World Translator</h1>
	  	<h5>Powered By Vue.js</h5>
	    <TranslateForm @emit="translateText"></TranslateForm>
	    <TranslateOutput v-text="translatedText"></TranslateOutput>
  	</div>
  </div>
</template>

<script>
import TranslateForm from './components/TranslateForm'
import TranslateOutput from './components/TranslateOutput'
export default {
  name: 'App',
  components: {
    TranslateForm,
    TranslateOutput
  },
  data: function() {
  	return {
  		translatedText: '',
  	}
  },
  methods: {
  	translateText: function(text, language) {
  		this.$http.get(`https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20181112T123106Z.6e030e264153b23a.0f72d2fded52e29d3aa507917b628d4e6af87665&lang=${language}&text=${text}`).then((response) => {
  			this.translatedText = response.body.text[0];
  		});
  	}
  }
}
</script>

<style>
body{
	background: #f3f3f3;
}
#app{
	max-width: 1024px;
	height: 50vh;
	display: flex;
	align-items: center;
	justify-content: center;
}
</style>
