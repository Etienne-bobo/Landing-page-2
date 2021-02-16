<template>
  <div>
    <nav
      :class="{ 'scrolled': !view.atTopOfPage }"
      class="fixed flex w-full bg-white items-center justify-between flex-wrap py-3 m-auto px-4 top-0 animated"
    >
      <div
        class="container mx-auto flex flex-wrap items-center justify-between"
      >
        <div
          class="w-full relative flex justify-between lg:w-auto lg:static lg:block lg:justify-start"
        >
          <a
            class="text-xl mr-12 font-bold leading-relaxed inline-block py-2 whitespace-no-wrap uppercase text-black"
            href="https://www.creative-tim.com/learning-lab/tailwind-starter-kit#/presentation"
          >Nodivo</a><button
            class="cursor-pointer text-xl leading-none px-3 py-1 border border-solid border-transparent rounded bg-transparent block lg:hidden outline-none focus:outline-none"
            type="button"
            @click="drawer()"
          >
            <span class="material-icons text-6xl"> view_list </span>
          </button>
        </div>
        <div
          class="lg:flex flex-grow items-center bg-white lg:bg-transparent lg:shadow-none"
          :class="{ hidden: !showMenu, block: showMenu }"
        >
          <ul class="flex flex-col lg:flex-row list-none mr-auto">
            <li class="flex items-center">
              <div>
                <div class="dropdown inline-block relative">
                  <button class="bg-gray-300 font-semibold py-2 px-4 rounded inline-flex items-center">
                    <span class="mr-1">Platforme</span>
                    <svg class="fill-current h-4 w-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20"><path d="M9.293 12.95l.707.707L15.657 8l-1.414-1.414L10 10.828 5.757 6.586 4.343 8z" /> </svg>
                  </button>
                  <ul class="dropdown-menu absolute hidden text-gray-700 pt-1">
                    <li class="">
                      <a class="rounded-t bg-gray-200 hover:bg-gray-400 py-2 px-4 block whitespace-no-wrap" href="#">Application web</a>
                    </li>
                    <li class="">
                      <a class="bg-gray-200 hover:bg-gray-400 py-2 px-4 block whitespace-no-wrap" href="#">Application mobile</a>
                    </li>
                  </ul>
                </div>
              </div>
            </li>
          </ul>
          <ul class="flex flex-col lg:flex-row list-none lg:ml-auto">
            <li class="flex items-center">
              <button
                type="button"
                class="flex border border-green-500 bg-green-500 text-white rounded-md px-4 py-2 m-2 transition duration-500 ease select-none hover:bg-green-600 focus:outline-none focus:shadow-outline"
              >
                <span class="material-icons mr-2">
                  language
                </span>
                Comment ca marche?
              </button>
            </li>
            <li class="flex items-center">
              <button
                type="button"
                class="flex item-cemter border border-blue-600 text-blue-600 rounded-md px-4 py-2 m-2 transition duration-500 ease select-none hover:bg-blue-500 hover:text-white focus:outline-none focus:shadow-outline"
              >
                <span class="material-icons mr-2">
                  import_contacts
                </span>
                Blog
              </button>
            </li>
            <li class="flex items-center">
              <svg class="svg-icon" viewBox="0 0 20 20">
                <path fill="none" d="M11.344,5.71c0-0.73,0.074-1.122,1.199-1.122h1.502V1.871h-2.404c-2.886,0-3.903,1.36-3.903,3.646v1.765h-1.8V10h1.8v8.128h3.601V10h2.403l0.32-2.718h-2.724L11.344,5.71z" />
              </svg>
            </li>
            <li class="flex items-center">
              <svg class="svg-icon" viewBox="0 0 20 20">
                <path fill="none" d="M18.258,3.266c-0.693,0.405-1.46,0.698-2.277,0.857c-0.653-0.686-1.586-1.115-2.618-1.115c-1.98,0-3.586,1.581-3.586,3.53c0,0.276,0.031,0.545,0.092,0.805C6.888,7.195,4.245,5.79,2.476,3.654C2.167,4.176,1.99,4.781,1.99,5.429c0,1.224,0.633,2.305,1.596,2.938C2.999,8.349,2.445,8.19,1.961,7.925C1.96,7.94,1.96,7.954,1.96,7.97c0,1.71,1.237,3.138,2.877,3.462c-0.301,0.08-0.617,0.123-0.945,0.123c-0.23,0-0.456-0.021-0.674-0.062c0.456,1.402,1.781,2.422,3.35,2.451c-1.228,0.947-2.773,1.512-4.454,1.512c-0.291,0-0.575-0.016-0.855-0.049c1.588,1,3.473,1.586,5.498,1.586c6.598,0,10.205-5.379,10.205-10.045c0-0.153-0.003-0.305-0.01-0.456c0.7-0.499,1.308-1.12,1.789-1.827c-0.644,0.28-1.334,0.469-2.06,0.555C17.422,4.782,17.99,4.091,18.258,3.266" />
              </svg>
            </li>
            <li class="flex items-center">
              <svg class="svg-icon" viewBox="0 0 20 20">
                <path fill="none" d="M14.52,2.469H5.482c-1.664,0-3.013,1.349-3.013,3.013v9.038c0,1.662,1.349,3.012,3.013,3.012h9.038c1.662,0,3.012-1.35,3.012-3.012V5.482C17.531,3.818,16.182,2.469,14.52,2.469 M13.012,4.729h2.26v2.259h-2.26V4.729z M10,6.988c1.664,0,3.012,1.349,3.012,3.012c0,1.664-1.348,3.013-3.012,3.013c-1.664,0-3.012-1.349-3.012-3.013C6.988,8.336,8.336,6.988,10,6.988 M16.025,14.52c0,0.831-0.676,1.506-1.506,1.506H5.482c-0.831,0-1.507-0.675-1.507-1.506V9.247h1.583C5.516,9.494,5.482,9.743,5.482,10c0,2.497,2.023,4.52,4.518,4.52c2.494,0,4.52-2.022,4.52-4.52c0-0.257-0.035-0.506-0.076-0.753h1.582V14.52z" />
              </svg>
            </li>
          </ul>
        </div>
      </div>
      <transition
        enter-class="opacity-0"
        enter-active-class="ease-out transition-medium"
        enter-to-class="opacity-100"
        leave-class="opacity-100"
        leave-active-class="ease-out transition-medium"
        leave-to-class="opacity-0"
      >
        <div
          v-show="isOpen"
          class="z-10 fixed inset-0 transition-opacity"
          @keydown.esc="isOpen = false"
        >
          <div
            class="absolute inset-0 bg-black opacity-50"
            tabindex="0"
            @click="isOpen = false"
          />
        </div>
      </transition>
      <aside
        class="transform top-0 left-0 w-64 text-gray-800 bg-white fixed h-full overflow-auto ease-in-out transition-all duration-300 z-30"
        :class="isOpen ? 'translate-x-0' : '-translate-x-full'"
      >
        <span
          class="flex items-center p-4 hover:bg-white hover:text-blue-500 "
          @click="isOpen = false"
        >
          <span class="font-semibold text-xl text-blue-500">Nodivo</span></span>
        <span
          class="flex items-center text-gray-800 p-4 hover:bg-indigo-500 active:bg-blue-500 hover:text-white "
          @click="isOpen = false"
        >
          <span class="material-icons mr-2">
            language
          </span>
          <span>Comment Ca marche?</span></span>
        <span
          class="flex items-center p-4 hover:bg-indigo-500 hover:text-white "
          @click="isOpen = false"
        ><span class="material-icons mr-2">
           adb
         </span>
          <span>Application Mobile</span></span>
        <span
          class="flex items-center p-4 hover:bg-indigo-500 hover:text-white "
          @click="isOpen = false"
        ><span class="material-icons mr-2">
           local_mall
         </span>
          <span>Application Web</span></span>
        <span
          class="flex items-center p-4 hover:bg-indigo-500 hover:text-white "
          @click="isOpen = false"
        ><span class="material-icons mr-2">
           import_contacts
         </span>
          <span>Blog</span></span>
        <div class="fixed bottom-0 w-full">
          <button
            class="flex items-center p-4 hover:text-white hover:bg-blue-600 w-full"
          >
            <span class="material-icons mr-2">
              help
            </span>
            <span>Aide</span>
          </button>
          <button
            class="flex items-center p-4 hover:text-white hover:bg-blue-600 w-full"
          >
            <span class="material-icons mr-2">
              face
            </span>
            <span>A propos</span>
          </button>
        </div>
      </aside>
    </nav>
  </div>
</template>
<script>
export default {
  data () {
    return {
      showMenu: false,
      isOpen: false,
      view: {
        atTopOfPage: true
      }
    }
  },
  watch: {
    isOpen: {
      immediate: true,
      handler (isOpen) {
        if (process.client) {
          if (isOpen) { document.body.style.setProperty('overflow', 'hidden') } else { document.body.style.removeProperty('overflow') }
        }
      }
    }
  },
  beforeMount () {
    window.addEventListener('scroll', this.handleScroll)
  },
  mounted () {
    document.addEventListener('keydown', (e) => {
      if (e.keyCode === 27 && this.isOpen) { this.isOpen = false }
    })
  },

  methods: {
    drawer () {
      this.isOpen = !this.isOpen
    },
    handleScroll () {
      // when the user scrolls, check the pageYOffset
      if (window.pageYOffset > 0) {
        // user is scrolled
        if (this.view.atTopOfPage) { this.view.atTopOfPage = false }
      } else {
        // user is at top of page
        // eslint-disable-next-line no-lonely-if
        if (!this.view.atTopOfPage) { this.view.atTopOfPage = true }
      }
    }
  }
}
</script>
<style scoped>
nav {
    z-index: 10
}

nav.scrolled {
    @apply shadow-2xl;
    border-bottom: 0px;
}
.svg-icon {
  width: 1em;
  height: 1em;
  margin: 0px 10px;
}

.svg-icon path,
.svg-icon polygon,
.svg-icon rect {
  fill: #4691f6;
}

.svg-icon circle {
  stroke: #4691f6;
  stroke-width: 1;
}
.dropdown:hover .dropdown-menu {
  display: block;
}

</style>
