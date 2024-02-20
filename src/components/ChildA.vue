<template>
    <div>
        <h2>Child Components A</h2>
        <ChildB />
    </div>
</template>

<script>
import ChildB from "./ChildB.vue";
export default {
    name: 'ChildA',
    components: {
        ChildB
    },
    data() {
        return {

        }
    },
}
</script>

<style scoped></style>