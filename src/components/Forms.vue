<template>
  <div class="contentall">
    <h1>Formulário </h1>
    <form id="form">
        <!-- Se houver um erro de CEP inválido, exibe a mensagem -->
        <p v-if="cepInvalido" style="color: red;">CEP inválido. Por favor, insira um CEP válido.</p>

        <!-- Todos os campos para que o usuário preencha o formulário-->
        <div>
          <input type="text" class="inputs" id="nome" placeholder="Nome" v-model="formData.nome" required>
          <span class="span-required">Nome deve ter no mínimo 3 caracteres</span>
        </div>
        <div>
          <input type="email" class="inputs" id="email" placeholder="E-mail" v-model="formData.email" required>
          <span class="span-required">Insira um e-mail válido</span>
        </div>
        <div>
          <input type="text" class="inputs" id="endereco" placeholder="Logradouro, Bairro" v-model="logradouro" required>
        </div>
        <div>
          <input type="text" class="inputs" id="cidade" placeholder="Cidade" v-model="cidade" required>
        </div>
        <div>
          <input type="text" class="inputs" id="uf" placeholder="UF" v-model="uf" required>
        </div>
        <div>
          <input type="text" class="inputs" id="cep" placeholder="CEP, ex: 00000-000" v-model="cep" @blur="buscarCEP" required>
        </div> 
        <p>Origem: </p>
            <div class="box-selector">
              <div> 
                <input type="radio" id="formulorigemD" name="formulorigem"  value="digital"> 
                <label for="formulorigemD"> Digital</label> 
              </div>
              <div>
                <input type="radio" id="formulorigemF" name="formulorigem" value="fisico"> 
                <label for="formulorigemF"> Físico</label>
              </div>
            </div>
    </form>
    <button type="submit" id="botaoparasubmit">Enviar Formulário</button>
    <button type="submit" @click="verCadastros">Ver Cadastros</button>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      formData: {
        nome: '',
        email: '',
        origem: 'digital'
      },
      logradouro: '',
      cidade: '',
      uf: '',
      cep: '',
      cepInvalido: true // Inicialmente, não há erro de CEP inválido
    };
  },
  methods: {
    async buscarCEP() {
      if (this.cep.length === 8) {
        try {
          const response = await axios.get(`https://viacep.com.br/ws/${this.cep}/json/`);
          this.logradouro = response.data.logradouro;
          this.cidade = response.data.localidade;
          this.uf = response.data.uf;
          // Resetar o estado do erro se a busca for bem-sucedida [x]
          this.cepInvalido = false;
        } catch (error) {
          console.error('Erro ao buscar CEP:', error);
          // Definir o estado do erro como verdadeiro se houver um erro ao buscar o CEP [x]
          this.cepInvalido = true;
        }
      }
    },
    submitForm() {
      // Necessário criar lógica para enviar os dados para Vuex ou Pinia; []
      console.log('Dados enviados:', this.formData);
    },
    verCadastros() {
      // Redirecionar para a página ListaUsuarios
      this.$router.push({ name: 'ListaUsuarios' });
    },
  }
};

</script>
<style scoped>

@media (min-width: 1024px) {
  .bemvindo h1 {
    text-align: left;
  }
}
</style>