<template>
  <div v-if="event">
    <h1>{{ event.title }}</h1>
    <p>{{ event.description }}</p>
  </div>
</template>

<script>
import EventService from '../services/EventService'

export default {
  data() {
    return {
      event: null
    }
  },
  async created() {
    try {
      const { data } = await EventService.getEvent(this.$route.params.id)
      this.event = data
    } catch (e) {
      console.log(e)
    }
  }
}
</script>
