<template>
    <div class="box">
        <h5>Advice #{{adviceId}}</h5>
        <p>"{{adviceMessage}}"</p>
        <button class="btn" @click="getAdvice()"><img class="icon" src="../assets/icon-dice.svg" alt="Random"/> </button>
    </div>
</template>
<script>
import axios from 'axios';
export default{
    name:'AdviceBox',
    data(){
        return{
            adviceMessage: null,
            adviceId : null
        }
    },
    mounted(){
        this.getAdvice();
    },
    methods: {
        getAdvice(){
            axios.get('https://api.adviceslip.com/advice')
            .then(response => (
            this.adviceId=response.data.slip.id,
            this.adviceMessage=response.data.slip.advice
            ))
        }
    }
}
</script>
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Manrope:wght@800&display=swap');
h5{
    color: hsl(150, 100%, 66%);
}
.icon{
    margin-top: 16px;
}
.box{
    font-family: 'Manrope', sans-serif;
    background-color: hsl(217, 19%, 24%);
    border-radius: 10px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 20px;
    width: 400px;
}
.btn{
    background-color: hsl(150, 100%, 66%);
    width: 60px;
    height: 60px;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    position: relative;
    top: 50px;
}
button{
    border: none;
    background: none;
    padding: none;
    cursor: pointer;
    /* filter: drop-shadow(0 0 30px red); */
}
button.btn:hover {
    box-shadow: 0 0 20px 10px green;
}
p{
    color: white;
    text-align: center;
}
</style>