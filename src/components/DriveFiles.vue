<template>
  <div>
    <div class="text-3xl w-full font-bold mb-2">Portfolio PDF Links</div>
    <ul>
      <li>
        <a href="/Diabetes_Weight_Loss_drug_log.pdf" target="_blank"
          >Diabetes Weight Loss Drug Blog Post</a
        >
      </li>
      <li>
        <a href="Everyday_Flowers_July.pdf" target="_blank">Everyday Flowers</a>
      </li>
      <li>
        <a href="Jewelry_Lab_Diamonds.pdf" target="_blank"
          >Jewelry Lab Diamonds</a
        >
      </li>
    </ul>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      files: [],
    };
  },
  mounted() {},
};
</script>
