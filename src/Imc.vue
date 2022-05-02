<template>
<div id="app">
    <div class="container-fluid">
        <div class="row">
            <div class=" col-md-12">
                <h1>Minha altura :{{ altura }}cm</h1>
                <input v-model="altura">
                <h1>Meu peso :{{ peso }}kg</h1>
                <input v-model="peso">
                <h2>Meu imc é: {{ calculaImc }}</h2>
            </div>
        </div>
    </div>
</div>
</template>

<script>
export default 
{
    data()
    {
        return{
            altura: null,
            peso: null
            }
    },
    
    computed:{
        calculaImc(){
        let peso = parseFloat(this.peso);
        let altura = parseFloat(this.altura) / 100;
        let resultado;
        let imc = peso / (altura * altura)
        if(imc < 18.5) {
         resultado = `${imc.toFixed(2)} kg/m2` + 'Classificação: Abaixo do peso' ;
        }
        else if (imc >=18.5 && imc <25 ) {
          resultado = `${imc.toFixed(2)} kg/m2 ` + 'Classificação: Normal' ;
        }
        else if (imc >=25 && imc <30 ) {
          resultado = `${imc.toFixed(2)} kg/m2` + 'Classificação: Sobrepeso' ;
        }
        else if (imc >=30 ) {
        resultado = `${imc.toFixed(2)} kg/m2` + 'Classificação: Obesidade' ;
        }
        return resultado
      }
    }

}
</script>


<style>

</style>