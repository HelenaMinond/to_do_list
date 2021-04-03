<template>
  <div>
    <h1>Crea una nueva tarea</h1>

    <section>
      <label>Tarea</label>
      <input
        v-model="nuevaTarea"
        type="text"
        placeholder="Ingresa nueva tarea"
        size="15"
        maxlength="40"
      />
      <button @click="AgregarTarea()">Crear</button>
    </section>

    <h2>Lista</h2>

    <ul>
      <li v-for="(nuevaTarea, indice) in tareas" :key="(nuevaTarea, indice)">
        {{ indice }}: {{ nuevaTarea }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      tareas: ["Ir al supermercado", "Pagar internet", "Pagar Netflix"],
      nuevaTarea: "",
    };
  },
  methods: {
    AgregarTarea() {
      if (this.nuevaTarea === "") return;
      this.tareas.push(this.nuevaTarea);
      this.nuevaTarea = "";
    },
  },
};
</script>

<style lang="scss">
div {
  font-family: "Roboto", sans-serif;
  display: flex;
  flex-direction: column;
  align-items: center;
}

h1,
h2 {
  color: gray;
  margin-top: 2rem;
}

label,
li {
  font-weight: 500;
}

label {
  font-size: large;
}

input,
button {
  margin-left: 0.5rem;
}

button {
  background-color: white;
  border: solid 1px gray;
  border-radius: 5px;
}
</style>
