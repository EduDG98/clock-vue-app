<script>
    export default{
        name: 'DigitalClock',
        mounted() { 
            setInterval(() => this.showTime(), 1000);
         },
        data() {
            return {
                hours: '00',
                minutes: '00',
                seconds: '00',
                period: '---'

            }
        },
        methods: {
            showTime() {
                const date = new Date();
                let hours = date.getHours();
                let minutes = date.getMinutes();
                let seconds = date.getSeconds();

                hours = this.showWithZero(hours);
                minutes = this.showWithZero(minutes);
                seconds = this.showWithZero(seconds);
                
                this.hours = hours;
                this.minutes = minutes;
                this.seconds = seconds;
                
                this.period = this.hours < 12 ? 'AM' : 'PM';
            },
            showWithZero(num) {
                return num = num <= 9 ? num.toString().padStart(2, 0) : num;
            }
        }
    }
</script>

<template>
    <span> {{ `${hours} : ${minutes} : ${seconds} ${period}`}} </span>
</template>

<style>
    span {
        background-color: black;
        padding: 20px;
        border: 2px solid palevioletred;
        border-radius: 10px;
        color: goldenrod;
        font-size: 60px;
    }
</style>