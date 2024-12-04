<script>
import { Booking } from "@dhx/trial-booking";
import "@dhx/trial-booking/dist/booking.css";

export default {
    props: ["data"],

    mounted() {
        this.booking = new Booking(this.$refs.container, {
            data: this.data,
        });
    },

    unmounted() {
        this.booking.destructor();
    }
};
</script>

<template>
    <div ref="container" class="widget"></div>
</template>
