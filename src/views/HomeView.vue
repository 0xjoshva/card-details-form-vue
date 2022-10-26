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
    <form action="post">
      <label for="name">
        CARDHOLDER NAME <br />
        <input name="name" type="text" placeholder="e.g Quandale Dingle" />
      </label>
      <label for="number">
        CARD NUMBER <br />
        <input name="number" type="text" placeholder="e.g 0238 2738 2838 2821" />
      </label>
      <div id="details">
        <label for="date">
          EXP. DATE (MM/YY) <br />
          <div id="mmyy">
            <input name="date" type="number" placeholder="MM" min="1" max="12"/>
            <input type="number" placeholder="YY" min="22" max="29"/>
          </div>
        </label>
        <label for="cvc">
          CVC <br />
          <input type="text" placeholder="e.g 123"  />
        </label>
      </div>
      <button>Confirm</button>
    </form>
  </section>
</template>

<script>
export default {};
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
  padding-left: 10px;
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
  border-image: linear-gradient(to right bottom, #260B3C, #a053df);
  border-image-slice: 1;
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

</style>
