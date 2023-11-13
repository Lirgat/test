<template>
    <div class="root">
        <section class="header">
            <h1 class="header-h1">{{ h1 }}</h1>
            <p class="header-info">{{ headerInfo }}</p>
        </section>
        <section class="main-section">
            <h1 class="main-h1">{{ mainH1 }}</h1>
            <div class="main-count">
                <p class="main-count__p">Попробуй функцию!</p>
                <div class="main-count__block">
                    <button class="button decrease" type="button" @click="decresaseCount">-</button>
                    <input class="main-count__block_input"
                    type="number" 
                    :value="count"
                    :min="minCount"
                    :max="maxCount"
                    >
                    <button class="button increase" type="button" @click="increaseCount">+</button>
                </div>
            </div>
        </section>
    </div>
</template>

<script>
export default {
    name: 'countComponent',
    data () {
        return {
            h1: 'Привет, всем!',
            headerInfo: 'Моя первая страница на Vue.js, которая будет содержать различные функции',
            mainH1: 'Функция счёта',
            count: 1, 
            maxCount: 10,
            minCount: 1
        }
    },
    methods: {
        increaseCount() {
            if (this.count < this.maxCount) {
                this.count++
            }
        }, decresaseCount() {
            if (this.count > this.minCount) {
                this.count--
            }
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
    scroll-behavior: smooth;
}
.header {
    width: 100%;
    font-weight: bold;
    display: flex;
    flex-direction: column;
    gap: 20px;
    background-color: white;
    border: 5px solid black;
}
.header-h1 {
    font-size: 85px;
    background-color: black;
    color: white;
    padding: 20px;
}
.header-info {
    width: 50%;
    font-size: 35px;
    padding: 20px;
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
    font-size: 70px;
}
.main-count {
    display: flex;
    flex-direction: column;
    gap: 30px;
    padding: 50px;
    border: 3px solid black;
    background-color: white;
    justify-content: center;
    align-items: center;
    box-shadow: 16px 18px 2px -2px rgba(0, 0, 0, 0.19);
    width: 40%;
}
.main-count__p {
    font-size: 35px;

}
.main-count__block {
     display: flex;
     flex-direction: row;
     gap: 30px;
     font-size: 50px;
}
.button {
    padding: 10px;
    font-size: 50px;
    border: none;
    background-color: white;
    cursor: pointer;
}
.main-count__block_input {
    font-size: 50px;
    text-align: center;
    border: none;
    
}
.button:hover {
    color: red;
    transition: 0.5s;
}
</style>