<template>
  <v-container>
    <div class=" px-5 mb-5 ">
      <h1 class="subheading grey--text my-10 ">Blogs</h1>
      <v-item-group class="mb-5">
        <v-row class="pt-5">
          <v-col v-for="(post,index) in posts" :key="index" cols="12" sm="12" md="6" lg="4">
            <v-item cols="12" sm="6" md="6" lg="4">
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
                    </v-row>
                  </v-img>
                  <v-card-text>
                    {{para | snippet}}
                  </v-card-text>
                  <v-card-actions class="px-5">
                    <v-row>
                      <v-tooltip bottom>
                        <template v-slot:activator="{ on, attrs }">
                          <v-icon v-bind="attrs" v-on="on" href="https://www.instagram.com/dawitccnt" color="primary">
                            mdi-instagram
                          </v-icon>
                        </template>
                        <span>message on instagram</span>
                      </v-tooltip>
                      <v-tooltip bottom>
                        <template v-slot:activator="{ on, attrs }">
                          <v-icon v-bind="attrs" v-on="on" color="primary">
                            mdi-facebook
                          </v-icon>
                        </template>
                        <span>message on instagram</span>
                      </v-tooltip>
                      <v-tooltip bottom>
                        <template v-slot:activator="{ on, attrs }">
                          <v-icon v-bind="attrs" v-on="on" href="https://www.instagram.com/dawitccnt" color="primary">
                            mdi-telegram
                          </v-icon>
                        </template>
                        <span>message on instagram</span>
                      </v-tooltip>

                      <v-col class="d-flex justify-end">
                        <v-btn class="text-uppercase ma-0" color="primary" label small @click="showDescription(post)">
                          Read More
                        </v-btn>
                      </v-col>
                    </v-row>
                  </v-card-actions>
                </v-card>
              </v-hover>
            </v-item>
          </v-col>
        </v-row>
      </v-item-group>
    </div>
    <template v-if="show">
      <div class="text-center">
        <v-dialog v-model="dialog" width="95%">
          <v-card>
            <v-card-title class="text-h5 grey lighten-2">
              {{singlePost.title}}
            </v-card-title>

            <v-card-text>
              <v-row>
                <v-col cols="12" sm="12" md="6" lg="6" xl="6">
                  <v-img :src="require(`@/assets/articles/${singlePost.hero}`)" height="600"
                    gradient="rgba(0, 0, 0, .42), rgba(0, 0, 0, .42)">
                  </v-img>
                </v-col>
                <v-col cols="12" sm="12" md="6" lg="6" xl="6">
                  <v-row>
                    <v-col class="d-flex justify-center" cols="12" sm="12" md="12" lg="12" xl="12">
                      <h1 class="subheading blue-grey--text mb-5 ">{{singlePost.title}}</h1>

                    </v-col>
                    <v-col cols="12" sm="12" md="12" lg="12" xl="12">
                      <p class="subheading grey--text mb-5 ">
                        {{para}}
                      </p>
                    </v-col>
                    <v-col cols="12">
                      <h2>contact</h2>
                      <br>
                    </v-col>
                       <v-divider></v-divider>
                    <v-col class='d-flex align-end'>
                      <base-btn v-for="(item, i) in items" :key="i" :href="item.href" class="ml-0 mr-3" color="primary"
                        square target="_blank">
                        <v-icon v-text="item.icon" />
                      </base-btn>
                    </v-col>
                  </v-row>
                </v-col>
              </v-row>
            </v-card-text>
            <v-divider></v-divider>

            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn color="primary" text @click="dialog = false">
                close
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-dialog>
      </div>
    </template>

    <template>
      <div class="text-center">
        <v-pagination color="primary" v-model="page" :length="4" circle></v-pagination>
      </div>
    </template>
  </v-container>
</template>
<script>
  export default {
    methods: {
      showDescription(post) {
        this.singlePost = post;
        this.show = true;
        this.dialog = true;
      }
    },

    data() {
      return {
        page: 1,
        items: [{
            href: 'https://www.instagram.com/dawitccnt',
            icon: 'mdi-instagram',
            contactIn: 'contact in Instagram'
          },
          {
            href: 'https://www.facebook.com/dawit.love.33',
            icon: 'mdi-facebook',
            contactIn: 'contact in Facebook'

          },
          {
            href: 'https://t.me/Da_W_iT',
            icon: 'mdi-telegram',
            contactIn: 'contact in Telegram'
          },
        ],
        singlePost: {},
        dialog: false,
        show: false,
        para: 'Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old. Richard McClintock, a Latin professor at Hampden-Sydney College in Virginia, looked up one of the more obscure Latin words, consectetur, from a Lorem Ipsum passage, and going through the cites of the word in classical literature, discovered the undoubtable source. Lorem Ipsum comes from sections 1.10.32 and 1.10.33 of "de Finibus Bonorum et Malorum" (The Extremes of Good and Evil) by Cicero, written in 45 BC. This book is a treatise on the theory of ethics, very popular during the Renaissance. The first line of Lorem Ipsum, "Lorem ipsum dolor sit amet..", comes from a line in section 1.10.32.',
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
