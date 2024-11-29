<script>
  import chip1 from './assets/chip1.png';
  import chip2 from './assets/chip2.png';
  import chip3 from './assets/chip3.png';
  import tipo1 from './assets/visa.png';
  import tipo2 from './assets/master.png';
  import tipo3 from './assets/american.png';


  export default { name: "App", 
  data() { 
    return { 
      tarjeta: { 
        tituloTarjeta: "",
        chipImagenTarjeta: {chip1, chip2, chip3},
        numeroTarjeta: "", 
        fechaExpiraTarjeta: "", 
        nombreClienteTarjeta: "", 
        tipoSrcTarjeta: {tipo1, tipo2, tipo3}
        }, 
      }; 
    }, 
  };

</script>

<template>
    <div id="app">
      <form>
        <div>
          <label>Título de la tarjeta: </label>
          <select v-model="tarjeta.tituloTarjeta">
            <option  >Visa Clasica Nacional</option>
            <option  >Visa Golden Nacional</option>
            <option >Visa International</option>
            <option  >Visa Black</option>
            <option  >Visa Master-Card</option>
            <option  >Visa American-Express</option>
          </select>
        </div>

        <div>
          <label>Chip SRC: </label>
          <select v-model="tarjeta.chipImagenTarjeta">
            <option :value="tarjeta.chipImagenTarjeta.chip1" >Chip 1</option>
            <option :value="tarjeta.chipImagenTarjeta.chip2" >Chip 2</option>
            <option :value="tarjeta.chipImagenTarjeta.chip3" >Chip 3</option>
          </select>
        </div>

        <div>
          <label>Número: </label>
          <input type="number" v-model="tarjeta.numeroTarjeta"/>
        </div>

        <div>
          <label>Fecha de expiración: </label>
          <input type="month" v-model="tarjeta.fechaExpiraTarjeta"/>
          
        </div>

        <div>
          <label>Propietario: </label>
          <input type="text" v-model="tarjeta.nombreClienteTarjeta"/>
        </div>

        <div>
          <label>Tipo de tarjeta SRC: </label>
          <select v-model="tarjeta.tipoSrcTarjeta">
            <option :value="tarjeta.tipoSrcTarjeta.tipo1">Visa</option>
            <option :value="tarjeta.tipoSrcTarjeta.tipo2">Master Card</option>
            <option :value="tarjeta.tipoSrcTarjeta.tipo3">American Express</option>
          </select>
        </div>
      </form>

      <div class="carnet">
        <h3>{{tarjeta.tituloTarjeta}}</h3>
        <img width="40" :src="tarjeta.chipImagenTarjeta" alt="" />
        <div>
          <h2>{{tarjeta.numeroTarjeta}}</h2>
          <span>Fecha Exp: <b>{{tarjeta.fechaExpiraTarjeta}}</b></span>
        </div>
        <footer>
          <span>{{tarjeta.nombreClienteTarjeta}}</span>
          <img :src="tarjeta.tipoSrcTarjeta" width="60" />
        </footer>
      </div>
    </div>
</template>

<style>
  * {
    margin: 0;
  }
  body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 60vh;
    font-size: 10px;
    font-family: sans-serif;
  }

  #app {
    display: flex;
    gap: 40px;
  }
  form {
    padding: 18px;
    border-radius: 20px;
    border: ridge 1px;
    box-shadow: 1px 1px 1px 1px gray;
    font-weight: bold;
    display: flex;
    flex-direction: column;
    gap: 15px;
    justify-content: center;
  }
  form div {
    display: grid;
    grid-template-columns: 100px 200px;
    align-items: center;
    gap: 5px;
  }

  form div label {
    text-align: right;
  }

  .carnet {
    width: 400px;
    height: 230px;
    background: #1c1a1e;
    color: white;
    border-radius: 20px;
    padding: 20px;
    box-shadow: 0px 0px 10px 2px black;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }

  h3 {
    font-size: 20px;
  }

  h2 {
    font-size: 30px;
    letter-spacing: 10px;
    margin-bottom: 15px;
    text-shadow: 0px 0px 1px gold;
    font-family: Times;
  }

  b {
    font-size: 16px;
  }

  footer {
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
    font-weight: bold;
    font-size: 18px;
    text-transform: uppercase;
    font-style: italic;
  }
</style>
  


