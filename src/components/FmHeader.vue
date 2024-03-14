<script setup lang="ts">
</script>

<template>
    <header>
        <nav class="top-menu">
            <img class="touchable" src="../assets/logo.svg" alt="alex.shevtsov">
            <ul>
                <li class="touchable">Обо мне</li>
                <li class="touchable">Наставничество</li>
                <li class="touchable">Мероприятия</li>
                <li class="touchable">Кейсы</li>
                <li class="touchable">Отзывы</li>
                <li class="touchable">Контакты</li>
            </ul>
            <div class="contacts touchable">
                <img src="../assets/call.svg">
                <span>8-345-123-34-45</span>
            </div>
        </nav>
    </header>
</template>

<style scoped>
header {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    color: white;
}
ul {
    list-style-type: none;
    display: grid;
    grid-template-columns: repeat(6, max-content);
    gap: 1.5rem;
    font-size: small;
    padding-inline-start: 0;
    justify-self: center;
}
img {
    justify-self: end;
    align-self: center;
}
.top-menu {
    display: grid;
    grid-template-columns: max-content 1fr max-content;
    padding: 2rem 10rem;
}
.contacts {
    display: grid;
    grid-template-columns: 1fr 3fr;
    justify-self: start;
    gap: 1.2rem;
}
.contacts > span {
    align-self: center;
    font-weight: 600;
}
.contacts > img {
    justify-self: end;
}
.touchable {
    cursor: pointer;
}
</style>
