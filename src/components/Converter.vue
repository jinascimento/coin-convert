<template>
        <div class="converter">
            <h2>{{moedaA}} Para {{moedaB}}</h2>
            <div class="input-box">
                <input type="text"  v-model="moedaA_value" v-bind:placeholder="moedaA">
                <input type="button" value="Converter" v-on:click="converter">
            </div>
            <h2>{{moedaB_value}}</h2>
        </div>
</template>

<script>
    export default {
      name: 'Converter',
      props: ["moedaA", "moedaB"],
      data() {
        return{
          moedaA_value: "",
          moedaB_value: 0,
        }
      },
      methods: {
        converter(){
          let from_to = this.moedaA + "_" + this.moedaB;
          let url = "https://free.currconv.com/api/v7/convert?q="+from_to+"&compact=ultra&apiKey=1fb549a0b4086d4d8eec";
          console.log(url);
          fetch(url)
              .then(res => {
                return res.json();
              })
              .then(json => {

                let quotation = json[from_to];
                this.moedaB_value = (quotation * parseFloat(this.moedaA_value)).toFixed(2);
          })
        }
      }
    };
</script>

<style scoped>
    .converter{
        padding: 20px;
        max-width: 300px;
        box-shadow: 0 4px 8px 0 rgb(0, 0, 0, 0.2);
    }

    .input-box {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
    }

    h2 {
        text-align: center;
    }

    input {
        margin-top: 10px;
    }

    input[type=text] {
        border-radius: 8px;
        height: 30px;

    }

    input[type=text] {
        border-radius: 8px;
        height: 30px;
    }

    input[type=button] {
        border-radius: 8px;
        background-color: #4c9875;
        height: 35px;
    }

    input[type=button]:hover {
         background-color: rgba(246, 244, 244, 0.99);
     }

</style>
