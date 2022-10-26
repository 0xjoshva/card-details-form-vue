<template>
  <section>
    <div class="cards">
      <div class="card"> 
        <img src="../assets/card-logo.svg" alt="">
        <p id="card-number">9238 2132 4738 120E</p>
        <div class="card-details">
        <p>QUANDALE DINGLE</p>
        <p>09/26</p>
        </div>
      </div>
      <div class="card">
        <p>420</p>
      </div>
    </div>
    <form @submit.prevent="onSubmit">
      <div class="inputs" v-show="submit === false">
      <label for="name">
        CARDHOLDER NAME <br />
        <input name="name" type="text" placeholder="e.g Quandale Dingle" required/>
      </label>
      <label for="number">
        CARD NUMBER <br />
        <input name="number" type="text" placeholder="e.g 0238 2738 2838 2821" required/>
      </label>
      <div id="details">
        <label for="date">
          EXP. DATE (MM/YY) <br />
          <div id="mmyy">
            <input name="date" type="number" placeholder="MM" min="1" max="12" required/>
            <input type="number" placeholder="YY" min="22" max="32" required/>
          </div>
        </label>
        <label for="cvc">
          CVC <br />
          <input type="text" placeholder="e.g 123"  required/>
        </label>
      </div>
      </div>
      <div v-show="submit === true" id="thanks">
        <img src="../assets/icon-complete.svg" alt="">
      <H1>THANK YOU!</H1>
      <p>We've added your card details</p>
      </div>
      <button @click="submit = true">Confirm</button>
    </form>
  </section>
</template>

<script>
export default {
  data() {
    return {
      submit: false
    }
  }
};
</script>
<style scoped>
section {
  width: 100%;
  height: 100vh;
  background-image: url(../assets/bg-main-desktop.png);
  background-repeat: no-repeat;
  background-size: 30% 100%;
  background-color: var(--white);
  display: flex;
  flex-direction: row;
  column-gap: 10rem;
  justify-content: center;
  align-items: center;
}
form {
  display: flex;
  flex-direction: column;
}
#mmyy {
  display: flex;
}
#details {
  display: flex;
}
.cards {
  display: flex;
  flex-direction: column;
  row-gap: 3rem;
}
.card:nth-child(1) {
  animation: swipe1 1s cubic-bezier(0.68, -0.55, 0.27, 1.55);
  transform: translateX(-60px);
  background: url(../assets/bg-card-front.png);
  background-repeat: none;
  width: 27.9rem;
  height: 15.3rem;
  padding: 1.5rem;
  color: var(--white);
}
#card-number{
  letter-spacing: 5px;
  font-size: 1.7rem;
  margin-top: 4.5rem;
  background: transparent;
  border-radius: 12px;
}
.card-details{
  display: flex;
  justify-content: space-between;
  font-size: 0.9rem;
  letter-spacing: 2px;
  padding-top: 1rem;
  font-weight: 400;
}
.card:nth-child(2) {
  transform: translateX(0px);
  animation: swipe2 0.6s ease-in-out;
  background: url(../assets/bg-card-back.png);
  background-repeat: none;
  width: 27.9rem;
  height: 15.3rem;
  color: var(--white);
}
.card:nth-child(2) p{
    font-size: 1rem;
    transform: translate(360px, 110px);
    letter-spacing: 3px;
    width: fit-content;

}
.card{
  transition: .2s ease-in-out all;
}
.card:hover{
  scale: 1.1;
}
@keyframes swipe1 {
  0% {
    transform: translateX(-500px);
    opacity: 0.4;
  }
  100% {
    transform: translateX(-60px);
    opacity: 1;
  }
}
@keyframes swipe2 {
  0% {
    transform: translateX(100px);
    opacity: 1;
  }
  100% {
    transform: translateX(0px);
    opacity: 1;
  }
}

form{
  width: 25rem;
  row-gap: 1rem;
}
.inputs{
  row-gap: 1.1rem;
  display: flex;
  flex-direction: column;
}
label{
  font-size: 1rem;
  font-weight: 500;
  letter-spacing: 2px;
  color: var(--verydarkviolet);
}
input{
  width: 100%;
  height: 3rem;
  padding: 1rem;
  border-radius: 8px;
  border: 1px solid var(--lightgreyviolet);
  font-size: 1.2rem;
  font-weight: 400;
  color: var(--verydarkviolet);;
}
input:focus{
  border: none;
  outline: none;
  border-width: 1px;
  border-style: solid;
  border-color: hsl(278, 94%, 30%);
}
::placeholder{
  color: var(--lightgreyviolet);
}
form button{
  background: var(--verydarkviolet);
  border-radius: 8px;
  color: var(--white);
  font-size: 1.2rem;
  padding: .8rem;
  transition: 0.2s all ease-in-out;
  border: none;
}
form button:active{
  transform: translateY(-10px);
}
form button:hover{
  background: rgb(92, 0, 128);
}
#mmyy{
  display: flex;
  column-gap: .7rem;
}
#mmyy input{
  width: 5.3rem;
}
#details{
  display: flex;
  justify-content: space-between;
  column-gap: 2rem;
  padding-bottom: 1.6rem;
}
#thanks{
  display: flex;
  flex-direction: column;
  text-align: center;
  margin-bottom: 4rem;
  animation: fade-in 0.2s ease-in-out;
}
#thanks img{
  width: 5rem;
  margin: 0 auto;
  height: auto;
  margin-bottom: 2rem;
}
#thanks h1{
  font-size: 1.8rem;
  font-weight: 500;
  letter-spacing: 3px;
  color: var(--verydarkviolet);
  padding-bottom: .5rem;
}
#thanks p{
  color: var(--darkgreyviolet);
  font-weight: 400;
}
@keyframes fade-in{
  0%{
    opacity: 0.1;
  }
  100%{
    opacity: 1;
  }
}
</style>
