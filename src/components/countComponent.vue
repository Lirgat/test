<template>
    <div class="root">
        <header class="header">
            <h1 class="header-h1">{{ h1 }}</h1>
            <p class="header-info">{{ headerInfo }}</p>
        </header>
        <main class="main-section">
            <article class="main-article">
                <h1 class="main-h1">{{ mainH1 }}</h1>
                <div class="main-count border-block">
                    <p class="main-count__p border-block__insideName">Попробуй функцию!</p>
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
            </article>
            <article class="main-article">
                <h1 class="main-h1">Функция вывода написанного на экран</h1>
                <div class="main-input border-block">
                    <label class="input__name border-block__insideName">Введите данные</label>
                    <input placeholder="Сюда вот)" сlass="input"
                    type="text"
                    :value="text"
                    @input="textInput($event.target.value)"
                    >
                <p class="output">{{ text }}</p>
                </div>
            </article>
            <article class="main-article">
                <h1 class="main-h1">Функция поиска по списку</h1>
                <div class="main-input border-block">
                    <label class="input__name border-block__insideName">Найдите то, что искали</label>
                    <input сlass="cool-input" type="text" @input="searchText = $event.target.value">
                    <p class="fullStuff">Всего барахла: {{ stuffs.length }}, совпадений: {{  getFilteredStuff.length }}</p>
                    <ul class="list">
                        <li
                        v-for="(stuff, index) in getFilteredStuff"
                        :key="index"
                        >
                        {{ stuff }}
                        </li>
                    </ul>
                </div>
            </article>
        </main>
        <footer class="footer">
        </footer>
    </div>
</template>

<script>
export default {
    name: 'countComponent',
    data () {
        return {
            h1: 'Привет, всем!',
            headerInfo: 'Моя страница на Vue.js, которая будет содержать различные функции. Всё что здесь есть - будет на Vue.js',
            mainH1: 'Функция счёта',
            count: 1, 
            maxCount: 10,
            minCount: 1,
            text: '',
            searchText: '',
            stuffs: ['Манка', 'Шоколадка', 'Утка', 'Гречка', 'Топор', 'Пиво', 'Крапива', 'Отвёртка', 'Кумыс', 'Утюг', 'Трансиллюминатор кожи', 'SEGA', 'Яйцо', 'Решётка', 'Граната']
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
        },
        textInput(value) {
            this.text = value
        }
    },
    computed: {
        getFilteredStuff() {
            return this.stuffs.filter(stuff => stuff.toLowerCase().includes(this.searchText.toLowerCase()))
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
    position: sticky;
}
.header-h1 {
    font-size: 85px;
    background-color: black;
    color: white;
    padding: 20px;
}
.header-info {
    font-size: 35px;
    padding: 20px;
}
.main-section {
    display: flex;
    flex-direction: column;
    gap: 100px;
}
.main-article {
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
.main-count, .border-block {
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
.main-count__p, .border-block__insideName {
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
.main-count__block_input, .input {
    font-size: 50px;
    text-align: center;
    border: 3px solid black;
    
}
.button:hover {
    color: red;
    transition: 0.5s;
}
.output {
    font-size: 35px;
    color: rgb(255, 72, 72);
}
.fullStuff, .list {
    font-size: 25px;
}
.list {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    gap: 40px;
    max-height: 222px;
}
</style>