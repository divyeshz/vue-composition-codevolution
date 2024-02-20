<template>
    <div>
        <h2>Child Components C</h2>
        <h3>Child Components C username - {{ userName }}</h3>
        <h3>Child Components C composition username - {{ childeUserName }}</h3>

        <h3>Child Components C count - {{ childCount }}</h3>
        <h3>Child Components C hero - {{ firstName }} {{ lastName }}</h3>

        <button @click="incrementCount" >Increment Count from child</button>
    </div>
</template>

<script>
import { inject, toRefs } from 'vue'
export default {
    name: 'ChildC',
    inject: ['userName'],
    setup() {
        const childeUserName = inject('c_userName', 'Default username')
        const childCount = inject('c_count', 0)
        const childHero = inject('c_hero', {})
        const incrementCount = inject('incrementCount')

        return {
            childeUserName,
            childCount,
            ...toRefs(childHero),
            incrementCount

        }

    }
}
</script>

<style scoped></style>