<script>
import axios from "./utils/axios";

import Spinner from "./components/Spinner.vue";
import EmailList from "./components/EmailList.vue";
import Navbar from "./components/Navbar.vue";
import Search from "./components/Search.vue";

export default {
  name: "App",
  data() {
    return {
      search: "",
      emails: [],
      isLoading: false,
    };
  },
  async mounted() {
    this.isLoading = true;
    const {
      data: { data },
    } = await axios.get("/users");
    this.emails = data;
    this.isLoading = false;
  },
  components: {
    Spinner,
    EmailList,
    Navbar,
    Search,
  },
};
</script>

<template>
  <Navbar />
  <div class="container max-w-screen-lg mx-auto pt-10">
    <Search v-model="search" />
    {{ search }}
  </div>
  <div class="container max-w-screen-lg mx-auto pt-10 w-full">
    <Spinner v-if="isLoading" />
    <EmailList v-else :emails="emails" />
  </div>
</template>
