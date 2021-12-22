<template>
  <div>
    <form >

    <input
      type="text"
      class="bar"
      placeholder="Name"
      v-model="inputName"
      @keypress="newCard"
    />
    <input
      type="number"
      min="1"
      max="100000"
      class="bar"
      placeholder="Card-number"
      v-model="inputNumber"
      @keypress="newCard"
    />

    <input
      type="date"
      class="bar"
      placeholder="Exp date"
      v-model="inputvalidThru"
      @keypress="newCard"
    />

    </form>


<form >
<select v-model="inputDeleteNumber" @select=removeCard()>
  <option>0</option>
<option>1</option>
<option>2</option>
<option>3</option>


</select>
<label>Remove card number..</label>
<input type="button" :value=inputDeleteNumber @click= removeCard() id="submit">
</form>



    <article v-if="cardList !== []">
      <span  v-bind:key="item.id" v-for="item in cardList" @click="removeCard() ">
        <div    class="card"  ref="cardRef" v.bind:id="item.id"   :style="{backgroundColor:item.cardColor}">
       

        
          <p class="number">
            <label> Card number: </label>{{ item.cardNumber }}
          </p>

          
      <footer> <p >
            <label> <small> Exp date:</small></label> {{ item.cardValid }}
          </p>

           <p class="name">
            <label><small> Cardholder Name:</small></label
            >{{ item.cardName }}
          </p>

<!-- <input type="hidden" value={{item.id}}> -->

          </footer>   
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
      newColor:'#efg',
      randomColor:['#789'],
      inputName: "",
      inputNumber: "",
      inputvalidThru: "",
      inputDeleteNumber:0,
      autoInputId: 0,
      cardList: [
        {
          id: 999,
          cardNumber: 123456,
          cardName: "test person",
          cardValid: "2021-12-01",
          cardColor: '#abc'
        },
      ],
    };
  },

  methods: {
    newCard(e) {
     
     
     var color = '#'+(Math.random()*0xFFFFFF<<0).toString(16);
this.randomColor.push(color);
this.newColor= this.randomColor.slice(-1);
     
     if (e.key === "Enter") {
        this.cardList.push({
          id: this.autoInputId,
          cardName: this.inputName,
          cardNumber: this.inputNumber,
          cardValid: this.inputvalidThru,
          cardColor:this.newColor
        });
        this.autoInputId++;




// var cardRefLast = this.$refs.cardRef.slice(-1) 
// console.log(cardRefLast)
// document.cardRefLast.style = this.newColor



// document.body.style.backgroundColor =color

      }

    },


    removeCard(){
      //   console.log( document.getElementById("submit").value);
      // console.log(this.$refs.cardId)

      var cardRemoveId = document.getElementById("submit").value


        this.cardList.splice([cardRemoveId],1)

    }
  },
};
</script>






<style scoped>


form{
  display: flex;
  flex-direction: column;
  padding: 1rem;
  max-width: 50vw;
}

input{

  padding: 1rem;
  margin: 1rem;
}

.card {
    text-align: center;
  max-width: 20rem;
  display: flex;
  flex-direction: column;
  flex-wrap: nowrap;
  background: linear-gradient(
      248.3deg,
      rgba(255, 255, 255, 0.24) 0%,
      rgba(255, 255, 255, 0) 100%
    ),
    #d0d0d0;
  box-shadow: 0px 0px 16px rgba(0, 0, 0, 0.08);
  border-radius: 8px;
  margin: 1rem;
  
}

/* .card:first-of-type{
background: linear-gradient(
      248.3deg,
      rgba(255, 255, 255, 0.24) 0%,
      rgba(255, 255, 255, 0) 100%
    ),
    #da6868;

}

.card:nth-of-type(2){
background: linear-gradient(
      248.3deg,
      rgba(255, 255, 255, 0.24) 0%,
      rgba(255, 255, 255, 0) 100%
    ),
    #6886da;

}


.card:nth-of-type(3){
background: linear-gradient(
      248.3deg,
      rgba(255, 255, 255, 0.24) 0%,
      rgba(255, 255, 255, 0) 100%
    ),
    #68dacb;

} */


label {
  font-size: 12px;


}

.name {
  padding: 1rem;
  font-family: PT Mono;
  font-style: normal;
  font-weight: normal;
   font-size: 12px;
  line-height: 20px;
  display: flex;
  align-items: center;
  text-transform: uppercase;
flex-direction: column;
  color: #000000;
}

.number {
  display: flex;
  flex-direction: column;
  flex-wrap: nowrap;
  padding: 0.5rem ;
  font-family: PT Mono;
  font-style: normal;
  font-weight: normal;
   font-size: 1.2rem;
  letter-spacing: 0.03em;
  text-align: center;
}

small {
  padding: 0.5rem;
}


footer{
    display: flex;
    text-align: center;
}
</style>
