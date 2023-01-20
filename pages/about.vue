<template>
  <div>
    <Card1 />
  </div>
</template>

<script setup lang="ts">
definePageMeta({
  middleware: 'auth1',
  pageTransition: {
    name: 'rotate'
  }
})
</script>
<style>
 
</style>