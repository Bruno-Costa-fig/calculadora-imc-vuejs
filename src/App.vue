<template>
  <div>
    <h1>Calculadora de IMC</h1>
    <input type="number" placeholder="Altura" id="altura" v-model="altura" />
    <input type="number" placeholder="Peso" v-model="peso" />
    <button @click="calcularImc">Calcular</button>
    <h2>{{ resultado }}</h2>
  </div>
</template>
<script>
export default {
  data(){
    return {
      peso: 0,
      altura: 0,
      resultado: ""
    }
  },
  methods: {
    calcularImc(){

      if(this.peso == 0 || this.altura == 0){
        alert("Preencha todos os dados!")
        return
      }

      let imc = (this.peso / (this.altura * this.altura)).toFixed(2)

      if(imc < 18.5){
          this.resultado = "Abaixo do peso ideal."
      } else if(imc >= 18.5 && imc <= 24.9){
          this.resultado = "Com peso ideal, Parabéns!"
      } else if(imc >= 25 && imc <= 29.9){
          this.resultado = "Com sobrepeso."
      } else if(imc >= 30 && imc <= 39.9){
          this.resultado = "Com obesidade grau II."
      }
      else if(imc >= 40){
          this.resultado = "Com obesidade grau III."
      }
    },
    proximaFuncao(){

    }
  }
}
</script>
<style>
  button {
    padding: 10px 20px;
    border: none;
    background: green;
    color: white;
  }
</style>