<template>
  <v-card class="mx-auto">
    <v-container fluid>
      <v-row dense dir="rtl" class="text-center justify-center">
        <v-col cols="6">
          <v-card class="mx-4 mb-4 pa-2" height="70%" rounded="lg">
            <v-img class="ma-2" :src="this.$route.params.product_image"
              gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)" height="60%">
            </v-img>
            <div class="title text-truncate">{{ this.$route.params.product_title }}</div>
            <div class="title text-truncate mt-4" style="color: teal">{{ this.$route.params.product_price * 50000 }}
              تومان
            </div>


            <v-btn class="mt-8 mb-2" color="orange">
              خرید
            </v-btn>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-card>
</template>

<script>
export default {
  name: 'Product',
  data() {

  },
  created() {
    console.log(this.$route.params.product_id)
  }
};
</script>

<style></style>