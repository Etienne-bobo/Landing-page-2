<template>
  <div class="mx-auto md:px-4 max-w-7xl relative overflow-hidden pb-6">
    <div class="container mx-auto relative">
      <div class="flex flex-col md:flex-row items-center pt-32 pb-16 md:pb-0">
        <div class="md:w-1/2 lg:w-3/5 mx-auto mb-4 sm:mb-16 md:mb-0">
          <h2 class="lg:text-3xl text-2xl font-bold text-blue-600 uppercase mb-2">
            Bienvenue Chez Nodivo
          </h2>
          <h1 class="text-3xl lg:text-5xl font-bold text-secondary leading-tight mb-6 md:mb-10">
            Acceder a la Platforme
          </h1>
          <div class="flex items-center md:ml-0 ml-10">
            <button
              type="button"
              class="flex bg-blue-500 text-white rounded-md px-4 py-2 m-2 transition duration-500 ease select-none hover:bg-blue-600 focus:outline-none focus:shadow-outline"
            >
              <span class="material-icons mr-2">
                adb
              </span>
              Mobile
            </button>
            <button
              type="button"
              class="flex border border-green-500 bg-green-500 text-white rounded-md px-4 py-2 m-2 transition duration-500 ease select-none hover:bg-green-600 focus:outline-none focus:shadow-outline"
            >
              <span class="material-icons mr-2">
                local_mall
              </span>
              Web
            </button>
          </div>
        </div>
        <div class="mt-16 sm:mt-0 flex-1 flex justify-end">
          <img src="../../static/images/header.jpeg">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {

}
</script>
