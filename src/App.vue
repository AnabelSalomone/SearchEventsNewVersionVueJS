<template>
  <div>
    <custom-header @see-favorites="toggleFavorites" :choice="activeList"></custom-header>
    <search @search-event="search"></search>
    <event-list v-if="activeList === 'search'" :events=filteredEvents></event-list>
    <event-list v-if="activeList === 'favorites'" events=""></event-list>
  </div>
</template>

<script>
import CustomHeader from './components/CustomHeader.vue'
import EventList from './components/EventList.vue'
import Search from './components/Search.vue'

export default {
  name: 'App',
  components: {
    CustomHeader,
    EventList,
    Search
  },
  data () {
    return {
      keyword: "",
      activeList: "search",
        events: [
            {
                id: 1,
                title: "Dire straits",
                description: "Dire straits concert",
                link: "http://www.google.fr",
            },
            {
                id: 2,
                title: "AC/DC",
                description: "AC/DC concert",
                link: "http://www.google.fr",
            },
            {
                id: 3,
                title: "Pink Floyd",
                description: "Pink Floyd concert",
                link: "http://www.google.fr",
            },
            {
                id: 4,
                title: "Rolling Stones",
                description: "Rolling Stones concert",
                link: "http://www.google.fr",
            },
        ],
        favorites: [] 
    }
  },
  computed: {
    filteredEvents(){
       let events = this.events;

       if (this.keyword.length > 0) {
         let regex = new RegExp(this.keyword, "i")
         events = this.events.filter(event => regex.test(event.title))
       }

       return events;
    }
  },
  methods: {
    search(keyword){
      this.keyword = keyword
    },
    toggleFavorites(){
      if(this.activeList === "favorites") {
        this.activeList = "search"
      } else {
        this.activeList = "favorites"
      }
    }
  }
}
</script>

<style lang="scss">
html, body {
  margin: 0
}

</style>
