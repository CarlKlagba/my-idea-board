<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-card>
        <v-card-title class="headline">
          My Cool Ideas
        </v-card-title>
        <v-card-actions>
          <v-btn
            color="primary"
            nuxt
            @click="createNewIdea"
          >
            Add Idea
          </v-btn>
          <fieldset v-for="(idea, index) in ideas" :key="index">
            <idea-card />
          </fieldset>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator'
type IdeaCard = {text : string}
@Component
export default class extends Vue {
  ideas: IdeaCard[] = [{
    text: "this is a great idea !"
  }]

  createNewIdea(){
    this.ideas.push({text: "new idea baby"})
  }
}
</script>
