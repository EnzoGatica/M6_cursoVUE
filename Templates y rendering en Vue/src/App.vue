<template>
  <div id="app">
    <FormComponent />
  </div>
</template>

<script>
import FormComponent from './components/FormComponent.vue';

export default {
  components: {
    FormComponent
  }
};
</script>

<style>
body {
  font-family: Arial, sans-serif;
  background-color: #f5f5f5;
  margin: 0;
  padding: 20px;
}
</style>
