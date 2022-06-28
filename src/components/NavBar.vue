<template>
  <nav>
    <v-app-bar app flat clipped-left>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title class="ml-n5">
        <v-btn text to="/" plain>
          <img src="../assets/logo.png" style="width: 30px" class="mr-1">
          <div class="">YouTube</div>
        </v-btn>
      </v-toolbar-title>
      <v-spacer></v-spacer>

      <v-text-field dense outlined hide-details clearable placeholder="Search" class="rounded-0 hidden-sm-and-down"
        v-model="searchText">
      </v-text-field>
      <v-btn dense text outlined class="pa-5 rounded-0 hidden-sm-and-down" @click="search">
        <v-icon>mdi-magnify</v-icon>
      </v-btn>
      <v-tooltip bottom>
        <template v-slot:activator="{ on }">
          <v-btn icon class="ml-1 hidden-sm-and-down" v-on="on">
            <v-icon>mdi-microphone</v-icon>
          </v-btn>
        </template>
        <span>Search with your voice</span>
      </v-tooltip>

      <v-spacer></v-spacer>

      <v-tooltip bottom>
        <template v-slot:activator="{ on }">
          <v-btn icon v-on="on">
            <v-icon>mdi-video-plus</v-icon>
          </v-btn>
        </template>
        <span>Create</span>
      </v-tooltip>

      <v-tooltip bottom>
        <template v-slot:activator="{ on }">
          <v-btn icon v-on="on">
            <v-icon>mdi-apps</v-icon>
          </v-btn>
        </template>
        <span>YouTube apps</span>
      </v-tooltip>

      <v-tooltip bottom>
        <template v-slot:activator="{ on }">
          <v-btn icon v-on="on">
            <v-icon>mdi-bell</v-icon>
          </v-btn>
        </template>
        <span>Notifications</span>
      </v-tooltip>

      <AccountDetails></AccountDetails>

    </v-app-bar>

    
    <!-- <v-navigation-drawer 
      app 
      clipped
      v-if="$vuetify.breakpoint.name === 'md' || $vuetify.breakpoint.name === 'sm'"
    >
      <v-list dense nav class="py-0 ml-n2">
        <v-list-item v-for="(page, index) in smallerItems" :key="index" link dense :to="page.link" class="pr-0">
          <v-list-item-icon class="ml-4 mr-6">
            <v-icon>{{ page.icon }}</v-icon>
          </v-list-item-icon>
        </v-list-item>
      </v-list>
    </v-navigation-drawer> -->

    <!-- Drawer -->
    <v-navigation-drawer v-model="drawer" app clipped>
      <v-list dense nav class="py-0 ml-n2">
        <v-list-item class="hidden-lg-and-up">
          <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
          <v-btn text to="/" plain>
            <img src="../assets/logo.png" style="width: 30px" class="mr-1">
            <div class="">YouTube</div>
          </v-btn>
        </v-list-item>
        <v-divider class="hidden-lg-and-up"></v-divider>

        <div v-for="(parentItem, index) in items" :key="index">
          <v-subheader v-if="parentItem.header" class="pl-3 py-4 font-weight-bold text-subtitle-2 text-uppercase">{{
            parentItem.header }}</v-subheader>

          <v-list-item v-for="(page, index) in parentItem.pages" :key="index" link dense :to="page.link" class="pr-0">

            <v-list-item-icon v-if="parentItem.header !== 'Subscriptions'" class="ml-4 mr-6">
              <v-icon>{{ page.icon }}</v-icon>
            </v-list-item-icon>
            <v-list-item-avatar v-else>
              <img src="../assets/profile.jpg">
            </v-list-item-avatar>
            <v-list-item-content>
              <v-list-item-title>
                {{ page.title }}
              </v-list-item-title>
            </v-list-item-content>
          </v-list-item>
          <v-divider class="mt-2 mb-2"></v-divider>
        </div>
        <v-divider class="mt-2 mb-2"></v-divider>
      </v-list>

      <v-list class="px-2">
        <span v-for="(link, index) in links" :key="index" class="mb-0">
          <span v-if="link.text === 'Terms'" class="mt-2 d-block"> </span>
          <v-btn href text :to="link.link" small class="px-1 text-capitalize mb-0 black--text">
            {{ link.text }}
          </v-btn>
        </span>
      </v-list>

    </v-navigation-drawer>


  </nav>
</template>

<script>
import AccountDetails from './AccountDetails.vue'

export default {
  components: { AccountDetails },
    updated() {
      console.log("drawer: ", this.drawer );
    },
    data() {
        return {
            drawer: false,
            searchText: "",
            smallerItems: [
              { title: "Home", link: "/", icon: "mdi-home" },
              { title: "Explore", link: "#", icon: "mdi-compass" },
              { title: "Shorts", link: "#", icon: "mdi-fire" },
              {
                title: "Subscriptions",
                link: "#",
                icon: "mdi-youtube-subscription"
              },
              {
                title: "Library",
                link: "#",
                icon: "mdi-play-box-multiple"
              },
            ],
            items: [
                {
                    header: null,
                    pages: [
                        { title: "Home", link: "/", icon: "mdi-home" },
                        { title: "Explore", link: "#", icon: "mdi-compass" },
                        { title: "Shorts", link: "#", icon: "mdi-fire" },
                        {
                            title: "Subscriptions",
                            link: "#",
                            icon: "mdi-youtube-subscription"
                        }
                    ]
                },
                {
                    header: null,
                    pages: [
                        {
                            title: "Library",
                            link: "#",
                            icon: "mdi-play-box-multiple"
                        },
                        {
                            title: "History",
                            link: "#",
                            icon: "mdi-history"
                        },
                        {
                            title: "Your videos",
                            link: "#",
                            icon: "mdi-play-box-outline"
                        },
                        {
                            title: "Watch later",
                            link: "#",
                            icon: "mdi-clock"
                        },
                        {
                            title: "Liked videos",
                            link: "#",
                            icon: "mdi-thumb-up"
                        }
                    ]
                },
                {
                    header: "Subscriptions",
                    pages: [
                        {
                            title: "Traversy Media",
                            link: "#",
                            icon: "mdi-badge-account",
                            img: "../assets/traversy.jpg"
                        },
                        {
                            title: "Deligent Dev",
                            link: "#",
                            icon: "mdi-badge-account",
                            img: "../assets/deligent.jpg"
                        },
                        {
                            title: "The Net Ninija",
                            link: "#",
                            icon: "mdi-badge-account",
                            img: "../assets/netNinja.jpg"
                        },
                        {
                            title: "AAE IdeaPro",
                            link: "#",
                            icon: "mdi-badge-account",
                            img: "../assets/ideaPro.jpg"
                        }
                    ]
                },
                {
                    header: "MORE FROM Jet-Tube",
                    pages: [
                        {
                            title: "Jet-Tube Premium",
                            link: "#",
                            icon: "mdi-youtube"
                        },
                        {
                            title: "Gaming",
                            link: "#",
                            icon: "mdi-youtube-gaming"
                        },
                        {
                            title: "Live",
                            link: "#",
                            icon: "mdi-access-point"
                        }
                    ]
                },
                {
                    header: null,
                    pages: [
                        {
                            title: "Setting",
                            link: "#",
                            icon: "mdi-cog"
                        },
                        {
                            title: "Report history",
                            link: "#",
                            icon: "mdi-flag"
                        },
                        {
                            title: "Help",
                            link: "#",
                            icon: "mdi-help-circle"
                        },
                        {
                            title: "Send feedback",
                            link: "#",
                            icon: "mdi-message-alert"
                        }
                    ]
                }
            ],
            links: [
                { text: "About", link: "#" },
                { text: "Press", link: "#" },
                { text: "Copyrignt", link: "#" },
                { text: "Contact us", link: "#" },
                { text: "Creators", link: "#" },
                { text: "Advertise", link: "#" },
                { text: "Developers", link: "#" },
                { text: "Terms", link: "#" },
                { text: "Privacy", link: "#" },
                { text: "Policy & Safety", link: "#" },
                { text: "Test new features", link: "#" }
            ],
        };
    },
    methods: {
        search() { }
    },
    mounted() {
        this.drawer = this.$vuetify.breakpoint.mdAndDown ? false : true;
    },
}
</script>

<style scoped>

</style>