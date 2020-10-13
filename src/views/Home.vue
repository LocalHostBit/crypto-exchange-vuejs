<template>
  <div>
    <circle-loader :loading="isLoading" :color="'#22543D'" :size="80" />
    <x-assets-table v-if="!isLoading" :assets="assets" />
  </div>
</template>

<script>
import api from "@/api";
import xAssetsTable from "@/components/xAssetsTable";

export default {
  name: "Home",

  components: { xAssetsTable },

  data() {
    return {
      isLoading: false,
      assets: []
    };
  },

  created() {
    this.isLoading = true;
    api
      .getAssets()
      .then(assets => (this.assets = assets))
      .finally(() => (this.isLoading = false));
  }
};
</script>
