<template>
    <div class="container"> 
        <br>
        <h1>Login</h1>
        <form>
            <div  class="form-todo form-group">
                <p>
                <label for="user"><strong>Usuário</strong></label>
                <input placeholder="Usuario" type="text" name="user" class="form-control" v-model="user" required>
                </p>
                <p>
                    <label for="senha"><strong>Senha</strong></label>
                    <input placeholder="Insira a senha" type="password" name="senha" class="form-control" v-model="senha" required>
                </p>
            <button v-on:click="logar" type="submit" class="btn btn-primary">Sign in</button>
            </div>          
        </form>
    </div>
</template>

<script>
    export default{
        name: 'Login',
        data(){
            return{
                user: '', 
                senha: ''
            }
        }, 
        methods: {
            logar(){
                if(this.user == '' && this.senha == ''){
                    alert('Campos vazios, preencha corretamente!');
                }
                if(this.user == 'Rafaela' && this.senha == '123'){
                    alert('Logado com sucesso!');
                }
            }
        }
    }
</script>