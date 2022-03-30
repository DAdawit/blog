<template>
  <div>
    <base-card dark>
      <v-img :src="require('@/assets/articles/jewelry_banner.jpg')" class="grey lighten-2" height="500" width="100%">
        <v-row class="fill-height pa-3" align="center">
          <v-col cols="12" md="7" offset-md="5">
            <h1 class="display-3 font-weight-light ml-12">
              The Art Of Travel
            </h1>
            <div class="subheading text-uppercase pl-2 mb-4 ml-12">
              Finding Beauty, One flight at a time
            </div>
          </v-col>
        </v-row>
      </v-img>
    </base-card>

    <v-container class="mt-10">
      <v-row>
        <v-col class="d-flex justify-center" sm="12" md="12" lg="12" xl="12">
          <h1 class="display-2 grey--text mb-5 text-capitalize">{{title}}</h1>
          <!-- <h1 class="display-3 grey--text text-capitalize ">{{title}}</h1> -->
        </v-col>
        <v-col class="d-flex justify-centetr" cols="12" sm="12" md="12" lg="12" xl="12">
          <p class="mx-12 grey--text pa">{{para}}</p>
        </v-col>
      </v-row>
    </v-container>

    <v-row>
      <v-col cols="12" sm="12" md="6" lg="6" xl="6">
        <v-row>
          <v-card flat tile class="mt-5">
            <div class="mx-12">
              <v-img :src="require('@/assets/articles/dan-farrell.jpg')" height="350" class="mx-18">
              </v-img>
            </div>
            <v-col class="d-flex justify-start ml-8" cols="12" sm="12" md="12" lg="12" xl="12">
              <h1 class="display-1 grey--text  text-capitalize">The Art Of Travel</h1>
            </v-col>
            <v-col class="d-flex justify-center" cols="12" sm="12" md="12" lg="12" xl="12">
              <p class="px-10 grey--text pa">
                {{para}}
              </p>
            </v-col>
          </v-card>
        </v-row>
      </v-col>

      <v-col cols="12" sm="12" md="6" lg="6" xl="6">
        <v-row>
          <v-card tile flat class="mt-5">
            <div class="mx-12">
              <v-img :src="require('@/assets/articles/fly-d.jpg')" height="350" class="mx-18">
              </v-img>
            </div>
            <v-col class="d-flex justify-start ml-8" cols="12" sm="12" md="12" lg="12" xl="12">
              <h1 class="display-1 grey--text text-capitalize">The Art Of Travel</h1>
            </v-col>
            <v-col class="d-flex justify-center" cols="12" sm="12" md="12" lg="12" xl="12">
              <p class="px-10 grey--text pa">
                {{para}}
              </p>
            </v-col>
          </v-card>
        </v-row>
      </v-col>
    </v-row>


    <!-- <v-row>
      <base-card dark>
        <v-img :src="require('@/assets/articles/ksenia-yakovleva.jpg')" class="grey lighten-2" height="470"
          width="100%">
          <v-row class="fill-height pa-3" align="center">
            <v-col cols="12" md="7" offset-md="5">
              
              <h1 class="display-3 font-weight-light ml-12">
                The Art Of Travel
              </h1>
              <div class="subheading text-uppercase pl-2 mb-4 ml-12">
                Finding Beauty, One flight at a time
              </div>
            </v-col>
          </v-row>
        </v-img>
      </base-card>
    </v-row> -->



    <!-- <div class="dave"> -->

    <v-row>
      <v-col class="d-flex justify-center">
        <h1 class="display-3 text-capitalize font-weight-medium ma-5 grey--text">Gallery</h1>
      </v-col>
    </v-row>
    <!-- </div> -->

  </div>
</template>

<script>
  export default {
    name: 'HomeBanner',
    data() {
      return {
        title: 'Where does it come from?',
        para: 'Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old. Richard McClintock, a Latin professor at Hampden-Sydney College in Virginia, looked up one of the more obscure Latin words, consectetur, from a Lorem Ipsum passage, and going through the cites of the word in classical literature, discovered the undoubtable source. Lorem Ipsum comes from sections 1.10.32 and 1.10.33 of "de Finibus Bonorum et Malorum" (The Extremes of Good and Evil) by Cicero, written in 45 BC. This book is a treatise on the theory of ethics, very popular during the Renaissance. The first line of Lorem Ipsum, "Lorem ipsum dolor sit amet..", comes from a line in section 1.10.32.'
      }
    }
  }

</script>
<style scoped>
  .tit {
    font-family: Cardo;
  }

  h1{
    font-family: Barlow_Light;
  }

</style>
