<template>
  <div>
    <fake-person></fake-person>
  </div>
</template>

<script>

import FakePerson from '@/components/FakePerson.vue'

export default {
  name: 'App',
  components: {
    FakePerson
  }
}
</script>

<style>

html, body {
  margin: 0;
  padding: 0
}

#app {
  inset: 0;
}
</style>
