<template>
  <div>
    <h1>Events</h1>
    <div class="events">
      <EventCard
        v-for="event in events"
        :key="event.id"
        :event="event"
      />
  </div>
  </div>
</template>

<script>
import {mapState} from 'vuex'
import EventCard from '@/components/EventCard.vue'

export default {
  name: 'IndexPage',
  components: {
    EventCard,
  },
  async fetch({  store,error }) {
    try {
      await store.dispatch('event/fetchEvents')
    } catch (e) {
      error({ statusCode: 503, message: 'No Events available,try again' })
    }
  },
  head() {
    return {
      title: 'EventListing - Home',
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        {
          hid: 'description',
          name: 'description',
          content: 'Event Listing Home Page Description goes here',
        },
      ],
    }
  },
  computed: {
   ...mapState('event', ['events']),
  },
}
</script>
