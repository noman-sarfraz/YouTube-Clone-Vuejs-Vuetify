<template>
  <div>
    <v-card 
      flat 
      :to="video.url"
      class="mx-auto rounded-0">

      <v-img :src="video.thumbnail" height="150px"></v-img>
      <v-row no-gutters>
        <v-col cols="2">
          <v-list-item>
            <v-list-item-avatar class="ml-n4 mt-4">
              <v-img src="@/assets/profile.jpg"></v-img>
            </v-list-item-avatar>
          </v-list-item>
        </v-col>
        <v-col class="ml-n3">
          <v-card-title class="text-subtitle-2 font-weight-bold mb-1">
            {{ video.title }}
          </v-card-title>
          <v-card-subtitle class="caption grey--text text--darken-1">
            {{ video.creator }}<br>
            {{ video.views }} views<v-icon>mdi-circle-small</v-icon
            >{{ video.createdAt }}
          </v-card-subtitle>
          

        </v-col>
      </v-row>

    </v-card>
  </div>
</template>

<script>
export default {
  props: ['video', 'channel']
}
</script>

<style scoped>

</style>