<template>
    <nav class="bg-white shadow-md">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between items-center py-3">
          <!-- Logo -->
          <a href="/" class="text-xl font-semibold text-gray-700 hover:text-gray-900">
            Clinic Name
          </a>
          <!-- Primary Navigation -->
          <ul class="flex space-x-4 sm:space-x-6 lg:space-x-8 text-gray-600">
            <li><a href="#" class="hover:text-blue-600">Home</a></li>
            <li><a href="#" class="hover:text-blue-600">About Us</a></li>
            <li><a href="#" class="hover:text-blue-600">Services</a></li>
            <li><a href="#" class="hover:text-blue-600">Doctors</a></li>
            <li><a href="#" class="hover:text-blue-600">Contact</a></li>
          </ul>
          <!-- Contact Button -->
          <a href="#" class="text-white px-4 py-2 rounded bg-indigo-500
                hover:bg-indigo-700 transition-colors">
            Make an Appointment
          </a>
        </div>
      </div>
    </nav>
  </template>
  
  <script>
  export default {
    name: "ClinicNavbar"
  }
  </script>
  
  <style scoped>
  /* You can add additional scoped CSS styles here if needed */
  </style>
  