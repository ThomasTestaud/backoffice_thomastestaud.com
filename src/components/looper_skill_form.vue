<template>
    <div>
      <h1>Edit skills</h1>
      <div v-if="forms.length > 0">
        <skill_form v-for="(form, index) in forms" :title="form.comp" :description="form.comp_description" :id="form.id" :key="index" :form-data="form" />
      </div>
      <div v-else>
        <p>Chargement...</p>
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
            console.log(response.data);
          })
          .catch(error => {
            console.log(error);
          });
      }
    }
  </script>
  