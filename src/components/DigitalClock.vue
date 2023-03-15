<script>
    export default{
        name: 'DigitalClock',
        mounted() { 
            setInterval(() => this.showTime(), 1000);
         },
        data() {
            return {
                hours: '',
                minutes: '',
                seconds: ''
            }
        },
        methods: {
            showTime() {
                const date = new Date();
                this.hours = date.getHours()
                this.minutes = date.getMinutes()
                this.seconds = date.getSeconds()
                console.log('Se monta el componente')
            }
        }
    }
</script>

<template>
    <span> {{ `${hours} : ${minutes} : ${seconds}`}} </span>
</template>

<style>

</style>