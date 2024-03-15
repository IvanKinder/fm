<script setup lang="ts">
</script>

<template>
    <header>
        <nav>
            <img src="../assets/logo.svg" alt="alex.shevtsov">
            <ul>
                <li>
                    <a class="touchable" href="#">Обо мне</a>
                </li>
                <li>
                    <a class="touchable" href="#">Наставничество</a>
                </li>
                <li>
                    <a class="touchable" href="#">Мероприятия</a>
                </li>
                <li>
                    <a class="touchable" href="#">Кейсы</a>
                </li>
                <li>
                    <a class="touchable" href="#">Отзывы</a>
                </li>
                <li>
                    <a class="touchable" href="#">Контакты</a>
                </li>
            </ul>
            <div class="contacts">
                <a class="menu" href="#">
                    <img src="../assets/menu.svg">
                </a>
                <a class="call" href="#">
                    <img src="../assets/call.svg">
                </a>
                <span>8-345-123-34-45</span>
            </div>
        </nav>
    </header>
</template>

<style scoped>
header {
    font-family: Montserrat, sans-serif;
    top: 0;
    left: 0;
    width: 80%;
    color: white;
    padding: 2% 10% 0;
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
nav > img {
    justify-self: end;
    align-self: center;
}
nav {
    display: grid;
    grid-template-columns: max-content 1fr max-content;
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
.call {
    justify-self: end;
    padding-top: 5px;
}
.touchable {
    color: white;
}
.menu {
    display: none;
}
@media (max-width: 960px) {
    nav {
        grid-template-columns: repeat(2, 1fr);
    }
    ul {
        display: none;
    }
    nav > img {
        justify-self: start;
    }
    .contacts {
        justify-self: end;
        grid-template-columns: 1fr 1fr;
    }
    .contacts > span {
        display: none;
    }
    .menu {
        display: block;
        padding-top: 5px;
    }
}
</style>
