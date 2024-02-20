<template>
    <div>
        <!-- Options API -->
        <input type="text" placeholder="Name" v-model="name">
        <hr>
        <input type="text" placeholder="First Name" v-model="firstName">
        <input type="text" placeholder="Last Name" v-model="lastName">
    </div>
</template>

<script>
import { ref, watch } from 'vue'

export default {
    name: 'Watch',
    setup() {
        const firstName = ref('')
        const lastName = ref('Mepal')

        watch([firstName, lastName], (newValues, oldValues) => {
            console.log('firstName Old value', oldValues[0]);
            console.log('firstName New value', newValues[0]);
            console.log('lastName Old value', oldValues[1]);
            console.log('lastName New value', newValues[1]);
        }, {
            immediate: true,
        })

        return {
            firstName,
            lastName
        }

    },
    data() {
        return {
            name: '',
        }
    },
    watch: {
        name(newValue, oldValue) {
            console.log('Old value', oldValue);
            console.log('New value', newValue);

        }
    },
} 
</script>

<style scoped></style>