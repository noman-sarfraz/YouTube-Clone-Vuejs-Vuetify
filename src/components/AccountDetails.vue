<template>
  <div>
    <v-menu offset-y>
      <template v-slot:activator="{ on }">
        <v-avatar class="ml-3" style="cursor: pointer" v-on="on">
          <img src="@/assets/profile.jpg">
        </v-avatar>
      </template>
      <v-card class="rounded-0">
        <v-list dense class="overflow-y-auto" style="max-height: calc(100vh - 100px)">
          <v-list-item>
            <v-list-item-avatar>
              <img src="@/assets/profile.jpg">
            </v-list-item-avatar>
            <v-list-item-content>
              <v-list-item-title class="mb-3 font-weight-bold">
                Noman Sarfraz
              </v-list-item-title>
              <v-list-item-subtitle class="blue--text font-weight-medium" to="#" style="cursor: pointer;">
                Manage your Google account
              </v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
          <v-divider></v-divider>
          <v-list-item to="#" style="cursor:pointer;">
            <v-list-item-icon>
              <v-icon>mdi-account-box</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Your channel</v-list-item-title>
          </v-list-item>
          <v-list-item to="#" style="cursor:pointer;">
            <v-list-item-icon>
              <v-icon>mdi-currency-usd</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Purchases and memeberships</v-list-item-title>
          </v-list-item>
          <v-list-item to="#" style="cursor:pointer;">
            <v-list-item-icon>
              <v-icon>mdi-youtube-studio</v-icon>
            </v-list-item-icon>
            <v-list-item-title>YouTube Studio</v-list-item-title>
          </v-list-item>
          <v-list-item to="#" style="cursor:pointer;">
            <v-list-item-icon>
              <v-icon>mdi-account-box-multiple</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Switch account</v-list-item-title>
            <v-list-item-icon>
              <v-icon>mdi-menu-right</v-icon>
            </v-list-item-icon>

            <!-- <v-list-item-action>
              <v-btn icon>
                <v-icon color="grey lighten-1">mdi-menu-right</v-icon>
              </v-btn>
            </v-list-item-action> -->
          </v-list-item>
          <v-list-item to="#" style="cursor:pointer;">
            <v-list-item-icon>
              <v-icon>mdi-login-variant</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Sign out</v-list-item-title>
          </v-list-item>
          <v-divider></v-divider>
          <v-list-item to="#" style="cursor:pointer;">
            <v-list-item-icon>
              <v-icon>mdi-theme-light-dark</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Appearance: Device theme</v-list-item-title>
          </v-list-item>
          <v-list-item to="#" style="cursor:pointer;">
            <v-list-item-icon>
              <v-icon>mdi-translate</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Language: English</v-list-item-title>
            <v-list-item-icon>
              <v-icon>mdi-menu-right</v-icon>
            </v-list-item-icon>
          </v-list-item>
          <v-list-item to="#" style="cursor:pointer;">
            <v-list-item-icon>
              <v-icon>mdi-longitude</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Location: Algeria</v-list-item-title>
            <v-list-item-icon>
              <v-icon>mdi-menu-right</v-icon>
            </v-list-item-icon>
          </v-list-item>
          <v-list-item to="#" style="cursor:pointer;">
            <v-list-item-icon>
              <v-icon>mdi-cog</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Settings</v-list-item-title>
          </v-list-item>
          <v-list-item to="#" style="cursor:pointer;">
            <v-list-item-icon>
              <v-icon>mdi-account-box</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Your data in Jet-Tube</v-list-item-title>
          </v-list-item>
          <v-list-item to="#" style="cursor:pointer;">
            <v-list-item-icon>
              <v-icon>mdi-help-circle</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Help</v-list-item-title>
          </v-list-item>
          <v-list-item to="#" style="cursor:pointer;">
            <v-list-item-icon>
              <v-icon>mdi-comment-alert</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Send Feedback</v-list-item-title>
          </v-list-item>
          <v-list-item to="#" style="cursor:pointer;">
            <v-list-item-icon>
              <v-icon>mdi-keyboard-settings</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Keyboard shortcut</v-list-item-title>
          </v-list-item>
          <v-list-item to="#" style="cursor:pointer;">
            <v-list-item-title>Restricted Mode: Off</v-list-item-title>
            <v-list-item-icon>
              <v-icon>mdi-menu-right</v-icon>
            </v-list-item-icon>
          </v-list-item>
        </v-list>
      </v-card>
    </v-menu>
  </div>
</template>

<script>

</script>

<style scoped>

</style>