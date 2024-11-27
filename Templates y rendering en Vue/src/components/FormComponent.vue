<template>
  <div class="container">
    <div class="controls">
      <label>
        <span>Color de fondo:</span>
        <input type="color" v-model="backgroundColor" />
      </label>

      <label>
        <span>Color de texto:</span>
        <input type="color" v-model="textColor" />
      </label>

      <label>
        <span>Mostrar texto:</span>
        <input type="checkbox" v-model="showText" />
      </label>

      <label>
        <span>Borde redondeado:</span>
        <input type="range" min="0" max="50" v-model="borderRadius" />
      </label>

      <label>
        <span>Contenido textual:</span>
        <textarea v-model="textContent" rows="2" placeholder="Escribe aquí..."></textarea>
      </label>

      <label>
        <span>Tipografía:</span>
        <select v-model="fontFamily">
          <option v-for="(font, index) in fonts" :key="index" :value="font">{{ font }}</option>
        </select>
      </label>

      <label>
        <span>Opaco:</span>
        <input type="checkbox" v-model="isOpaque" />
      </label>

      <div class="font-size">
        <span>Tamaño de letra:</span>
        <label v-for="(size, index) in fontSizes" :key="index">
          <input type="radio" :value="size.value" v-model="fontSize" /> {{ size.label }}
        </label>
      </div>
    </div>

    <div v-show="showShape" :style="figureStyle" :class="{ bordered: isOpaque }" class="figure">
      <span v-if="showText">{{ textContent }}</span>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      backgroundColor: '#4caf50',
      textColor: '#ffffff',
      showText: true,
      textContent: 'Awesome Vue.js',
      fontFamily: 'Arial',
      fontSize: 'medium',
      isOpaque: true,
      borderRadius: 20,
      showShape: true,
      fonts: ['Cursive', 'Courier New', 'Arial'],
      fontSizes: [
        { label: 'Pequeño', value: 'small' },
        { label: 'Mediano', value: 'medium' },
        { label: 'Grande', value: 'large' },
      ]
    };
  },
  computed: {
    figureStyle() {
      return {
        backgroundColor: this.backgroundColor,
        color: this.textColor,
        borderRadius: this.borderRadius + '%',
        fontFamily: this.fontFamily,
        fontSize: this.getFontSize(),
        opacity: this.isOpaque ? 1 : 0.5,
        padding: '20px',
        display: 'flex',
        alignItems: 'center',
        justifyContent: 'center',
        width: '200px',
        height: '200px',
        transition: 'all 0.3s ease-in-out',
        boxShadow: '0 4px 8px rgba(0, 0, 0, 0.1)',
      };
    },
  },
  methods: {
    getFontSize() {
      switch (this.fontSize) {
        case 'small':
          return '12px';
        case 'medium':
          return '16px';
        case 'large':
          return '24px';
        default:
          return '16px';
      }
    },
  },
};
</script>

<style scoped>
.container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  gap: 30px;
  max-width: 900px;
  margin: 40px auto;
  padding: 20px;
}

.controls {
  flex: 1;
  min-width: 300px;
  background-color: #253442;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  color: #ecf0f1;
}

.controls label {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 15px;
}

.controls label span {
  flex: 1;
  text-align: left;
}

textarea {
  resize: none;
  width: 100%;
  padding: 5px;
  border-radius: 5px;
}

input[type="color"],
textarea,
select {
  flex: 2;
  padding: 5px;
  border: none;
  border-radius: 5px;
  background-color: #ecf0f1;
  color: #2c3e50;
}

input[type="checkbox"],
input[type="radio"] {
  margin-left: 10px;
}

input[type="range"] {
  width: 100%;
}

.font-size {
  display: flex;
  align-items: center;
  gap: 10px;
}

.figure {
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #3f8f60;
  color: white;
  border: 2px solid #fff;
  text-align: center;
  border-radius: 20%;
  transition: all 0.3s ease;
  width: 200px;
  height: 200px;
}

</style>
