<template>
    <div>
        Hello {{ fullName }}
    </div>
    <button @click="sendEvent">Call Heroes</button>
</template>

<script>
import { computed } from 'vue'

export default {
    name: 'PersonGreeting',
    props: ['firstName', 'lastName'],
    setup(props, context) {
        const fullName = computed(() => {
            return `${props.firstName} ${props.lastName}`
        })

        function sendEvent() {
            context.emit('callHeroes', fullName.value)
        }

        return {
            fullName,
            sendEvent
        }
    }
    // computed: {
    //     fullName() {
    //         return `${this.firstName} ${this.lastName}`
    //     }
    // },
}
</script>

<style scoped></style>