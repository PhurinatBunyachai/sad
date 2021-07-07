<template>
  <div class="hello">
    counter : {{ count }} <button @click="newInput">+</button>
    <button v-if="inputs.length > 1" @click="undo">undo</button>
    <div v-for="(input, index) in inputs" :key="input.id">
      <input :id="input.id" v-model="input.value" />
      <button @click="clearInput(index)">X</button>
    </div>
    <button @click="submit">submit</button>
  </div>
</template>

<script>
export default {
  name: "CloneInput",
  props: {
    msg: String,
  },
  data() {
    return {
      inputs: [
        {
          id: "input",
          value: "",
        },
      ],
      count: 1,
    };
  },
  methods: {
    newInput() {
      this.inputs.push({
        id: `input${++this.count}`,
        value: "",
      });
    },
    undo() {
      if (this.inputs.length > 1) {
        this.inputs.pop();
        this.count--;
      } else {
        alert("can't remove");
      }
    },
    submit(e) {
      e.preventDefault();
      alert(JSON.stringify(this.inputs));
    },
    clearInput(index) {
      this.inputs[index].value = "";
    },
  },
};
</script>

