<template>
  <div class="relative">
    <div class="relative pt-6 ">
      <Popover>
        <div class="mx-auto max-w-7xl px-4 sm:px-6">
          <nav
            class="relative flex items-center justify-between sm:h-10 md:justify-center"
            aria-label="Global"
          >
            <div
              class="flex flex-1 items-center md:absolute md:inset-y-0 md:left-0"
            >
              <div class="flex w-full items-center justify-between md:w-auto">
                <a href="#">
                  <div class="flex items-center">
                    <span class="sr-only">Tek Jones</span>
                    <img
                      class="mr-4 h-16 w-auto"
                      src="../../public/assets/logo-main.png"
                      alt=""
                    />
                    <h6
                      class="text-primary font-termina text-2xl uppercase leading-none"
                    >
                      Tek <br />
                      Jones
                    </h6>
                  </div>
                </a>
                <div class="-mr-2 flex items-center md:hidden">
                  <PopoverButton
                    class="text-primary hover:text-secondary-200 focus:ring-secondary inline-flex items-center justify-center rounded-md p-2 focus:outline-none focus:ring-2 focus:ring-inset"
                  >
                    <span class="sr-only">Open main menu</span>
                    <MenuIcon class="h-8 w-8" aria-hidden="true" />
                  </PopoverButton>
                </div>
              </div>
            </div>

            <div
              class="hidden md:absolute md:inset-y-0 md:right-0 md:flex md:items-center md:justify-end"
            >
              <div class="hidden md:flex md:items-center md:space-x-10">
                <a
                  v-for="item in navigation"
                  :key="item.name"
                  :href="item.href"
                  class="font-termina text-bar hover:text-secondary text-2xl"
                  >{{ item.name }}</a
                >
                <img src="../../public/assets/ellipse.png" alt="" />
              </div>
            </div>
          </nav>
        </div>

        <transition
          enter-active-class="duration-150 ease-out"
          enter-from-class="opacity-0 scale-95"
          enter-to-class="opacity-100 scale-100"
          leave-active-class="duration-100 ease-in"
          leave-from-class="opacity-100 scale-100"
          leave-to-class="opacity-0 scale-95"
        >
          <PopoverPanel
            focus
            class="absolute inset-x-0 top-0 z-10 origin-top-right transform p-2 transition md:hidden"
          >
            <div
              class="overflow-hidden rounded-lg bg-white shadow-md ring-1 ring-black ring-opacity-5"
            >
              <div class="flex items-center justify-between px-5 pt-4">
                <div>
                  <img
                    class="h-8 w-auto"
                    src="https://tailwindui.com/img/logos/workflow-mark-indigo-600.svg"
                    alt=""
                  />
                </div>
                <div class="-mr-2">
                  <PopoverButton
                    class="inline-flex items-center justify-center rounded-md bg-white p-2 text-gray-400 hover:bg-gray-100 hover:text-gray-500 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-indigo-500"
                  >
                    <span class="sr-only">Close menu</span>
                    <XIcon class="h-8 w-8" aria-hidden="true" />
                  </PopoverButton>
                </div>
              </div>
              <div class="px-2 pt-2 pb-3">
                <a
                  v-for="item in navigation"
                  :key="item.name"
                  :href="item.href"
                  class="font-termina block rounded-md px-3 py-2 text-base font-medium text-gray-700 hover:bg-gray-50 hover:text-gray-900"
                  >{{ item.name }}</a
                >
              </div>
              <a
                href="#"
                class="block w-full bg-gray-50 px-5 py-3 text-center font-medium text-indigo-600 hover:bg-gray-100"
              >
                Log in
              </a>
            </div>
          </PopoverPanel>
        </transition>
      </Popover>
      
    </div>
  </div>
</template>

<script>
  import { Popover, PopoverButton, PopoverPanel } from "@headlessui/vue";
  import { MenuIcon, XIcon } from "@heroicons/vue/outline";

  const navigation = [
    { name: "WORK", href: "#" },
    { name: "ABOUT", href: "#" },
  ];

  export default {
    components: {
      Popover,
      PopoverButton,
      PopoverPanel,
      MenuIcon,
      XIcon,
    },
    setup() {
      return {
        navigation,
      };
    },
  };
</script>

<style></style>
