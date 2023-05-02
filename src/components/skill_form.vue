<template>
    <form @submit.prevent="submitForm">
      <label for="text-input">Text Input:</label>
      <input type="text" id="text-input" v-model="textInput" required>
      
      <label for="textarea-input">Textarea Input:</label>
      <textarea id="textarea-input" v-model="textareaInput" required></textarea>
      
      <input type="hidden" id="hidden-input" v-model="hiddenInput">
      
      <button type="submit">Submit</button>
    </form>
  </template>
  
  <script>
    export default {
        name: 'skill_form',
      data() {
        return {
          textInput: '',
          textareaInput: '',
          hiddenInput: ''
        }
      },
      methods: {
        submitForm() {
            /*
          // perform ajax request using axios or any other library
          axios.put('/your-endpoint-url', {
            textInput: this.textInput,
            textareaInput: this.textareaInput,
            hiddenInput: this.hiddenInput
          }).then(response => {
            // handle successful response here
          }).catch(error => {
            // handle error response here
          });
          */
        }
      }
    }
  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>