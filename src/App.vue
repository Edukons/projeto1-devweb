<script>
import { ref } from 'vue'

const dados = ref('')

function mostrarDados() {
  const nome = document.getElementById("nome").value;
  const senha = document.getElementById("senha").value;
  const confirma_senha = document.getElementById("confirma_senha").value;
  const email = document.getElementById("email").value;
  const biografia = document.getElementById("biografia").value;
  const endereco = document.getElementById("endereco").value;
  const data_nascimento = document.getElementById("data_nascimento").value;
  const cidade = document.getElementById("cidade").value;
  const estado = document.getElementById("estado").value;

  if (nome === "" || senha === "" || confirma_senha === "" || email === "" || biografia === "" || endereco === "" || cidade === "" || estado === "" || data_nascimento === "")  {
    alert("Por favor, preencha todos os campos!");
  } else if (senha != confirma_senha) {
    alert("As senhas não coincidem!");
  } else {
    dados.value = "Nome: " + nome  + "Senha: " + senha  + "Email: " + email  + "Endereço: " + endereco  + "Biografia: " + biografia + "Cidade:" + cidade + "Estado:" + estado + "Data de nascimento:" + data_nascimento;
    document.getElementById("dados").innerHTML = dados.value;
  } 
}
</script>

<template>
  
  <form @submit.prevent="mostrarDados">
    <h1>Formulário de Cadastro</h1>
    <label for="nome">Nome:</label>
    <input type="text" id="nome" name="nome" minlength="3" maxlength="20" required>

    <label for="email">E-mail:</label>
    <input type="email" id="email" name="email" required>

    <label for="senha">Senha:</label>
    <input type="password" id="senha" name="senha" minlength="6" required>

    <label for="confirma_senha">Confirme a Senha:</label>
    <input type="password" id="confirma_senha" name="confirma_senha" minlength="6" required>

    <label for="data_nascimento">Data de Nascimento:</label>
    <input type="date" id="data_nascimento" name="data_nascimento" required>

    <label for="endereco">Endereço:</label>
    <input type="text" id="endereco" name="endereco" required>

    <label for="biografia">Biografia:</label>
    <input type="text" id="biografia" name="biografia" required>

    <label for="cidade">Cidade:</label>
    <input type="text" id="cidade" name="cidade" required>

    <label for="estado">Estado:</label>
    <select id="estado" name="estado" required>
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

    <button type="submit">Mostrar Dados</button>
    <div id="dados"></div>

  </form>
</template>



<style scoped>
template{
  background-color: black;
}
label,
select {
  display: block;
  text-align: center;
  margin-right: 10px;
}
form{
  background-color: orangered;
  display: block;
  width: 500px;
  text-align: center;
  border-radius: 10px;
  
}
input,option{
  margin-bottom: 10px;
  text-align: center;
  border-radius: 10px;

}
select{
  text-align: center;
  border-radius: 10px;
  margin-left: 175px;
}
</style>
