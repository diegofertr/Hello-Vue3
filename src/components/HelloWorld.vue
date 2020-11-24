<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <hr>
    <div>
      <h1>Contador</h1>
      <h2 class="counter">{{ counter }}</h2>
      <button class="btn-primary" @click="decrement">-</button>
      <button class="btn-primary" @click="increment">+</button>
    </div>
    <hr>
    <div>
      <h1>Model</h1>
      <label for="nombre">Nombre: </label>
      <input name="nombre" class="txt-input" type="text" v-model="nombre" placeholder="Introduzca su nombre">
      <p>
        <strong>Su nombre es:</strong> {{ nombre }}
      </p>
    </div>
  </div>
</template>

<script>
import { onMounted, ref } from 'vue'
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  setup () {
    // Creando variables reactivas
    const counter = ref( 0 )
    const nombre = ref( '' )

    // Funciones o métodos
    const increment = () => {
      counter.value++
    }

    const decrement = () => {
      counter.value--
    }

    const setNombre = () => {
      nombre.value = 'diegofer'
    }
    const setCounter = () => {
      counter.value = 10
    }

    // Asignando datos de entrada al montar el componente
    onMounted(setNombre)
    onMounted(setCounter)


    return {
      // variables reactivas
      counter,
      nombre,
      // funciones
      increment,
      decrement,
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
  text-decoration: none;
}
.counter {
  margin: 1rem 0;
  font-size: 3rem;
}
.btn-primary {
  padding: .5rem 2rem;
  margin: 0 1rem;
  border-radius: 10px;
  border: none;
  background: #091F92;
  color: white;
  font-size: 1.5rem;
}
.btn-primary:focus {
  outline: none;
}
.btn-primary:hover {
  opacity: .9;
}
.txt-input {
  margin: 1rem 0;
}
hr {
  margin: 2rem 0;
}
input {
  padding: 10px;
  border-radius: 5px;
  font-size: 1rem;
  box-shadow: transparent;
}

</style>
