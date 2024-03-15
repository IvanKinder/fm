<script lang="ts">
</script>

<template>
    <div class="modal">
        <div>Закажите обратный звонок</div>
        <div>
            <v-text-field
            :counter="10"
            label="ИМЯ"
            hide-details
            required
          ></v-text-field>
        </div>
        <div>
            <v-text-field
            :counter="10"
            label="ТЕЛЕФОН"
            hide-details
            required
          ></v-text-field>
        </div>
        <div class="check">
            <v-checkbox label="Checkbox"></v-checkbox>
            <span>Согласен на сохранение и обработку персональных данных</span>
        </div>
        <div>
            <a href="#" class="consult-btn btn-2">
                <div>
                    <span>Заказать обратный звонок</span>
                </div>
                <div>
                    <img class="arrow" src="../assets/arrow_w.svg">
                </div>
            </a>
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
    width: 50%;
    color: white;
}
.check {
    display: grid;
    grid-template-columns: 1fr 1fr;
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
.btn-2 > div > span {
    align-self: center;
    justify-self: center;
}
</style>