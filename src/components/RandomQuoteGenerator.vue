
<script setup>
import { ref, onMounted } from "vue";



const quotes = ref([

    {
        text: "Bu tatil nerden baksan 5000 dolgu",
        author: "Samed Ali Eren",
    },
    {
        text:"Bak gözüm düşüyor",
        author: "Ceyda Elbir",
    },
    {
        text: "Gudubet Garı",
        author: "Akif Akaroğlu",
    },
    {
        text:"İçim geçivermiş",
        author: "Kadriye Akaroğlu"
    },
    {
        text:"Erkeklerin hepsi ölse keşke Batucum hariç",
        author: "Dirim Yönden"
    },
    {
        text:"Ah şu bi satılsa rahatlıcam",
        author: "İnanç Berkay"
    },
    {
        text:"Seni Sikerim Aslanım",
        author: "Anıl Akaroğlu"
    },
])

const currentQuote = ref ({text:'',author:''})

const getRandomQuote = ()  => {
    const randomIndex = Math.floor(Math.random()*quotes.value.length)
    currentQuote.value = quotes.value[randomIndex]
}

onMounted(getRandomQuote)

</script>


<template>
    <div class="quote-generator">
        <h1 class="app-title">Yüce Alıntılar</h1>
        <blockquote class="quote-container">
            <p>{{ currentQuote.text }}</p>
            <cite>
                {{ currentQuote.author }}
            </cite> <!--Alıntılarda kullanılıe genellikle italic yazılır-->
        </blockquote>

        <button @click="getRandomQuote" class="quote-button">Özlü sözlerimizden yararlan</button>
    </div>
</template>

<style>

.quote-generator {
    max-width: 400px;
    margin: 50px auto;
    padding: 20px;
    text-align: center;
    border: 1px solid #ccc;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

.app-title{
    font-size: 24px;
    margin-bottom: 20px;
    color: #333;
}

.quote-container {
    background-color: #f9f9f9;
    padding: 20px;
    border-radius: 8px;
    border: 1px solid #ddd;
    margin-bottom: 20px;
}

p{
    font-size: 18px;
    margin-bottom: 10px;
}

cite{
    font-style: normal;
    color: #777;
    opacity: .75;
}

.quote-button{
    padding: 10px 20px;
    font-size: 16px;
    background-color: #3498db;
    color: #fff;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

.quote-button:hover {
    background-color: #2980b9;

}

</style>