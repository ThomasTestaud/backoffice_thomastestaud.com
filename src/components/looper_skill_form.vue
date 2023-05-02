<template>
    <div>
      <h1>My Vue App</h1>
      <div v-if="forms.length > 0">
        <skill_form v-for="(form, index) in forms" :key="index" :form-data="form" />
      </div>
      <div v-else>
        <p>Loading forms...</p>
      </div>
    </div>
  </template>
  
  <script>
    import skill_form from './skill_form.vue';
    import axios from 'axios';
  
    export default {
      name: 'looper_skill_form',
      components: {
        skill_form
      },
      data() {
        return {
          forms: []
        }
      },
      mounted() {
        // fetch data from API
        axios.get('https://skillsapi.thomastestaud.com/index.php?route=api&user=0')
          .then(response => {
            this.forms = response.data;
          })
          .catch(error => {
            console.log(error);
          });
      }
    }
  </script>
  