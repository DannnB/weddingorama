<template>
  <div class="home">
    <h1>Online RSPVs and wedding infomation is open from Monday the 7th of June 2021</h1>
    <h2>Please come back on or after this date to fill in the RSPV form.</h2>
    <!-- <Header /> -->
    <!-- <SMS /> -->
    <!-- <RSVP /> -->
    <!-- <Location /> -->
    <!-- <Schedule /> -->
    <!-- <Gifts /> -->
    <!-- <Party /> -->
    <!-- <QnA /> -->
  </div>
</template>

<script>
// @ is an alias to /src
import Header from '@/components/Header.vue'
import SMS from '@/components/SMS.vue'
import RSVP from '@/components/RSVP.vue'
import Location from '@/components/Location.vue'
import Schedule from '@/components/Schedule.vue'
import Gifts from '@/components/Gifts.vue'
import Party from '@/components/Party.vue'
import QnA from '@/components/QnA.vue'

export default {
  name: 'Home',
  components: {
    Header,
    SMS,
    RSVP,
    Location,
    Schedule,
    Gifts,
    Party,
    QnA,
  }
}
</script>

<style lang="scss">
body {
  font-size: 16px;
  margin: 0;
}
section {
  padding: 30px 10px;
}
ul {
  list-style: none;
  padding: 0
}
</style>