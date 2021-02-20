<template>
  <div>
    <InputText v-model="text"/>
    <Button label="Greet" icon="pi pi-user" @click="greet"></Button>
    {{text}}
    <Toast/>
  </div>
</template>

<script>
import { defineComponent, ref } from "vue";
import { useToast } from 'primevue/usetoast';

export default defineComponent({
  setup(){
    const toast= useToast();
    const text = ref('Prime');
    const greet = () => {
      toast.add({severity: 'info', summary:'Hello', detail: text});
    }

    return {
      text,
      greet
    }
  }
})

/*
export default {
  data(){
    return {
      text: null
    }
  },
    methods: {
      greet(){
        this.$toast.add({severity: 'info', summary:'Hello', detail: this.text});
      }
    }
}
*/

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
