<script setup lang="ts">
</script>

<template>
    <main>
        <section>
            <h1>СОЗДАЮ УСЛОВИЯ ДЛЯ ВАШЕГО УСПЕХА</h1>
            <div class="description">
                <hr>
                <span class="small-text">Когда ваше время и энергия лучше сфокусированы, стремление к новым возможностям становится реальностью,  ваш успех зависит от ваших действий</span>
            </div>
            <div class="consult-btns">
                <a href="#" class="consult-btn btn-1">
                    <div>
                        <span>
                            Записаться на консультацию
                        </span>
                    </div>
                    <div>
                        <img class="arrow" src="../assets/arrow.svg">
                    </div>
                </a>
                <a href="#" class="consult-btn btn-2">
                    <div>
                        <span>
                            Бесплатная консультация
                        </span>
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
                        <span class="mid-text">130+</span>
                        <span class="small-text">техник для достижения целей</span>
                    </div>
                </div>
                <div>
                    <hr>
                    <div class="digits">
                        <span class="mid-text">250%</span>
                        <span class="small-text">увеличение личной продуктивности</span>

                    </div>
                </div>
            </div>
        </section>
        <img src="../assets/mentor.png" alt="mentor photo">
    </main>
</template>

<style scoped>
main {
    display: grid;
    grid-template-columns: 1fr 0.8fr;
    padding: 0 6% 0 10%;
    font-family: Raleway, sans-serif;
}
h1 {
    margin-bottom: 0;
    font-size: 2.7rem;
}
section {
    margin: 65px 0 30px 0;
    color: white;
    text-align: left;
    display: grid;
    grid-template-rows: repeat(4, max-content);
    gap: 45px;
}
main > img {
    max-height: 598px;
    justify-self: end;
}
@media (max-width: 1310px) {
    section {
        margin: 0;
    }
    main > img {
        max-height: 539px;
    }
}
@media (max-width: 1153px) {
    section {
        gap: 20px;
    }
    main > img {
        max-height: 469px;
    }
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
}
.small-text {
    color: #FFFFFF80;
    line-height: 18px;
    font-size: 16px;
}
.consult-btns {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 30px;
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
    margin-top: 25px;
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
</style>
