<script>
import Booking from "./components/Booking.vue";
import { getData } from "./data";

export default {
    components: { Booking },
    data() {
        const dataset = getData();
        return { dataset };
    },
};
</script>

<template>
    <Booking :data="dataset" />
</template>
