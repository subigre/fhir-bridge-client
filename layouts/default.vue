<template>
  <v-app class="fhir-bridge">
    <v-app-bar app dark clipped-left dense color="indigo">
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title>FHIR Bridge Demo Client</v-toolbar-title>
    </v-app-bar>
    <v-navigation-drawer v-model="drawer" app clipped>
      <v-list dense>
        <v-list-item>
          <v-list-item-title>Audit Event</v-list-item-title>
        </v-list-item>
        <v-list-item>
          <v-list-item-title>Condition</v-list-item-title>
        </v-list-item>
        <v-list-item>
          <v-list-item-title>Consent</v-list-item-title>
        </v-list-item>
        <v-list-item>
          <v-list-item-title>Diagnostic Report</v-list-item-title>
        </v-list-item>
        <v-list-group>
          <template #activator>
            <v-list-item-title>Observations</v-list-item-title>
          </template>
          <v-list-item nuxt to="/observations/create">
            <v-list-item-icon>
              <v-icon>mdi-pencil</v-icon>
            </v-list-item-icon>
            <v-list-item-content>
              <v-list-item-title>Create</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
          <v-list-item nuxt to="/observations/search">
            <v-list-item-icon>
              <v-icon>mdi-magnify</v-icon>
            </v-list-item-icon>
            <v-list-item-content>
              <v-list-item-title>Search</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list-group>
        <v-list-item>
          <v-list-item-title>Patient</v-list-item-title>
        </v-list-item>
        <v-list-item>
          <v-list-item-title>Procedure</v-list-item-title>
        </v-list-item>
        <v-list-item>
          <v-list-item-title>Questionnaire-Response</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-main>
      <nuxt />
    </v-main>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      drawer: true
    }
  }
}
</script>
