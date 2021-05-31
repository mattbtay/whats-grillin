<template>
    <v-card
    :loading="loading"
    class="mx-auto my-12"
    max-width="374"
    @click="viewItem"
  >
    <template slot="progress">
      <v-progress-linear
        color="deep-purple"
        height="10"
        indeterminate
      ></v-progress-linear>
    </template>

    <v-img
      height="250"
      src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
      
    ></v-img>

    <!-- <v-card-title>{{data.type}}</v-card-title> -->

    <!-- <v-card-text>
      <v-row
        align="center"
        class="mx-0 pb-5"
      >
        <v-rating
          :value="data.rating"
          color="amber"
          dense
          half-increments
          readonly
          size="14"
        ></v-rating>
        <div class="grey--text ms-4">
          {{data.rating}} (1)
        </div>
      </v-row>

    </v-card-text> -->


    
  </v-card>
</template>

<script>
    export default {
      props: {
       data: {
         required:true,
         type:Object
       }
      },
    data: () => ({
      loading: false,
      selection: 1,
    }),

    methods: {
      reserve () {
        this.loading = true
        setTimeout(() => (this.loading = false), 2000)
      },
      addItem(){
        console.log('do something')
      },
      viewItem($event){
        // debugger
        console.log(this.data.type)
      }
    },
  }
</script>

<style lang="scss" scoped>

</style>