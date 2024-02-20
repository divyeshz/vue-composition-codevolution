<template>
    <div>
        <h3>Parent component {{ name }}</h3>
        <h3>Parent component count {{ count }}</h3>
        <h3>Parent component hero {{ firstName }} {{ lastName }}</h3>

        <button @click="incrementCount">Increment count</button>
        <ChildA />
    </div>
</template>

<script>
import { provide, ref, reactive, toRefs } from 'vue'
import ChildA from "./ChildA.vue";

export default {
    name: 'ProvideInject',
    components: {
        ChildA,
    },
    setup() {
        provide('c_userName', 'Mepal')

        function incrementCount() {
            count.value++
        }

        const count = ref(0)

        const state = reactive({
            firstName: 'New',
            lastName: 'Demo',
        })

        provide('c_count', count)
        provide('c_hero', state)
        provide('incrementCount', incrementCount)

        return {
            count,
            ...toRefs(state),
            incrementCount
        }
    },
    data() {
        return {
            name: 'Divyesh'
        }
    },
    provide() {
        return {
            userName: this.name,
        }
    }
}
</script>

<style scoped></style>