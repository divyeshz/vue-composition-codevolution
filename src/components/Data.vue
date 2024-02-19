<template>
    <div>
        <h2>Options - {{ o_firstName }}</h2>
        <h2>Composition - {{ c_firstName }}</h2>
        <h2>Composition - {{ greet }}</h2>
    </div>
</template>

<script>
import { ref } from 'vue'

export default {
    name: 'DataComponent',
    setup() {
        const c_firstName = ref('Mepal')
        c_firstName.value = 'Patel'
        const greet = `Hello ${c_firstName.value}`
        console.log('c_firstName', c_firstName);

        return {
            c_firstName,
            greet
        }
    },
    data() {
        return {
            o_firstName: 'Divyesh',
        }
    },
}
</script>

<style scoped></style>