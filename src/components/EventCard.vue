<template>
  <router-link
    class="event-link"
    :to="{ name: 'EventDetails', params: { id: event.id } }"
  >
    <div class="card mb-2">
      <div class="card-body">
        <div class="card-subtitle mb-2 text-muted">
          @ {{ event.time }} on {{ event.date }}
        </div>
        <h4 class="card-title">{{ event.title }}</h4>
      </div>
    </div>
  </router-link>
</template>

<script>
export default {
  name: 'EventCard',
  props: {
    event: Object
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

.event-link {
  text-decoration: none;
}
</style>
