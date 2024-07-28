<template>
  <v-container class="fill-height">
    <v-responsive class="d-flex align-center text-center fill-height">
      <div class="text-body-2 font-weight-light mb-n1">Welcome to</div>

      <h1 class="text-h2 font-weight-bold">Theme Challenge</h1>

      <div class="py-5" />

      <v-row class="d-flex align-center justify-center">
        <v-col cols="auto"> <v-btn color="primary"> Primary </v-btn> </v-col>
        <v-col cols="auto">
          <v-btn color="secondary"> Secondary </v-btn>
        </v-col>
        <v-col cols="auto"> <v-btn color="error"> Error </v-btn> </v-col>
      </v-row>

      <div class="py-5" />

      <v-row class="d-flex align-center justify-center">
        <v-col cols="4">
          <v-select
            v-model="selectedTheme"
            :items="myThemes"
            label="Select Theme"
            @update:model-value="setTheme()"
          />
        </v-col>
      </v-row>

      <v-card
        class="mx-auto"
        max-width="400"
      >
        <v-img
          class="align-end text-white"
          cover
          height="200"
          src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
        >
          <v-card-title>Top 10 Australian beaches</v-card-title>
        </v-img>

        <v-card-subtitle class="pt-4">
          Number 10
        </v-card-subtitle>

        <v-card-text>
          <div>Whitehaven Beach</div>

          <div>Whitsunday Island, Whitsunday Islands</div>
        </v-card-text>

      </v-card>

    </v-responsive>
  </v-container>
</template>

<script setup>
  import { ref } from 'vue'
  import { useTheme } from 'vuetify'

  const theme = useTheme()
  const myThemes = ['light', 'dark', 'customLightTheme', 'customDarkTheme']
  const selectedTheme = ref(myThemes[0])

  const setTheme = () => {
    theme.global.name.value = selectedTheme.value
    console.log(selectedTheme.value)
  }
</script>
