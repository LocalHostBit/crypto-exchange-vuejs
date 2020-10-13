<template>
  <main>
    <xHeader :links="links" class="w-screen bg-blue-600 shadow" />
    <x-title />
    <router-view class="container flex justify-center px-5 py-5" />
    <x-footer />
  </main>
</template>

<script>
import xHeader from "@/components/xHeader";
import xTitle from "@/components/xTitle";
import xFooter from "@/components/xFooter";

export default {
  name: "App",
  components: { xHeader, xTitle, xFooter },

  data() {
    return {
      links: [
        {
          title: "BTC",
          to: { name: "coin-detail", params: { id: "bitcoin" } }
        },
        {
          title: "ETH",
          to: { name: "coin-detail", params: { id: "ethereum" } }
        },
        {
          title: "XRP",
          to: { name: "coin-detail", params: { id: "ripple" } }
        },
        {
          title: "About",
          to: { name: "about", patch: "/about" }
        }
      ]
    };
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
