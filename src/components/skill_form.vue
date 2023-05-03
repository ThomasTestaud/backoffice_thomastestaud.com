<template>
    <form @submit.prevent="submitForm">
      <label for="text-input">Skill:</label>
      <input type="text" id="text-input" v-model="textInput" required>
      
      <label for="textarea-input">Skill description:</label>
      <textarea id="textarea-input" v-model="textareaInput" required></textarea>
      
      <input type="text" id="skill-id" v-model="skillId">
      
      <button type="submit">Valider</button>
    </form>
  </template>
  
  <script>
    import axios from 'axios';

    export default {
        name: 'skill_form',
        props: {
            title: String,
            description: String,
            id : Number
        },
      data() {
        return {
            
          textInput: this.title,
          textareaInput: this.description,
          skillId: this.id
          
        }
      },
      methods: {
        submitForm() {
        
          // perform ajax request using axios
          axios.put('https://skillsapi.thomastestaud.com/index.php?route=api', {
            textInput: this.textInput,
            textareaInput: this.textareaInput,
            hiddenInput: this.hiddenInput
          }).then(response => {
            // handle successful response here
            console.log(response);
          }).catch(error => {
            // handle error response here
            console.log('There has been an error' + error);
          });
          
        }
      }
    }
  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>