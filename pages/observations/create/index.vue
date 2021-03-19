<template>
  <v-container fluid>
    <v-breadcrumbs :items="breadcrumbs"></v-breadcrumbs>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      breadcrumbs: [{ text: 'Observations' }, { text: 'Create' }]
    }
  }
}
</script>
