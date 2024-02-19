<template>
    <div>
        <h2>{{ firstName }} {{ lastName }}</h2>
    </div>
</template>

<script>
import { reactive, toRefs } from 'vue'

export default {
    name: 'DemoTwo',
    setup() {
        const state = reactive({
            firstName: 'Vihang',
            lastName: 'Patel'
        })

        setTimeout(() => {
            state.firstName = 'Yash'
            state.lastName = 'Patel'
            console.log(state);
        }, 2000);

        return toRefs(state);
    }
}
</script>

<style scoped></style>