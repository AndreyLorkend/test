<template>
  <div id="app">
    <input v-model="column" type="number" />
    <input v-model="row" type="number" />
    <table>
      <tr v-for="col in column">
        <td v-for="r in row">
          <div
            v-bind:style="style"
            id="box"
            v-on:click="changeColor($event)"
          ></div>
        </td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      style: {
        backgroundColor: '#1111',
      },
      column: 5,
      row: 5,
    };
  },

  methods: {
    changeColor($event) {
      let color = '#';
      for (let i = 0; i < 6; i++) {
        let num = Math.floor(Math.random() * 16);
        color += num.toString(16);
      }
      $event.srcElement.style.backgroundColor = color;
    },
  },
};
</script>

<style>
#app {
}

#box {
  width: 50px;
  height: 50px;
  border-radius: 1px;
  border: solid;
  display: block;
}
</style>
