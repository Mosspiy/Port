<template>
  <div class="py-24 bg-gradient-to-b from-gray-900 to-gray-800" id="contact">
    <div class="container mx-auto px-6">
      <!-- Section Header -->
      <div class="text-center mb-16 text-3xl">
        <h2 class="text-4xl font-bold">Contact <span class="text-primary bg-clip-text text-purple-500">Me</span></h2>
        <div class="divider w-24 mx-auto bg-primary h-1 rounded my-4"></div>
        <p class="text-gray-300 max-w-full mx-auto text-lg">
          Looking for a fresh graduate for your team? Have an interesting project idea or collaboration opportunity? Let's connect!
        </p>
      </div>
      
      <div class="flex flex justify-center lg:flex-row gap-12">
        <!-- Contact Info -->
        <div class="w-xl lg:w-70px animate">
          <div class="card bg-gray-800 shadow-2xl rounded-2xl p-8 border border-gray-700 h-full">
            <h3 class="text-2xl font-bold mb-8 text-center">Let's Connect</h3>
            
            <div class="space-y-8">
              <div class="flex items-center gap-6 group">
                <div class="bg-gradient-to-br from-blue-500 to-purple-600 p-4 rounded-xl shadow-lg group-hover:shadow-blue-500/20 transition-all duration-300">
                  <i class="fas fa-map-marker-alt text-white text-xl"></i>
                </div>
                <div>
                  <h4 class="font-bold text-lg mb-1 text-gray-100">Location</h4>
                  <p class="text-gray-300 group-hover:text-gray-200 transition-colors duration-300">Saraburi, Thailand</p>
                </div>
              </div>
              
              <div class="flex items-center gap-6 group">
                <div class="bg-gradient-to-br from-blue-500 to-purple-600 p-4 rounded-xl shadow-lg group-hover:shadow-blue-500/20 transition-all duration-300">
                  <i class="fas fa-envelope text-white text-xl"></i>
                </div>
                <div>
                  <h4 class="font-bold text-lg mb-1 text-gray-100">Email</h4>
                  <a href="mailto:piyawat.c03@gmail.com" class="text-gray-300 hover:text-primary transition-colors duration-300">piyawat.c03@gmail.com</a>
                </div>
              </div>
              
              <div class="flex items-center gap-6 group">
                <div class="bg-gradient-to-br from-blue-500 to-purple-600 p-4 rounded-xl shadow-lg group-hover:shadow-blue-500/20 transition-all duration-300">
                  <i class="fas fa-phone text-white text-xl"></i>
                </div>
                <div>
                  <h4 class="font-bold text-lg mb-1 text-gray-100">Phone</h4>
                  <a href="tel:+66972987467" class="text-gray-300 hover:text-primary transition-colors duration-300">+66 972 987 467</a>
                </div>
              </div>              
            </div>
            
            <div class="mt-12">
              <h3 class="text-xl font-bold mb-6 text-center">Connect With Me</h3>
              <div class="flex flex-wrap justify-center gap-5 mt-5">
                <a href="https://resume.superresume.com/ViewResume?Key=OuqwdkNuRUygHHKvqCdNqEEUNxwCIZq3&Enc=XrrUTLg7uXqwX32ccLcSMLWVVUM" target="_blank"
   class="btn btn-circle bg-gray-700 hover:bg-blue-600 border-0 w-15 h-15 flex items-center justify-center transition-all duration-300 hover:scale-110 shadow-lg">
  <img src="https://static.jobtopgun.com/company_image/1/5/logo_com_job/j5.gif?time=20250530172401" alt="JobTopGun" />
</a>
<a href="https://th.jobsdb.com/th/profile/ปิยะวัฒน์-โชติวรอานนท์-7J5KFNqq1f"
   class="btn btn-circle bg-gray-700 hover:bg-blue-600 border-0 w-15 h-15 flex items-center justify-center transition-all duration-300 hover:scale-110 shadow-lg">
  <img src="https://setaasia.com/wp-content/uploads/2024/07/support-jobsDb-logo135px-2.png" alt="JobsDB" />
</a>
<a href="https://jobbkk.com/resumes/preview_new/3903842" target="_blank"
   class="btn btn-circle bg-gray-700 hover:bg-blue-600 border-0 w-15 h-15 flex items-center justify-center transition-all duration-300 hover:scale-110 shadow-lg">
  <img src="https://nipponhaku.com/wp-content/uploads/2024/08/New-logo-Jobbkk-CO.png" alt="JobBKK" />
</a>
              </div>
            </div>
            
            <!-- Portfolio Availability -->
            <div class="mt-12 bg-gray-700 rounded-xl overflow-hidden shadow-lg">
              <div class="py-8 px-6 text-center">
                <i class="fas fa-graduation-cap text-primary text-3xl mb-4"></i>
                <h4 class="font-bold mb-2">Recent Graduate</h4>
                <p class="text-gray-300">Available for job opportunities</p>
                <p class="text-gray-300">Open to freelance projects & collaborations</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const form = ref({
  name: '',
  email: '',
  subject: '',
  message: ''
});

const formSubmitting = ref(false);
const formSuccess = ref(false);

const submitForm = () => {
  formSubmitting.value = true;
  
  // Simulate form submission
  setTimeout(() => {
    formSubmitting.value = false;
    formSuccess.value = true;
    
    // Reset form
    form.value = {
      name: '',
      email: '',
      subject: '',
      message: ''
    };
    
    // Hide success message after 5 seconds
    setTimeout(() => {
      formSuccess.value = false;
    }, 5000);
  }, 1500);
};
</script>