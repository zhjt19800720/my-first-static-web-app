
<template>
  <div>
    <h1>User Data</h1>
    <p>{{ userData }}</p>
  </div>
</template>
<script>
import axios from 'axios';
 
 export default {
   data() {
     return {
       userData: null
     };
   },
   created() {
     this.fetchUserData();
   },
   methods: {
     fetchUserData() {
       axios.get('https://app-240920125718.azurewebsites.net/api/greeting')
         .then(response => {
           this.userData = response.data;
         })
         .catch(error => {
           console.error('There was an error!', error);
         });
     }
   }
 };
</script>
