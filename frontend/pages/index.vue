<template>
  <div>
    {{ hello }}
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      hello: null,
    };
  },
  async mounted() {
    try {
      const response = await axios.get("http://localhost:1337/main");
      this.hello = response.data.hello;
    } catch (error) {
      this.erorr = error;
      console.log(this.erorr);
    }
  },
};
</script>
