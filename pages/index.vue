<template>
  <div>
    <v-container>
      <v-row>
        <v-col sm="6" md="4" v-for="meat in meats" :key=meat.date>
          <cook-card :data="meat" />
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        sheet: false,
      tiles: [
        { img: 'keep.png', title: 'Keep' },
        { img: 'inbox.png', title: 'Inbox' },
        { img: 'hangouts.png', title: 'Hangouts' },
        { img: 'messenger.png', title: 'Messenger' },
        { img: 'google.png', title: 'Google+' },
      ],
      }
    },
    async asyncData ( {$content} ){
      const meats = await $content('cooks').fetch()
      return {
        meats
      }
    }
  }
</script>

<style lang="scss" scoped>

</style>