<template>
  <div id="translateForm">
    <div class="form-container">	
      <form class="well form-inline" @enter="formSubmit" @submit="formSubmit">
    		<input class="form-control" type="text" v-model="textToTranslate" placeholder="Enter word...">
        <select class="form-control" v-model="language">
          <option value="ja">Japanese</option>
          <option value="ru">Russian</option>
          <option value="sv">Swedish</option>
          <option value="es">Spanish</option>
          <option value="fr">French</option>
          <option value="zh">Chinese</option>
          <option value="la">Latin</option>
          <option value="nl">Dutch</option>
        </select>
    		<input class="btn btn-primary" type="submit" value="Translate">
    	</form>
    </div>
  </div>
</template>

<script>
export default {
  name: 'translateForm',
  data() {
  	return {
  		textToTranslate: '',
      language: '',
  	}
  },
  created() {
    this.language = 'ja';
  },
  methods: {
  	// Translate and link to the yandex api
  	formSubmit(e) {
  		// Translate to text to api yandex
        this.$emit('emit', this.textToTranslate, this.language)
        e.preventDefault();
  	}
  },

}
</script>

<style>
  .form-container{
    display: flex;  
    align-items: center;
    justify-content: center;
  }
</style>
