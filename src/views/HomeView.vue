<template>
  <div>
    <NavBar />

    <v-container fluid>
      <v-row>
        <v-col cols="12" xs="8" sm="6" md="4" lg="3" v-for="i in 12" :key="i" class="mx-xs-auto">
          <v-skeleton-loader type="card-avatar" :loading="loading">
            <VideoCard 
              :video="video"
              :channel="channel"
            ></VideoCard>
          </v-skeleton-loader>
        </v-col>
      </v-row>
    </v-container>

  </div>
</template>

<script>
import NavBar from '../components/NavBar'
import VideoCard from '../components/VideoCard'

  export default {
    components: {
      NavBar, VideoCard
    },
  data() {
    return {
      loading: true,
      video: {
        id: 1,
        url: '/videoPlay',
        title: "iMac Pro Review",
        thumbnail:
          "https://i.ytimg.com/vi/goMlaAmenWA/hqdefault.jpg?sqp=-oaymwEcCOADEI4CSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLA46-W6nixBd_ejrJFR-qoYdzAN4Q",
        youtubeURL: "https://www.youtube.com/embed/jn9mHzXJIV0",
        creator: "Marques Brownlee",
        likes: 0,
        createdAt: '2 years ago',
        subscribers: '100k',
        views: 4526,
        description:
          'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Culpa vel inventore voluptatum reiciendis delectus quibusdam incidunt consequuntur, nostrum aperiam, natus quidem qui corrupti reprehenderit quaerat neque voluptatibus? Ullam, maiores temporibus! Lorem, ipsum dolor sit amet consectetur adipisicing elit. Culpa vel inventore voluptatum reiciendis delectus, Lorem, ipsum dolor sit amet consectetur adipisicing elit. Culpa vel inventore voluptatum reiciendis delectus'
      },
      channel: {
        url: '/channel',
        avatar: '@/assets/profile.jpg'
      }
    }
    
  },

    methods: {
      
    },
    mounted() {
      setTimeout(() => {
        this.loading = false
      }, 2000)
    },
  }
</script>
