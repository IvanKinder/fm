<script setup lang="ts">
import { computed, onMounted, ref } from 'vue';
import CallWindow from "./CallWindow.vue";
import axios from "axios";

interface Props {
    setOver: Function;
}

const props = defineProps<Props>();

const windowWidth = ref(window.innerWidth);
const showModal = ref(false);
const daily = ref(0);
const dateNum = computed(() => {
    const now = new Date();
    const d = now.getDate().toString();
    const m = now.getMonth().toString();
    const y = now.getFullYear().toString();
    const dmy = d + m + y;
    const dmyList = dmy.split("");
    const acc = dmyList.reduce((accumulator, currentValue) => {
        return (parseInt(accumulator) + parseInt(currentValue)).toString();
    }, '0');

    return acc;
});

window.addEventListener('resize', function() {
    windowWidth.value = window.innerWidth;
});

const showConsult = () => {
    props.setOver();
    showModal.value = !showModal.value;
}

onMounted(() => {
    axios.get("https://www.cbr-xml-daily.ru/daily_json.js").then((res) => {
        daily.value =  Math.round(res.data?.Valute?.GBP?.Value);
    }).catch(() => {
        daily.value = 250;
    })
})
</script>

<template>
    <main>
        <section>
            <h1>СОЗДАЮ УСЛОВИЯ ДЛЯ ВАШЕГО УСПЕХА</h1>
            <div class="description">
                <hr>
                <span v-if="windowWidth > 960" class="small-text">Когда ваше время и энергия лучше сфокусированы, стремление к новым возможностям становится реальностью,  ваш успех зависит от ваших действий</span>
                <span v-else class="small-text">Ваш успех зависит от ваших действий</span>
            </div>
            <div class="consult-btns">
                <a href="#" @click="showConsult" class="consult-btn btn-1">
                    <div>
                        <span v-if="windowWidth > 960">
                            Записаться на консультацию
                        </span>
                        <span v-else>Записаться</span>
                    </div>
                    <div>
                        <img class="arrow" src="../assets/arrow.svg">
                    </div>
                </a>
                <a href="#" @click="showConsult" class="consult-btn btn-2">
                    <div>
                        <span v-if="windowWidth > 960">
                            Бесплатная консультация
                        </span>
                        <span v-else>Заказать звонок</span>
                    </div>
                    <div>
                        <img class="arrow" src="../assets/arrow_w.svg">
                    </div>
                </a>
            </div>
            <div class="digits-container">
                <div>
                    <hr>
                    <div class="digits">
                        <span class="mid-text">{{dateNum}}+</span>
                        <span v-if="windowWidth > 960" class="small-text">техник для достижения целей</span>
                        <span v-else class="small-text">техники</span>
                    </div>
                </div>
                <div>
                    <hr>
                    <div class="digits">
                        <span class="mid-text">{{daily}}%</span>
                        <span v-if="windowWidth > 960" class="small-text">увеличение личной продуктивности</span>
                        <span v-else class="small-text">продуктивности</span>
                    </div>
                </div>
            </div>
        </section>
        <div class="mentor">
            <img src="../assets/mentor.png" alt="mentor photo">
        </div>
        <transition name="fade">
            <call-window v-if="showModal" :show-consult="showConsult"/>
        </transition>
    </main>
</template>

<style scoped>
.fade-enter-active, .fade-leave-active {
    transition: transform 0.5s;
}
.fade-enter, .fade-leave-to {
    transform: translateX(-100%);
}
main {
    display: grid;
    grid-template-columns: 1fr 0.8fr;
    padding: 0 6% 0 10%;
    font-family: Raleway, sans-serif;
}
h1 {
    margin-top: 35px;
    font-size: 2.7rem;
    width: 79%;
}
section {
    margin: 65px 0 30px 0;
    color: white;
    text-align: left;
    display: grid;
    grid-template-rows: repeat(4, max-content);
    gap: 45px;
}
.mentor {
    overflow: hidden;
    width: fit-content;
}
.mentor > img {
    max-height: 576px;
    justify-self: end;
}
.consult-btns {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 30px;
}
.description {
    display: grid;
    grid-template-columns: 1px 1fr;
    gap: 20px;
}
hr {
    margin: 0;
    font-size: 53px;
    line-height: 1.3;
    height: auto;
}
.small-text {
    color: #FFFFFF80;
    line-height: 18px;
    font-size: 16px;
}
.consult-btn {
    display: grid;
    grid-template-columns: 4.6fr 1fr;
}
.btn-1 {
    gap: 2px;
    color: #07305D;
}
.btn-2 {
    border-bottom: 1px solid white;
    border-top: 1px solid white;
    border-right: 1px solid white;
    opacity: 1;
    color: white;
}
.btn-2 > div {
    height: 55px;
    border-left: 1px solid white;
    display: grid;
}
.btn-2 > div > span {
    align-self: center;
    justify-self: center;
}
.btn-1 > div {
    text-align: center;
    background: white;
    height: 55px;
    display: grid;
}
.btn-1 > div > span {
    align-self: center;
    justify-self: center;
}
.arrow {
    align-self: flex-end;
    margin: 0 8px 8px 0;
    justify-self: end;
}
.digits-container {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 30px;
    margin-top: 35px;
}
.digits-container > div {
    display: grid;
    grid-template-columns: 1px 0.6fr;
    gap: 20px;
}
.digits {
    display: grid;
}
.mid-text {
    font-family: Montserrat, sans-serif;
    font-size: xx-large;
    line-height: normal;
}
@media (max-width: 1310px) {
    section {
        margin: 0;
    }
    .mentor > img {
        max-height: 583px;
    }
    .digits-container {
        margin: 0;
    }
}
@media (max-width: 1153px) {
    section {
        gap: 53px;
    }
    .mentor > img {
        max-height: 585px;
    }
}
@media (max-width: 960px) {
    main {
        padding: 10px 7px;
    }
    .consult-btns {
        grid-template-columns: 1fr;
        gap: 10px;
        max-width: 200px;
    }
    h1 {
        margin: 0;
        font-size: 18px;
        width: 100%;
    }
    section {
        max-width: 200px;
        grid-template-rows: max-content 36px repeat(4, max-content);
        gap: 82px;
    }
    .description {
        gap: 8px;
        font-size: 10px;
        width: 135px;
    }
    .small-text {
        font-size: 12px;
    }
    .btn-1 > div {
        height: 35px;
    }
    .btn-2 > div {
        height: 35px;
    }
    .arrow {
        width: 10px;
        margin: 0 4px 4px 0;
    }
    .digits-container {
        gap: 10px;
    }
    .digits-container > div {
        gap: 8px;
    }
}
@media (max-width: 720px) {
    .mentor {
        right: 28px;
        position: relative;
    }
    .mentor > img {
        max-height: 530px;
        position: relative;
        top: 42px;
    }
    section {
        grid-template-rows: max-content 36px repeat(2, max-content);
    }
}
</style>
