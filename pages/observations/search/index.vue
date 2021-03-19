<template>
  <v-container fluid>
    <v-breadcrumbs :items="breadcrumbs"></v-breadcrumbs>
    <v-card>
      <v-card-title>
        <v-btn small color="primary" @click="search">Search</v-btn>
        <v-spacer></v-spacer>
      </v-card-title>
      <v-data-table
        :headers="headers"
        :items="resources"
        :loading="loading"
      ></v-data-table>
    </v-card>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      breadcrumbs: [{ text: 'Observations' }, { text: 'Search' }],
      headers: [
        { text: '#', value: 'resource.id' },
        { text: 'Resource Type', value: 'resource.resourceType' },
        { text: 'Profile', value: 'resource.meta.profile' },
        { text: 'Subject', value: 'resource.subject.identifier.value' }
      ],
      loading: false,
      resources: []
    }
  },
  methods: {
    search() {
      this.loading = true
      this.$axios
        .get(`${process.env.baseUrl}/Observation`)
        .then((response) => {
          this.resources = response.data.entry
        })
        .finally(() => {
          this.loading = false
        })
    }
  }
}
</script>
