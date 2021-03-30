<template>
    <div>
        <div v-for="event in events" :key=event.id>
            <event :event=event></event>
        </div>
    </div>
</template>

<script>
import Event from './Event.vue'

export default {
    name: "EventList",
    components: {
        Event
    },
    props: ["events"]
}
</script>