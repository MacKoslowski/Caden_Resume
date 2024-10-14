<template>
  <div>
    <div class="text-3xl w-full font-bold mb-2">Portfolio PDF Links</div>
    <!--<ul>
      <li v-for="file in files" :key="file.id">
        <a
          :href="`https://drive.google.com/uc?id=${file.id}`"
          target="_blank"
          >{{ file.name }}</a
        >
      </li>
    </ul>-->

    <div
      v-for="file in files"
      :key="file.id"
      class="rounded-lg bg-base-100 hover:shadow-xl transition ease-in-out hover:scale-[102%]"
    >
      <a :href="`https://drive.google.com/uc?id=${file.id}`" target="_blank">
        <div class="hero-content flex-col md:flex-row">
          <div class="grow w-full">
            <h1 class="text-xl font-bold">
              {{ file.name }}
            </h1>
          </div>
        </div>
      </a>
    </div>
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
  mounted() {
    const apiKey = "AIzaSyASxw8DT8Gt7z6bIbG5ixw6LmJw6_x7YF8";
    const folderId = "1TOPTFSZdPXjXspSu45tSK40Hn8cinbi4";

    const url = `https://www.googleapis.com/drive/v3/files?q='${folderId}'+in+parents&key=${apiKey}`;

    axios
      .get(url)
      .then((response) => {
        this.files = response.data.files.filter(
          (file) => file.mimeType === "application/pdf"
        );
      })
      .catch((error) => {
        console.error("Error fetching files:", error);
      });
  },
};
</script>
