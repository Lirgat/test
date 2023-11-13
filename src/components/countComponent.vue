<template>
    <div class="root">
        <section class="header">
            <h1 class="header-h1">{{ h1 }}</h1>
            <p class="header-info">{{ headerInfo }}</p>
        </section>

    </div>
</template>

<script>
export default {
    name: 'countComponent',
    data () {
        return {
            h1: 'Hello, world',
            headerInfo: 'I"m so excited! This is my first vue.js page! I am learning this framework for a better money on a work and my girlfriend dont need to work as a cashier...'
        }
    }
}
</script>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Oswald:wght@700&display=swap');
</style>
<style>
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    font-family: 'Oswald', sans-serif;
}
body {
    background-color: darkgrey;
}
.header {
    color: white;
    width: 100%;
    background-color: black;
    font-weight: bold;
    padding: 30px;
    display: flex;
    flex-direction: column;
    gap: 20px;
}
.header-h1 {
    font-size: 45px;
}
.header-info {
    width: 30%;
}
</style>