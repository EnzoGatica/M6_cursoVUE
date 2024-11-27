<script setup>
import { ref } from 'vue'

// Variables del estado
const titulo = ref('')
const emoji = ref('')
const apreciacion = ref('')
const competencias = ref([])
const opinion = ref('')
</script>

<template>
  <div class="container">
    <div class="formulario">
      <h2>Formulario</h2>

      <!-- Input de texto -->
      <label for="titulo">Título:</label>
      <input id="titulo" v-model="titulo" type="text" placeholder="Ingresa un título" />

      <!-- Select de emojis -->
      <div>
    <label for="emoji">Emoji:</label>
    <select id="emoji" v-model="emoji">
      <option value="" disabled>Selecciona un emoji</option>
      <option v-for="(emojiItem, index) in emojis" :key="index" :value="emojiItem">
        {{ emojiItem }}
      </option>
    </select>
  </div>

      <!-- Radio para apreciación -->
      <label>Apreciación:</label>
      <label><input type="radio" v-model="apreciacion" value="Regular" /> Regular</label>
      <label><input type="radio" v-model="apreciacion" value="Bien" /> Bien</label>
      <label><input type="radio" v-model="apreciacion" value="Muy bien" /> Muy bien</label>
      <label><input type="radio" v-model="apreciacion" value="Increíble" /> Increíble</label>

      <!-- Checkbox de competencias -->
      <label>Competencias aprendidas:</label>
      <label><input type="checkbox" v-model="competencias" value="Morfología de un componente" /> Morfología de un componente</label>
      <label><input type="checkbox" v-model="competencias" value="Directivas" /> Directivas</label>
      <label><input type="checkbox" v-model="competencias" value="One-Way y Two-Way data binding" /> One-Way y Two-Way data binding</label>
      <label><input type="checkbox" v-model="competencias" value="Estado" /> Estado</label>
      <label><input type="checkbox" v-model="competencias" value="El patrón de diseño MVVM" /> El patrón de diseño MVVM</label>

      <!-- Textarea de opinión -->
      <label for="opinion">Opinión:</label>
      <textarea id="opinion" v-model="opinion" placeholder="Escribe tu opinión"></textarea>
    </div>

    <!-- Mostrar los valores reactivos -->
    <div class="resultados">
      <h2>Valores ingresados</h2>
      <p><strong>Título:</strong> {{ titulo }}</p>
      <p><strong>Emoji:</strong> {{ emoji }}</p>
      <p><strong>Apreciación:</strong> {{ apreciacion }}</p>
      <p><strong>Competencias:</strong> {{ competencias.join(', ') }}</p>
      <p><strong>Opinión:</strong> {{ opinion }}</p>
    </div>
  </div>
</template>

<style>
/* Estilos para darle el formato visual de la imagen proporcionada */
.container {
  display: flex;
  justify-content: center;
  align-items: flex-start;
  padding: 20px;
  background-color: #111;
  color: white;
  min-height: 100vh;
}

.formulario {
  width: 500px;
  padding: 20px;
  background-color: #000;
  border-radius: 20px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
}

h2 {
  text-align: center;
  margin-bottom: 20px;
  color: white;
}

label {
  display: block;
  margin-bottom: 8px;
  font-size: 14px;
  color: white;
}

input[type="text"], select, textarea {
  width: 100%;
  margin-bottom: 15px;
  padding: 10px;
  background-color: #333;
  border: 1px solid #555;
  border-radius: 10px;
  color: white;
}

input[type="radio"], input[type="checkbox"] {
  margin-right: 10px;
}

textarea {
  height: 80px;
}

.resultados {
  margin-left: 30px;
  width: 300px;
  background-color: #222;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
}

.resultados p {
  margin: 10px 0;
  font-size: 14px;
  color: white;
}
</style>

<script>
export default {
  data() {
    return {
      emoji: "", 
      emojis: ["😀", "😎", "🥳", "🤔"],
    };
  },
};
</script>