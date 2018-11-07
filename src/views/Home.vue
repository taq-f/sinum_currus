<template>
  <div>
    <ul>
      <li v-for="element in elements" :key="element.hash">
        {{ element.text }}
      </li>
    </ul>
  </div>
</template>

<script>
import { ipcRenderer } from "electron";

export default {
  data() {
    return {
      message: "ABC",
      elements: [
        {
          hash: "aaa",
          text: "sample text 1"
        },
        {
          hash: "bbb",
          text: "sample text 2"
        },
        {
          hash: "ccc",
          text: "sample text 3"
        }
      ]
    };
  },
  mounted() {
    ipcRenderer.on("channel", () => {});
  }
};
</script>
