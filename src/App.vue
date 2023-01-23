<template>
    <div class="q1" v-if="status==1">
        <h4>1. Чувствуете ли вы слабость?</h4>
        <ul class="options">
            <input id="1-1" type="radio" name="q1" value="Эндокринолог" v-model="option1"><label for="1-1">Усталость</label><br>
            <input id="1-2" type="radio" name="q1" value="Эндокринолог" v-model="option1"><label for="1-2">Апатия</label>
        </ul>
        <button type="button" v-on:click="options.push(option1)" @click="check">Дальше</button>
    </div>

    <div class="q2" v-if="status==2">
        <h4>2. Чувствуете ли вы депрессию?</h4>
        <ul class="options">
            <input id="2-1" type="radio" name="q2" value="Эндокринолог" v-model="option2"><label for="2-1">Да</label><br>
            <input id="2-2" type="radio" name="q2" value="Невропатолог" v-model="option2"><label for="2-2">Нет</label>
        </ul>
        <button type="button" v-on:click="options.push(option2)" @click="check">Дальше</button>
    </div>

    <div class="q3" v-if="status==3">
        <h4>3. Чувствуете ли вы бессонницу?</h4>
        <ul class="options">
            <input id="3-1" type="radio" name="q3" value="Невропатолог" v-model="option3"><label for="3-1">Да</label><br>
            <input id="3-2" type="radio" name="q3" value="Эндокринолог" v-model="option3"><label for="3-2">Нет</label>
        </ul>
        <button type="button" v-on:click="options.push(option3)" @click="check">Дальше</button>
    </div>

    <div class="q4" v-if="status==4">
        <h4>4. Чувствуете ли вы зябкость?</h4>
        <ul class="options">
            <input id="4-1" type="radio" name="q4" value="Эндокринолог" v-model="option4"><label for="4-1">Утром</label><br>
            <input id="4-2" type="radio" name="q4" value="Кардиолог" v-model="option4"><label for="4-2">Вечером</label><br>
            <input id="4-3" type="radio" name="q4" value="Кардиолог" v-model="option4"><label for="4-3">Постоянно</label>
        </ul>
        <button type="button" v-on:click="options.push(option4)" @click="check">Дальше</button>
    </div>

    <div class="q5" v-if="status==5">
        <h4>5. Чувствуете ли вы вялость?</h4>
        <ul class="options">
            <input id="5-1" type="radio" name="q5" value="Эндокринолог" v-model="option5"><label for="5-1">Утром</label><br>
            <input id="5-2" type="radio" name="q5" value="Кардиолог" v-model="option5"><label for="5-2">Вечером</label><br>
            <input id="5-3" type="radio" name="q5" value="Невропатолог" v-model="option5"><label for="5-3">Постоянно</label>
        </ul>
        <button type="button" v-on:click="options.push(option5)" @click="check">Дальше</button>
    </div>

    <div class="q6" v-if="status==6">
        <h4>6. Когда вы чувствуете сонливость?</h4>
        <ul class="options">
            <input id="6-1" type="radio" name="q6" value="Эндокринолог" v-model="option6"><label for="6-1">Утром</label><br>
            <input id="6-2" type="radio" name="q6" value="Эндокринолог" v-model="option6"><label for="6-2">Вечером</label><br>
            <input id="6-3" type="radio" name="q6" value="Невропатолог" v-model="option6"><label for="6-3">Постоянно</label>
        </ul>
        <button type="button" v-on:click="options.push(option6)" @click="check">Дальше</button>
    </div>

    <div class="q7" v-if="status==7">
        <h4>7. Как вы чувствуете прибавку массы тела?</h4>
        <ul class="options">
            <input id="7-1" type="radio" name="q7" value="Кардиолог" v-model="option7"><label for="7-1">Плотные отеки на лице утром</label><br>
            <input id="7-2" type="radio" name="q7" value="Кардиолог" v-model="option7"><label for="7-2">Плотные отеки по всему телу вечером</label><br>
            <input id="7-3" type="radio" name="q7" value="Эндокринолог" v-model="option7"><label for="7-3">Отеков нет</label>
        </ul>
        <button type="button" v-on:click="options.push(option7)" @click="check">Дальше</button>
    </div>

    <div class="q8" v-if="status==8">
        <h4>8. Когда вы чувствуете онимение пальцев?</h4>
        <ul class="options">
            <input id="8-1" type="radio" name="q8" value="Невропатолог" v-model="option8"><label for="8-1">Связанно со стрессом</label><br>
            <input id="8-2" type="radio" name="q8" value="Эндокринолог" v-model="option8"><label for="8-2">Независимо от стресса</label>
        </ul>
        <button type="button" v-on:click="options.push(option8)" @click="check">Дальше</button>
    </div>

    <div class="q9" v-if="status==9">
        <h4>9. Когда вы чувствуете запоры?</h4>
        <ul class="options">
            <input id="9-1" type="radio" name="q9" value="Эндокринолог" v-model="option9"><label for="9-1">Постоянно</label><br>
            <input id="9-2" type="radio" name="q9" value="Гастроэнтеролог" v-model="option9"><label for="9-2">С приемом пищи</label>
        </ul>
        <button type="button" v-on:click="options.push(option9)" @click="check">Дальше</button>
    </div>

    <div class="q10" v-if="status==10">
        <h4>10. Когда вы чувствуете выпадение волос?</h4>
        <ul class="options">
            <input id="10-1" type="radio" name="q10" value="Терапевт" v-model="option10"><label for="10-1">С приемом препаратов</label><br>
            <input id="10-2" type="radio" name="q10" value="Эндокринолог" v-model="option10"><label for="10-2">Постоянно</label>
        </ul>
        <button type="button" v-on:click="options.push(option10)" @click="check">Дальше</button>
    </div>

    <div class="q11" v-if="status==11">
        <h4>11. Какое чувство боли в сердце у вас?</h4>
        <ul class="options">
            <input id="11-1" type="radio" name="q11" value="Кардиолог" v-model="option11"><label for="11-1">Учащение ритма</label><br>
            <input id="11-2" type="radio" name="q11" value="Эндокринолог" v-model="option11"><label for="11-2">Замедление ритма</label><br>
            <input id="11-3" type="radio" name="q11" value="Невропатолог" v-model="option11"><label for="11-3">Просто боль</label>
        </ul>
        <button type="button" v-on:click="options.push(option11)" @click="check">Дальше</button>
    </div>

    <div class="q12" v-if="status==12">
        <h4>12. Какие виды судороги у вас?</h4>
        <ul class="options">
            <input id="12-1" type="radio" name="q12" value="Эндокринолог" v-model="option12"><label for="12-1">Мышечные</label><br>
            <input id="12-2" type="radio" name="q12" value="Невропатолог" v-model="option12"><label for="12-2">Эпилептические</label>
        </ul>
        <button type="button" v-on:click="options.push(option12)" @click="check">Дальше</button>
    </div>

    <div class="q13" v-if="status==13">
        <h4>13. Когда вы чувствуете нарушение менструального цикла?</h4>
        <ul class="options">
            <input id="13-1" type="radio" name="q13" value="Гинеколог" v-model="option13"><label for="13-1">С приемом препаратов</label><br>
            <input id="13-2" type="radio" name="q13" value="Эндокринолог" v-model="option13"><label for="13-2">Не связанно, возрастное</label><br>
            <input id="13-3" type="radio" name="q13" value="Гинеколог" v-model="option13"><label for="13-3">Периодически</label>
        </ul>
        <button type="button" v-on:click="options.push(option13)" @click="check">Дальше</button>
    </div>

    <div class="results" v-if="status==14">
        <h4>Вам нужно обратиться к следующим специалистам:</h4>
        <ul v-for="item in [...new Set(options)]">{{item}}</ul>
        <button type="button" @click="reloadPage">Пройти заново</button>
    </div>
    
    <div class="alert">
        <h4 v-if="missing==1">Вы не выбрали ответ!</h4>
    </div>

</template>
<script>
    export default {
        name: 'app',
        data (){
            return{
                options: [],
                status: 1,
                missing: 0
            }
        },
        methods: {
            reloadPage(){
                window.location.reload();
            },
            check(){
                if (this.options[this.options.length-1]==null){
                    this.missing = 1;
                }
                else{
                    this.status = this.status + 1;
                    this.missing = 0;
                }
            }
        }
        
    }
</script>
<style>
    #app{
        margin-left: 5%;
    }
    .alert{
        color: tomato;
    }
</style>