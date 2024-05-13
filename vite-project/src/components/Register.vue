<template>
    <section class="bg-[#F4F7FF] py-20 lg:py-[120px]">
      <div class="container mx-auto">
        <div class="-mx-4 flex flex-wrap">
          <div class="w-full px-4">
            <div
              class="
                relative
                mx-auto
                max-w-[525px]
                overflow-hidden
                rounded-lg
                bg-white
                py-16
                px-10
                text-center
                sm:px-12
                md:px-[60px]
              "
            >
              <h1 class="mb-10 text-center md:mb-16">Cadastro de Usuário</h1>
              <form @submit.prevent="handleSubmit">
                <div class="mb-6">
                  <input
                    type="text"
                    v-model="user.name"
                    placeholder="Nome"
                    required
                    class="
                      border-[#E9EDF4]
                      w-full
                      rounded-md
                      border
                      bg-[#FCFDFE]
                      py-3
                      px-5
                      text-base text-body-color
                      placeholder-[#ACB6BE]
                      outline-none
                      focus:border-primary
                      focus-visible:shadow-none
                    "
                  />
                </div>
  
                <div class="mb-6">
                  <input
                    type="email"
                    v-model="user.email"
                    placeholder="Email"
                    required
                    class="
                      border-[#E9EDF4]
                      w-full
                      rounded-md
                      border
                      bg-[#FCFDFE]
                      py-3
                      px-5
                      text-base text-body-color
                      placeholder-[#ACB6BE]
                      outline-none
                      focus:border-primary
                      focus-visible:shadow-none
                    "
                  />
                </div>
  
                <div class="mb-6">
                  <input
                    type="password"
                    v-model="user.password"
                    placeholder="Senha"
                    required
                    class="
                      border-[#E9EDF4]
                      w-full
                      rounded-md
                      border
                      bg-[#FCFDFE]
                      py-3
                      px-5
                      text-base text-body-color
                      placeholder-[#ACB6BE]
                      outline-none
                      focus:border-primary
                      focus-visible:shadow-none
                    "
                  />
                </div>
  
                <!-- Additional fields as in your example -->
                <div class="mb-6">
                  <input
                    type="text"
                    v-model="user.cep"
                    placeholder="CEP"
                    @blur="fetchCep"
                    required
                    class="
                      border-[#E9EDF4]
                      w-full
                      rounded-md
                      border
                      bg-[#FCFDFE]
                      py-3
                      px-5
                      text-base text-body-color
                      placeholder-[#ACB6BE]
                      outline-none
                      focus:border-primary
                      focus-visible:shadow-none
                    "
                  />
                </div>
  
                <div class="mb-6">
  <input type="text" id="rua" placeholder='Rua 'v-model="user.rua" required
         class="
           border-[#E9EDF4]
           w-full
           rounded-md
           border
           bg-[#FCFDFE]
           py-3
           px-5
           text-base text-body-color
           placeholder-[#ACB6BE]
           outline-none
           focus:border-primary
           focus-visible:shadow-none
         ">
</div>

<div class="mb-6">
  <input type="text" placeholder='Bairro 'id="bairro" v-model="user.bairro" required
         class="
           border-[#E9EDF4]
           w-full
           rounded-md
           border
           bg-[#FCFDFE]
           py-3
           px-5
           text-base text-body-color
           placeholder-[#ACB6BE]
           outline-none
           focus:border-primary
           focus-visible:shadow-none
         ">
</div>

<div class="mb-6">
  <input type="text" placeholder='Localidade' id="localidade" v-model="user.localidade" required
         class="
           border-[#E9EDF4]
           w-full
           rounded-md
           border
           bg-[#FCFDFE]
           py-3
           px-5
           text-base text-body-color
           placeholder-[#ACB6BE]
           outline-none
           focus:border-primary
           focus-visible:shadow-none
         ">
</div>

<div class="mb-6">
  <input type="text" placeholder='UF' id="uf" v-model="user.uf" required
         class="
           border-[#E9EDF4]
           w-full
           rounded-md
           border
           bg-[#FCFDFE]
           py-3
           px-5
           text-base text-body-color
           placeholder-[#ACB6BE]
           outline-none
           focus:border-primary
           focus-visible:shadow-none
         ">
</div>

<div class="mb-4">
  <label for="role" class="block text-gray-600 text-sm font-bold mb-2">Você é:</label>
  <select v-model="user.role" id="role" required
          class="
          border-[#E9EDF4]
           w-full
           rounded-md
           border
           bg-[#FCFDFE]
           py-3
           px-4
           text-base text-body-color
           placeholder-[#ACB6BE]
           outline-none
           focus:border-primary
           focus-visible:shadow-none
          ">
    <option disabled value="">Selecione uma opção</option>
    <option>Paciente</option>
    <option>Doutor</option>
    <option>Secretaria</option>
  </select>
</div>
                <!-- Other address fields also styled similarly -->
  
                <div class="mb-10">
                  <button
                    type="submit"
                    class="
                      w-full
                      px-4
                      py-3
                      bg-indigo-500
                      hover:bg-indigo-700
                      rounded-md
                      text-white
                    "
                  >
                    Cadastrar
                  </button>
                </div>
              </form>
            </div>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script>
  import axios from 'axios';
  
  export default {
    name: 'RegisterForm',
    data() {
      return {
        user: {
          name: '',
          email: '',
          password: '',
          cep: ''
          // Include other fields if necessary
        }
      };
    },
    methods: {
      fetchCep() {
        const cep = this.user.cep.replace(/\D/g, ''); // Remove non-numeric characters
        if (cep.length === 8) {
          axios.get(`https://viacep.com.br/ws/${cep}/json/`)
            .then(response => {
              const data = response.data;
              if (data.erro) {
                alert('CEP não encontrado.');
              } else {
                // Assign data to user object fields if necessary
              }
            })
            .catch(error => {
              console.error('Erro ao obter dados do CEP:', error);
              alert('Erro ao obter dados do CEP. Por favor, tente novamente.');
            });
        } else {
          alert('CEP inválido. Digite apenas os números.');
        }
      },
      handleSubmit() {
        console.log('User Registration:', this.user);
        // Placeholder for actual submission logic
        alert('Cadastro submetido! Verifique o console para os detalhes.');
      }
    }
  };
  </script>
  