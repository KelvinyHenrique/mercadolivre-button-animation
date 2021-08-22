<template>
  <div class="home">
    <Button
      :loading="isLoading"
      @click="isLoading = !isLoading"
      loading-time="2s"
      title="Confirmar compra"
    />
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import Button from "@/components/Button.vue"; // @ is an alias to /src

@Options({
  components: {
    Button,
  },
  data() {
    return {
      isLoading: false,
    };
  },
})
export default class Home extends Vue {}
</script>

<style scoped>
.home {
  width: 100%;
  height: 100vh;
  margin: 0;
  padding: 0;
  background-color: #121212;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
