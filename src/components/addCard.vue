<template>
  <div>
    <!-- <form action="submit"> -->

    <input
      type="text"
      class="bar"
      placeholder="Name"
      v-model="inputName"
      @keypress="newCard"
    />
    <input
      type="text"
      class="bar"
      placeholder="Card-number"
      v-model="inputNumber"
      @keypress="newCard"
    />

    <!-- </form> -->

    <article v-if="card !== []">


      <span v-bind:key="item.id" v-for="item in card" >
       
       <div class="card">
       
  

  <p class="number"> {{ item.cardNumber }}</p>
     <p class="name"> {{ item.cardName }}</p>

        </div>
      </span>
    </article>


  </div>
</template>


<script>
export default {
  name: "addCard",
  data() {
    return {
      inputName: "",
      inputNumber: "",
      validThru: "",
      autoInputId:0,
      card: [
        {
          id: 999,
          cardNumber: 0,
          cardName: "test",
          valid: 0,
        },
      ],
    };
  },

  methods: {
      
    
    newCard(e) {
              
      if (e.key === "Enter") {

    
        this.card.push({ 
            id: this.autoInputId,
            cardName:this.inputName, 
            cardNumber:this.inputNumber
            });
            this.autoInputId++

                console.log(this.card) 
      }
    },
  },
};
</script>






<style scoped>
.card {
 width: 20rem;
 height: 10rem;
 display: flex;
  background: linear-gradient(
      248.3deg,
      rgba(255, 255, 255, 0.24) 0%,
      rgba(255, 255, 255, 0) 100%
    ),
    #d0d0d0;
  box-shadow: 0px 0px 16px rgba(0, 0, 0, 0.08);
  border-radius: 8px;
}

.name {

    padding-top: 1rem;
  font-family: PT Mono;
  font-style: normal;
  font-weight: normal;
  font-size: 18px;
  line-height: 20px;
  display: flex;
  align-items: center;
  text-transform: uppercase;

  color: #000000;
}


.number{
     padding: 1rem;
    font-family: PT Mono;
font-style: normal;
font-weight: normal;
font-size: 29px;
line-height: 32px;
letter-spacing: 0.03em;

}
</style>
