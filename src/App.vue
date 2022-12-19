<template>
  <div>
    <!--<Login />-->
    <CadastroAluno/>
    <!--<ListagemAlunos/>-->
  </div>
</template>

<script>
  import Login from './components/Login.vue'
  import CadastroAluno from './components/CadastroAluno.vue'
  import ListagemAlunos from './components/ListagemAlunos.vue'
    
  export default {
    name: 'App',
    components: {
      Login,
      CadastroAluno, 
      ListagemAlunos
    }
  }
</script>


