<script>
import { ref } from 'vue'

export default {
  data() {
    return {
      dados: '',
      nome: '',
      senha: '',
      confirma_senha: '',
      email: '',
      biografia: '',
      endereco: '',
      data_nascimento: '',
      cidade: '',
      estado: '',
      hobbies: '',
      linguagens: [],
      dadosExibidos: false
    }
  },
  methods: {
    mostrarDados() {
      if (this.nome === "" || this.senha === "" || this.confirma_senha === "" || this.email === "" || this.biografia === "" || this.endereco === "" || this.cidade === "" || this.estado === "" || this.data_nascimento === "") {
        alert("Por favor, preencha todos os campos!");
      } else if (this.senha !== this.confirma_senha) {
        alert("As senhas não coincidem!");
      } else {
        this.dados = "Nome: " + this.nome + "Senha: " + this.senha + " Email: " + this.email + " Endereço: " +
          this.endereco + " Biografia: " + this.biografia + " Cidade:" + this.cidade + " Estado:" + this.estado +
          " Data de nascimento:" + this.data_nascimento;
        this.dadosExibidos = true;
      }
    }
  }
}
</script>

<template>
  <form @submit.prevent="mostrarDados">
    <h1>Formulário de Cadastro</h1>
    <label for="nome">Nome:</label>
    <input type="text" v-model="nome" minlength="3" maxlength="20" placeholder="Digite seu nome" autocomplete="on"
      required>

    <label for="email">E-mail:</label>
    <input type="email" v-model="email" placeholder="id@domínio.com" autocomplete="on" required>

    <label for="senha">Senha:</label>
    <input type="password" v-model="senha" placeholder="Senha" minlength="6" autocomplete="on" required>

    <label for="confirma_senha">Confirme a Senha:</label>
    <input type="password" v-model="confirma_senha" placeholder="Confirme sua senha" minlength="6" autocomplete="on"
      required>

    <label for="endereco">Endereço:</label>
    <input type="text" v-model="endereco" autocomplete="on" placeholder="Seu endereço" required>

    <label for="biografia">Biografia:</label>
    <textarea type="text" v-model="biografia" autocomplete="on"  required></textarea>

    <label for="cidade">Cidade:</label>
    <input type="text" v-model="cidade" placeholder="Cidade" autocomplete="on" required>

    <label for="data_nascimento">Data de Nascimento:</label>
    <input type="date" v-model="data_nascimento" autocomplete="on" required>

    <label for="estado">Estado:</label>
    <select v-model="estado" required>
      <option value="">Selecione o Estado</option>
      <option value="AC">Acre</option>
      <option value="AL">Alagoas</option>
      <option value="AP">Amapá</option>
      <option value="AM">Amazonas</option>
      <option value="BA">Bahia</option>
      <option value="CE">Ceará</option>
      <option value="DF">Distrito Federal</option>
      <option value="ES">Espírito Santo</option>
      <option value="GO">Goiás</option>
      <option value="MA">Maranhão</option>
      <option value="MT">Mato Grosso</option>
      <option value="MS">Mato Grosso do Sul</option>
      <option value="MG">Minas Gerais</option>
      <option value="PA">Pará</option>
      <option value="PB">Paraíba</option>
      <option value="PR">Paraná</option>
      <option value="PE">Pernambuco</option>
      <option value="PI">Piauí</option>
      <option value="RJ">Rio de Janeiro</option>
      <option value="RN">Rio Grande do Norte</option>
      <option value="RS">Rio Grande do Sul</option>
      <option value="RO">Rondônia</option>
      <option value="RR">Roraima</option>
      <option value="SC">Santa Catarina</option>
      <option value="SP">São Paulo</option>
      <option value="SE">Sergipe</option>
      <option value="TO">Tocantins</option>
    </select>

    <Div>
      <label for="linguagens">Linguagens de Programação</label>
      <input type="checkbox" v-model="linguagens" value="CSS" /> CSS
      <input type="checkbox" v-model="linguagens" value="JS" /> JS
      <input type="checkbox" v-model="linguagens" value="HTML" /> HTML
    </Div>

    <button type="submit">Mostrar Dados</button>
    <div id="dados"></div>

    <div v-if="dadosExibidos" id="dadosFinais">
      <h2>Dados do Formulário</h2>
      <p><strong>Nome:</strong> {{ nome }}</p>
      <p><strong>Nasceu em:</strong> {{ data_nascimento }}</p>
      <p><strong>Biografia:</strong> {{ biografia }}</p>
      <p><strong>Email:</strong> {{ email }}</p>
      <p><strong>Senha:</strong> {{ senha }}</p>
      <p><strong>Endereço:</strong> {{ endereco }}</p>
      <p><strong>Cidade:</strong> {{ cidade }}</p>
      <p><strong>Estado:</strong> {{ estado }}</p>
      <p><strong>Linguagens de programação:</strong> {{ linguagens[0] }}, {{ linguagens[1] }}, {{ linguagens[2] }}</p>

    </div>
  </form>
</template>



<style scoped>
.dadosFinais {
  margin-right: 0%;
}

body {
  background-color: black;
}

label,
select {
  display: block;
  text-align: center;
  margin-right: 10px;
}

form {
  background-color: orangered;
  display: block;
  width: 600px;
  height: 950px;
  text-align: center;
  border-radius: 10px;
  margin-left: 50%;
}

input,
option {
  margin-bottom: 10px;
  text-align: center;
  border-radius: 10px;

}

button {
  background-color: black;
  color: aliceblue;
  border-radius: 15px;
  margin-top: 30px;
}

select {
  text-align: center;
  border-radius: 10px;
  margin-left: 230px;
}
</style>
