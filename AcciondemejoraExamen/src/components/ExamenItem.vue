<template>
    <h2>{{ examen.title }}</h2>
    <select @change="consola(selectedOption)" v-model="selectedOption">
        <option v-for="(option,index) in examen.options" :key="index" :value="index + 1">{{ option }}</option>
    </select>
    <p>Respuesta  {{ selectedOption }}</p>
</template>
<script lang="ts" setup>
import {ref} from 'vue';
import type { IExamen } from '@/interfaces/IExamen';
const { examen } = defineProps(['examen']);
const selectedOption = ref<number>(examen.answer);

const consola = (index: number) => {
    console.log(`Pregunta ID: ${examen.id}, Opción seleccionada: ${index}`);
};

</script>
<style scoped>
    .formulario{
        width: 500px;
        height: 360px;
    }
    .errorAp, .ApLargo, .errorte, .NLargo, .tel{
        color: red;
    }
    input{
        width: 60%;
        height: 28px;
        border-radius: 50px;
        border: none;
        background-color: cadetblue;
    }
.otro{
    margin-top: 10px;
    width: 60%;
}
    span{
        width: 100%;
        display: block;
    }
    select{
        width: 60%;
        height: 25px;
        border-radius: 100px;
        border: none;
        background-color: cadetblue;
    }

    option{
        font-size: 15px;
        text-align: center;
    }
    h3{
        font-size: 13px;
    }
    button{
        display: flex;
        width: 100px;
        border-radius: 20px;
        border: none;
        margin-top: 20px;
        margin-left: 40%;
        margin-bottom: 40px;
}
button:hover{
    cursor: pointer;
    background-color: cornflowerblue;
}
</style>