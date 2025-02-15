<template>
  <nav
    id="navbar"
    class="fixed top-0 z-10 w-full text-neutral-800 border-b border-b-[#FFFFFF14] backdrop-blur-lg"
    :class="{ 'bg-[#0D0A0B]': scrollY < 500, 'bg-[#0D0A0B70]': scrollY >= 500 }"
  >
    <div
      class="flex flex-col max-w-screen-2xl px-8 mx-auto lg:items-center lg:justify-between lg:flex-row relative"
    >
      <div
        class="flex flex-col lg:flex-row items-center space-x-4 xl:space-x-8"
      >
        <div
          class="w-full flex flex-row items-center justify-between py-[20px]"
        >
          <div>
            <img src="~/assets/img/logo/logo.svg" class="w-20" alt="FEZ Logo" />
          </div>
          <button
            class="rounded-lg lg:hidden focus:outline-none focus:shadow-outline text-white"
            @click="open = !open"
          >
            <SegmentIcon v-if="!open" class="text-lg" />
            <CloseIcon v-else class="text-lg" />
          </button>
        </div>
        <ul
          :class="[open ? 'flex' : 'hidden lg:flex']"
          class="w-auto !mr-auto h-auto flex flex-col lg:absolute text-[#D0D0D0] lg:top-[50%] lg:left-[50%] lg:translate-x-[-50%] lg:translate-y-[-50%] lg:items-center pb-4 lg:pb-0 lg:justify-center lg:flex-row origin-top duration-300 xl:space-x-5 space-y-3 lg:space-y-0 lg:!ml-0"
        >
          <a
            v-for="section in sections"
            :key="section.id"
            :href="'#' + section.id"
            :title="section.name"
            :class="{
              'text-white border-b border-b-white':
                activeSection === section.id,
            }"
            @click.prevent="scrollToSection(section.id)"
          >
            {{ section.name }}
          </a>
          <!-- <li class="relative group">
            <button
              class="md:px-4 py-2 text-sm bg-transparent rounded-lg text-[#666666] hover:text-gray-900 focus:outline-none focus:shadow-outline flex items-center"
              @click="dropdownToggler"
              @blur="dropdownToggler"
            >
              <span>Products</span>
              <ChevronUpIcon v-if="dropdownNavbar" class="text-base" />
              <ChevronDownIcon v-else class="text-base" />
            </button>
            <transition name="transform-fade-down">
              <ul
                v-if="dropdownNavbar"
                class="flex lg:absolute flex-col max-w-42 py-1 lg:bg-white rounded-md lg:shadow-md pl-2 lg:pl-0"
              >
                <li>
                  <a
                    href="#"
                    class="block py-2 px-4 text-sm text-gray-700 hover:bg-gray-100"
                    >Exchange</a
                  >
                </li>
                <li>
                  <a
                    href="#"
                    class="block py-2 px-4 text-sm text-gray-700 hover:bg-gray-100"
                    >Wallet</a
                  >
                </li>
                <li>
                  <a
                    href="#"
                    class="block py-2 px-4 text-sm text-gray-700 hover:bg-gray-100"
                    >Explorer</a
                  >
                </li>
                <li>
                  <a
                    href="#"
                    class="block py-2 px-4 text-sm text-gray-700 hover:bg-gray-100"
                    >Charts</a
                  >
                </li>
              </ul>
            </transition>
          </li> -->
        </ul>
      </div>
      <div
        :class="[open ? 'flex' : 'hidden lg:flex']"
        class="space-x-3 mb-5 lg:mb-0"
      >
        <a href="https://app.feztool.com">
          <base-button class="px-5 py-3 bg-[#F3EFF5] text-black font-bold">
            Login / Signup
          </base-button>
        </a>
      </div>
    </div>
  </nav>
</template>
<script lang="ts" setup>
import ChevronUpIcon from "~icons/material-symbols-light/keyboard-arrow-up-rounded";
import ChevronDownIcon from "~icons/material-symbols-light/keyboard-arrow-down-rounded";
import SegmentIcon from "~icons/material-symbols-light/segment-rounded";
import CloseIcon from "~icons/material-symbols-light/close-small-outline-rounded";

const open = ref(false);
const dropdownNavbar = ref(false);

const dropdownToggler = () => {
  dropdownNavbar.value = !dropdownNavbar.value;
};

const scrollY = ref(0);

const sections = ref([
  { name: "Introduction", id: "hero" },
  { name: "Tools", id: "remote-sensing" },
  { name: "Documentation", id: "documentation" },
  { name: "Our Team", id: "our-team" },
  { name: "Contact Us", id: "contact-us" },
  { name: "Collabs", id: "collabration" },
]);

const activeSection = ref("hero");

const handleScroll = () => {
  let scrollPosition = window.scrollY + 100; // Offset for navbar height

  for (let section of sections.value) {
    const el = document.getElementById(section.id);
    if (
      el &&
      el.offsetTop <= scrollPosition &&
      el.offsetTop + el.offsetHeight > scrollPosition
    ) {
      activeSection.value = section.id;
      break;
    }
  }

  updateScroll();
};

onMounted(() => {
  window.addEventListener("scroll", handleScroll);
});

onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll);
});

const scrollToSection = (id: string) => {
  const el = document.getElementById(id);
  if (el) {
    window.scrollTo({ top: el.offsetTop - 80, behavior: "smooth" }); // Adjust for navbar height
  }
};

// Function to update scrollY
const updateScroll = () => {
  scrollY.value = window.scrollY;
};
</script>
