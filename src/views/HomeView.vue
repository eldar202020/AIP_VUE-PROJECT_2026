<template>
  <div>
    <!-- Карусель -->
    <v-carousel
      cycle
      height="400px"
      hide-delimiter-background
      show-arrows="hover"
    >
      <v-carousel-item v-for="ad in ads" :key="ad.id">
        <v-img :src="ad.src" height="100%" cover>
          <div class="ad-link">
            <v-btn color="error" :to="'/ad/' + ad.id">
              {{ ad.title }}
            </v-btn>
          </div>
        </v-img>
      </v-carousel-item>
    </v-carousel>

    <!-- Сетка карточек -->
    <v-container>
      <v-row>
        <v-col v-for="ad in ads" :key="ad.id" cols="12" sm="6" md="4">
          <v-card>
            <v-img :src="ad.src" height="200px" cover></v-img>

            <v-card-title>
              <h3>{{ ad.title }}</h3>
            </v-card-title>

            <v-card-text>
              {{ ad.desc }}
            </v-card-text>

            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn text :to="'/ad/' + ad.id"> Open </v-btn>
              <v-btn color="primary" raised> Buy </v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      ads: [
        {
          id: "1",
          title: "First",
          desc: "First Desc",
          src: "https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg",
        },
        {
          id: "2",
          title: "Second",
          desc: "Second Desc",
          src: "https://cdn.vuetifyjs.com/images/carousel/sky.jpg",
        },
        {
          id: "3",
          title: "Third",
          desc: "Third Desc",
          src: "https://cdn.vuetifyjs.com/images/carousel/bird.jpg",
        },
        {
          id: "4",
          title: "Fourth",
          desc: "Fourth Desc",
          src: "https://cdn.vuetifyjs.com/images/carousel/planet.jpg",
        },
      ],
    };
  },
};
</script>

<style scoped>
.ad-link {
  position: absolute;
  bottom: 50px;
  left: 50%;
  transform: translate(-50%, 0);
  background: rgba(0, 0, 0, 0.5);
  padding: 5px 15px;
  border-radius: 5px;
}
</style>
