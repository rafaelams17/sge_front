<template>
    <div class="container">
        <br>
        <h1>Cadastro de Alunos</h1>
        <hr />
        <div class="form-todo form-group">
            <p>
                <input placeholder="Nome do Aluno" type="text" name="nomeAluno" class="form-control" v-model="nomeAluno" />
            </p>

            <p>
                <input placeholder="CPF do Aluno" type="text" name="cpf" class="form-control" v-model="cpf" />
            </p>

            <p>
                <input placeholder="Data de Nascimento do Aluno" type="date" name="data" class="form-control" v-model="data_nasc" />
            </p>
            <button v-on:click="cadastrar" type="submit" class="btn btn-primary">Cadastrar</button>
        </div>
        <br>
        
        <hr/>

        <div class="container">
        <div class="list-group">
            <div v-for="(cadastros, index) in cadastro" :key="index" class="list-group-item" >
                <span  class="comment__author">
                    <p> 
                        Aluno: <strong> {{ cadastros.nomeAluno}}</strong>
                    </p>
                    <p>
                        CPF: {{cadastros.cpf }}
                    </p>
                    <p>
                        Data de Nascimento: {{ cadastros.data_nasc }}
                    </p>
                </span>
                <div>
                    <a href="#" title="Excluir" v-on:click="removeAluno(index)">Excluir</a>
                </div>
            </div>
        </div>
    </div>
    </div>
</template>

<script>
    export default{
        name: 'CadastroAluno',    
        data(){
            return{
                cadastro: [],
                nomeAluno: '',
                cpf: '',
                data_nasc: ''
            }
        },
        methods:{
            cadastrar(){
                if(this.cpf === '' && this.nomeAluno === '' && this.data_nasc === ''){
                    alert('Campos vazios, preencha corretamente!');
                }
                if(this.cpf.trim() === '' || this.nomeAluno.trim() === '' || this.data_nasc.trim() === ''){
                    return;
                }

                this.cadastro.push({
                    nomeAluno: this.nomeAluno,
                    cpf: this.cpf, 
                    data_nasc: this.data_nasc
                });

                alert('Aluno Cadastrado com sucesso!')

                this.nomeAluno = '';
                this.cpf = '';
                this.data_nasc = '';

            },
            removeAluno(index){
                this.cadastro.splice(index, 1);
            }
        } 
        
    }
</script>

<style>
h1{
    text-align: center;
}

</style>