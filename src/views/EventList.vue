<template>
  <h1>Events For Good</h1>
  <div class="events">
    <EventCard v-for="event in events" :key="event.id" :event="event" />
  </div>
</template>

<script>
import EventService from '@/services/EventService'
import EventCard from '@/components/EventCard.vue'

export default {
  name: 'EventList',
  components: {
    EventCard
  },
  data() {
    return {
      events: null
    }
  },
  async created() {
    try {
      const { data } = await EventService.getEvents()
      this.events = data
    } catch (e) {
      console.log(e)
    }
  }
}
</script>

<style scoped>
.events {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
