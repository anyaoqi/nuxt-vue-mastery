<template>
  <div>
    <h1>Events</h1>
    <EventCard
      v-for="(event,index) in events"
      :key="index"
      :event="event"
      :data-index="index"
    />
  </div>
</template>

<script>
import EventCard from '@/components/EventCard.vue'
import { mapState } from 'vuex';
export default {
  head(){
    return {
      title:'this is title',
      meta:[
        {
          hid:'description',
          name:'description',
          content: 'this is content'
        }
      ]

    }
  },
  components:{ EventCard },
  async fetch({ store, error }){
    try {
      await store.dispatch('events/fetchEvents')
    } catch (e) {
      error({
        statusCode: 503,
        message: '网络错误，请稍后重试'
      })
    }
  },
  computed: mapState({
    events: state => state.events.events
  })
}
</script>
