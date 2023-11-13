<template>
    <div class="root">
        <section class="header">
            <h1 class="header-h1">{{ h1 }}</h1>
            <p class="header-info">{{ headerInfo }}</p>
        </section>
        <section class="main-section">
            <h1 class="main-h1">{{ mainH1 }}</h1>
        </section>
    </div>
</template>

<script>
export default {
    name: 'countComponent',
    data () {
        return {
            h1: 'Hello, world!',
            headerInfo: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Beatae dignissimos, ab qui officia consectetur vitae sequi, voluptatibus suscipit distinctio perspiciatis veritatis facere quis illo tempora aspernatur aperiam maxime eaque totam?',
            mainH1: 'Count Function'
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
    background-color: rgb(240, 240, 240);
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
    font-size: 85px;
}
.header-info {
    width: 50%;
    font-size: 35px;
}
.main-section {
    display: flex;
    flex-direction: column;
    gap: 20px;
    justify-content: center;
    align-items: center;
    margin-top: 40px;
}
.main-h1 {
    font-size: 60px;
}
</style>