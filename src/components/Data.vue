<template>
    <div>
        <h2>Options - {{ o_firstName }}</h2>
        <h2>Options - {{ o_firstName }} {{ o_lastName }} a.k.a {{ o_heroName }}</h2>

        <h2>Composition - {{ c_firstName }}</h2>
        <h2>Composition - {{ greet }}</h2>

        <h2>Composition - {{ c_firstName }} {{ c_lastName }} a.k.a {{ c_heroName }}</h2>
        <h2>Composition - {{ greetHero }}</h2>

        <h2>Composition - {{ state.firstName }} {{ state.lastName }} {{ state.heroName }}</h2>
        <h2>Composition - {{ reactiveGreetHero }}</h2>

    </div>
</template>

<script>
import { ref, reactive } from 'vue'

export default {
    name: 'DataComponent',
    setup() {
        const c_firstName = ref('Neel')
        const c_lastName = ref('Joshi')
        const c_heroName = ref('Raju')

        const greet = `Hello ${c_firstName.value}`
        const greetHero = `Hello ${c_firstName.value} ${c_lastName.value} a.k.a ${c_heroName.value}`

        const state = reactive({
            firstName: 'Vihang',
            lastName: 'Patel',
            heroName: 'Shyam',
        })

        const reactiveGreetHero = `Hello ${state.firstName} ${state.lastName} a.k.a ${state.heroName}`

        return {
            c_firstName,
            c_lastName,
            c_heroName,
            greet,
            greetHero,
            state,
            reactiveGreetHero
        }
    },
    data() {
        return {
            o_firstName: 'Divyesh',
            o_lastName: 'Mepal',
            o_heroName: 'Dino James',

        }
    },
}
</script>

<style scoped></style>