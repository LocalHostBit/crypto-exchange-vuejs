<template>
  <header class="shadow w-screen">
    <nav>
      <nav class="flex items-center justify-between flex-wrap bg-green-700 p-6">
        <div class="flex items-center flex-shrink-0 text-white">
          <x-icon class="mr-2" />
          <router-link
            :to="{ name: 'home' }"
            class="font-semibold text-xl tracking-tight"
          >Exchange Crypto</router-link>
        </div>
        <div class="hidden sm:block w-full block flex-grow lg:flex lg:items-center lg:w-auto">
          <div class="text-sm lg:flex-grow ml-5">
            <router-link
              v-for="l in links"
              :key="l.title"
              :to="l.to"
              class="block mt-4 lg:inline-block lg:mt-0 text-teal-200 hover:text-white mr-4"
            >{{l.title}}</router-link>
          </div>
        </div>
      </nav>
    </nav>
  </header>
</template>

<script>
import xIcon from "@/components/xIcon";

export default {
  name: "xHeader",
  components: { xIcon },

  props: {
    links: {
      type: Array,
      default: () => []
    }
  }
};
</script>
