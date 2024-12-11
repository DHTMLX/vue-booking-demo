<script>
import { Booking } from "@dhx/trial-booking";
import "@dhx/trial-booking/dist/booking.css";

export default {
    props: ["data"],

    mounted() {
        this.booking = new Booking(this.$refs.container, {
            data: this.data,
        });

        this.booking.setConfirmHandler(function(event){
            const { confirm } = event;
            setTimeout(() => {
                Math.random() < 0.5 ? confirm.error() : confirm.done();
            }, 1000);
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
