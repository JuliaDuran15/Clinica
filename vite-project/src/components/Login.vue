<script setup>
</script>
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
              <h1 class="mb-10 text-center md:mb-16">Login to Your Account</h1>
              <form @submit.prevent="handleLogin">
                <div class="mb-6">
                  <input
                    type="email"
                    v-model="email"
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
                    v-model="password"
                    placeholder="Password"
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
                    Login
                  </button>
                </div>
              </form>
              <router-link
                to="/forgot-password"
                class="
                  mb-2
                  inline-block
                  text-base text-[#adadad]
                  hover:text-primary hover:underline
                "
              >
                Forgot Password?
              </router-link>
              
            </div>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script>
  import { ref } from 'vue';
  
  export default {
    setup() {
      const email = ref('');
      const password = ref('');
  
      const handleLogin = async () => {
        // Logic to handle login, e.g., call an API
        console.log('Attempting to login with:', email.value, password.value);
        // Example API call
        // axios.post('/api/login', { email: email.value, password: password.value })
        //   .then(response => {
        //     console.log('Login successful:', response);
        //   })
        //   .catch(error => {
        //     console.error('Login failed:', error);
        //   });
      };
  
      return { email, password, handleLogin };
    }
  };
  </script>
  
  <style scoped>
  /* Additional styles can be added here */
  </style>
  