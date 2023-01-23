<template lang="">
  <div>
   <h1>Index</h1>
   <h2>Logged: {{logged}}</h2>
  </div>
</template>
<script setup>
import { useLogged } from '~~/composables/states';

const logged = useLogged();
</script>
<style>
  
</style>