<template>
  <div>
    <h2>Logged: {{ logged }}</h2>
    <Card1 />
  </div>
</template>

<script setup lang="ts">
import { useLogged } from '~~/composables/states'
const logged = useLogged();
definePageMeta({
  middleware: 'auth1',
  pageTransition: {
    name: 'rotate'
  }
});
</script>
<style>
 
</style>