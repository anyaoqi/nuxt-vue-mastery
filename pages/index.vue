<template>
  <div>
    <h1>Events</h1>
    <EventCard
      v-for="(event,index) in evnents"
      :key="index"
      :event="event"
      :data-index="index"
    />
  </div>
</template>

<script>
import EventCard from '~/components/EventCard.vue'
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
  async asyncData({ $axios,error }){
    const res = await $axios.$get('http://localhost:3000/events').catch(e => {
      error({
        statusCode:503,
        message: "网络无法连接，请稍后重试"
      })
    })
    return { evnents:res }
  }
}
</script>
