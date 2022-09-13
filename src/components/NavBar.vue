<template>
  <div
    class="
      bg-gray-900
      text-gray-100
      py-3.5
      px-6
      shadow
      md:flex
      justify-between
      items-center
    "
  >
    <div class="flex items-center">
      <span class="text-green-500 text-xl mr-1 cursor-pointer">
        <i class="fa-brands fa-facebook-messenger"></i>
      </span>
      <h1 class="text-xl">Designer</h1>
    </div>

    <span
      @click="MenuOpen()"
      class="absolute md:hidden right-6 top-1.5 cursor-pointer text-3xl mt-1"
    >
      <i
        :class="[
          open ? 'fa-sharp fa-solid fa-xmark' : 'fa-sharp fa-solid fa-bars',
        ]"
      ></i>
    </span>

    <ul
      class="md:flex md:items-center md:px-0 px-10 md:pb-0 pb-10 md:static absolute bg-gray-900 md:w-auto w-full top-14 duration-700 ease-in
      "
      :class="[open ? 'left-0' : 'left-[100%]']"
    >
      <li class="md:mx-4 md:my-0 my-6" v-for="link in links" :key="link">
        <a :href="link.link" class="text-xl hover:text-green-500">
          {{ link.name }}
        </a>
      </li>

      <ButTon>Get Started</ButTon>
    </ul>
  </div>
</template>


<script>
import ButTon from "@/components/ButTon.vue";
// import { ref } from '@vue/reactivity'
export default {
  components: {
    ButTon,
  },
  data() {
    return {
      open: false,
      links: [
        { name: "Home", link: "#" },
        { name: "About", link: "#" },
        { name: "Help", link: "#" },
      ],
    };
  },
  methods: {
    MenuOpen() {
      this.open = !this.open;
    },
  },
  // setup() {
  //     let open = ref(false)
  //     let links = [
  //         {name : "Home", link : "#"},
  //         {name : "About", link : "#"},
  //         {name : "Help", link : "#"}
  //     ]

  //     function MenuOpen() {
  //         open.value = !open.value
  //     }

  //     return{links, open, MenuOpen}
  // }
};
</script>