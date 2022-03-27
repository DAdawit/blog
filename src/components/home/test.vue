<template>
  <div>
    <div class=" px-5 mb-5 ">
      <h1 class="subheading grey--text mb-5 ">All Auctions</h1>
      <!-- <v-item-group class="mb-5"> -->
      <v-row class="pt-5">
        <v-col v-for="(post,index) in posts" :key="index" cols="12" sm="12" md="4" lg="4">
          <v-item cols="12" sm="12" md="6" lg="4">
            <v-hover v-slot="{ hover }">
              <v-card flat tile class="mx-auto" :elevation="hover ? 12 : 2" :class="{ 'on-hover': hover }">
                <v-img :src="require(`@/assets/articles/${post.hero}`)" height="400"
                  gradient="rgba(0, 0, 0, .42), rgba(0, 0, 0, .42)">
                  <v-row class="fill-height text-right ma-0">

                    <v-col cols="12">
                      <v-chip label class="mx-0 mb-2 text-uppercase" color="grey darken-3" text-color="white" small>
                        {{ post.category }}
                      </v-chip>

                      <h3 class="title font-weight-bold mb-2">
                        {{ post.title }}
                      </h3>

                      <div class="caption">
                        {{ post.author }}<br>Date
                      </div>
                    </v-col>

                    <v-col align-self="end">
                      <v-btn class="text-uppercase ma-0" color="primary" label small>
                        Read More
                      </v-btn>
                    </v-col>

                  </v-row>

                </v-img>

              </v-card>
            </v-hover>
          </v-item>
        </v-col>
      </v-row>
      <!-- </v-item-group> -->
    </div>
    <!-- <h1>{{posts[0]}}</h1> -->
  </div>
</template>
<script>
  export default {
    data() {
      return {
        posts: [{
            "title": "Moroccan Days",
            "author": "John L",
            "category": "Travel",
            "hero": "gary-yost.jpg"
          },
          {
            "title": "Swedish Fishing",
            "author": "Rachel L",
            "category": "Leisure",
            "hero": "neckles.jpg"
          },
          {
            "title": "Paris in Spring",
            "author": "John L",
            "category": "Travel",
            "hero": "edz-norton.jpg"
          },
          {
            "title": "Youthful Independence",
            "author": "Rachel L",
            "category": "Political",
            "hero": "ksenia-yakovleva.jpg"
          },
          {
            "title": "Trial By Fire",
            "author": "Anthony R",
            "category": "Cooking",
            "hero": "long-truong.jpg"
          },
          {
            "title": "Water Ventures",
            "author": "Rachel L",
            "category": "Leisure",
            "hero": "simon-john.jpg"
          },
          {
            "title": "Mt. Zekial",
            "author": "Rachel L",
            "category": "Travel",
            "hero": "krystal-ng.jpg"
          },
          {
            "title": "Cozumel Caves",
            "author": "Rachel L",
            "category": "Travel",
            "hero": "andres-vera.jpg"
          },
          {
            "title": "Amazing Ireland",
            "author": "Rachel L",
            "category": "Travel",
            "hero": "luisana-galicia.jpg"
          },
          {
            "title": "Cabin Fever",
            "author": "Rachel L",
            "category": "Travel",
            "hero": "judith-zimmerman.jpg"
          },
          {
            "title": "To the ancient ruins",
            "author": "Rachel L",
            "category": "Travel",
            "hero": "fly-d.jpg"
          },
          {
            "title": "New fashion trends",
            "author": "Rachel L",
            "category": "Travel",
            "hero": "girl-with.jpg"
          },
          {
            "title": "Go on a vacation",
            "author": "Rachel L",
            "category": "Travel",
            "hero": "sabrianna.jpg"
          }
        ]
      }
    }
  }

</script>

<style scoped>
    .v-card {
        transition: opacity .4s ease-in-out;
    }
    .v-card:not(.on-hover) {
        opacity: 0.9;
    }
    .show-btns {
        color: rgb(245, 245, 245) !important;
    }
</style>