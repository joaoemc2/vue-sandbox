<template>
    <div class="card-container">
        <h1 class="title">Question!</h1>
        <p class="text">Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been
            the industry's standard dummy text ever since the 1500s.</p>
        <div class="alternatives">
            <div class="alternative" @click="teste(0)">
                <div class="number">
                    <p>1</p>
                </div>
                <p class="alternative-text">{{ alternativeOne }}</p>
            </div>
            <div class="alternative " @click="teste(1)">
                <div class="number">
                    <p>2</p>
                </div>
                <p class="alternative-text">{{ alternativeTwo }}</p>
            </div>
            <div class="alternative" @click="teste(2)">
                <div class="number">
                    <p>3</p>
                </div>
                <p class="alternative-text">{{ alternativeTree }}</p>
            </div>
            <div class="alternative" @click="teste(3)">
                <div class="number">
                    <p>4</p>
                </div>
                <p class="alternative-text">{{ alternativeFour }}</p>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    name: "QuizSimulador",
    data() {
        return {
            id: 0,
            alternativeOne: "",
            alternativeTwo: "",
            alternativeTree: "",
            alternativeFour: "",

            questions: [
                {
                    id: 0,
                    texto: "Loren ipsum",

                    alternative1: "alternativa 1",
                    alternative2: "alternativa 2",
                    alternative3: "alternativa 3",
                    alternative4: "alternativa 4",

                    callback: [1, 2, 1, 4]
                },
                {
                    id: 1,
                    texto: "Loren ipsum 1",

                    alternative1: "alternativa1 1",
                    alternative2: "alternativa1 2",
                    alternative3: "alternativa1 3",
                    alternative4: "alternativa1 4",

                    callback: [1, 2, 4, 0]
                },
            ],
        }
    },
    methods: {
        teste(numero) {
            this.id = this.questions[this.id].callback[numero]
            console.log(this.id)

            this.alternativeOne = this.questions[this.id].alternative1
            this.alternativeTwo = this.questions[this.id].alternative2
            this.alternativeTree = this.questions[this.id].alternative3
            this.alternativeFour = this.questions[this.id].alternative4


        },
        iniciarQuiz() {
            this.alternativeOne = this.questions[0].alternative1
            this.alternativeTwo = this.questions[0].alternative2
            this.alternativeTree = this.questions[0].alternative3
            this.alternativeFour = this.questions[0].alternative4
        }

    },
    mounted() {
        this.iniciarQuiz()
    }
}
</script>

<style scoped>
.card-container {
    background-color: #fff;
    width: 570px;
    height: 700px;
    margin-left: 250px;
    border-radius: 32px;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 38px;
}

.text {
    width: 553px;
    margin-bottom: 36px;
}

.alternative {
    background-color: #DFFFFD;
    border-radius: 13px;
    width: 553px;
    height: 65px;
    margin-bottom: 12px;
    display: flex;
    align-items: center;
    transition: .3s;
}

.alternative:hover {
    background-color: #befdf9;
}

.number {
    background-color: #8CEBE4;
    width: 30px;
    height: 30px;
    border-radius: 100px;
    display: flex;
    justify-content: center;
    align-items: center;
    margin-left: 12px;
}

.alternative-text {
    margin-left: 38px;
}

.btn {
    padding: 16px 220px;
    font-size: 16px;
    font-weight: 700;
    border-radius: 12px;
    border: none;
    color: rgb(22, 22, 22);
    background-color: aqua;
    margin-bottom: 22px;
}
</style> 