<script setup lang="ts">
import { defineProps, ref } from 'vue';

interface Props {
    showConsult: Function;
}

defineProps<Props>();

const requires = (value: string) => {
    if (value) return true
    return 'Name is required.'
}

const name = ref("");
const phone = ref("");

const nameRules = [
    requires,
];
    

</script>

<template>
    <div class="modal">
        <v-btn @click="showConsult" class="close-btn" icon="$close" size="x-large" variant="text"></v-btn>
        <div class="call-back">Закажите обратный звонок</div>
        <div>
            <v-text-field
            v-model="name"
            :rules="nameRules"
            :counter="10"
            label="ИМЯ"
            hide-details
            required
          ></v-text-field>
        </div>
        <div>
            <v-text-field
            v-model="phone"
            :counter="10"
            :rules="nameRules"
            label="ТЕЛЕФОН"
            hide-details
            required
          ></v-text-field>
        </div>
        <div class="check">
            <v-checkbox label="Согласен на сохранение и обработку персональных данных"></v-checkbox>
        </div>
        <div>
            <v-btn :disabled="!(name && phone)" variant="plain" class="consult-btns">
                <div class="consult-btn btn-2">
                    <div class="new-btn">
                        <span>Заказать обратный звонок</span>
                    </div>
                    <div>
                        <img class="arrow" src="../assets/arrow_w.svg">
                    </div>
                </div>
            </v-btn>
        </div>
    </div>
</template>

<style scoped>
.modal {
    background: #0F1D45;
    position: absolute;
    left: 0;
    top: 0;
    height: 100%;
    width: 32%;
    color: white;
    display: grid;
    padding: 2%;
    font-family: Raleway, sans-serif;
    z-index: 2;
}
.close-btn {
    justify-self: end;
}
.call-back {
    text-align: left;
    font-size: xxx-large;
}
.check {
    text-align: left;
    line-height: normal;
}
.arrow {
    align-self: flex-end;
    margin: 0 8px 8px 0;
    justify-self: end;
}
.consult-btns {
    padding: 0;
    height: auto !important;
    font-size: small;
}
.consult-btn {
    display: grid;
    grid-template-columns: 4.6fr 1fr;
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
.new-btn {
    padding: 0 20px;
}
.btn-2 > div > span {
    align-self: center;
    justify-self: center;
}
@media (max-width: 320px) {
    .modal {
        width: 100%;
        padding: 4%;
    }
    .call-back {
        line-height: 30px;
        font-size: x-large;
        max-width: 200px;
    }
    .consult-btn {
        grid-template-columns: 215px 50px;
    }
    .new-btn {
        font-size: 9px;
    }
    .check {
        font-size: small;
    }
}
</style>