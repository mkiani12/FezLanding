<template>
  <section id="remote-sensing" class="w-full lg:pb-24 pb-12 bg-[#FAFAFA]">
    <BaseSection class="lg:max-w-[1200px]">
      <div class="col-span-12 text-black text-left lg:pt-24 lg:pb-22 pt-12">
        <div class="lg:grid lg:grid-cols-12 gap-x-16 py-10">
          <div
            class="lg:col-span-6 max-w-full mb-5 lg:mb-0 flex flex-col justify-center"
          >
            <h1 class="lg:text-5xl text-3xl font-bold mb-8 uppercase">
              Contact Us
            </h1>
            <p class="lg:pr-6">
              Have questions or inquiries about FEZtool? We're here to help!
              Whether you're seeking assistance with our products, have feedback
              to share, or simply want to learn more about our services, our
              dedicated team is ready to assist you. Feel free to reach out to
              us through the contact form below, and we'll get back to you as
              soon as possible. Alternatively, you can also connect with us via
              email at support@feztool.com or through our social media channels.
              We value your input and look forward to hearing from you!
            </p>
          </div>
          <div class="lg:col-span-6 max-w-full">
            <div class="bg-white p-10 rounded-2xl">
              <label
                for="email"
                class="block mb-2 text-sm font-medium text-gray-900 dark:text-white"
                >Your email</label
              >
              <input
                type="email"
                id="email"
                aria-describedby="helper-text-explanation"
                class="bg-gray-50 mb-5 border border-gray-300 text-gray-900 text-sm rounded-lg block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white"
                placeholder="name@flowbite.com"
              />
              <label
                for="message"
                class="block mb-2 text-sm font-medium text-gray-900 dark:text-white"
              >
                Message
              </label>
              <textarea
                id="message"
                rows="4"
                class="block mb-5 p-2.5 w-full text-sm text-gray-900 bg-gray-50 rounded-lg border border-gray-300 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white"
                placeholder="Your message..."
              ></textarea>
              <base-button class="px-8 py-3 bg-[#72B01D] text-white font-bold">
                Send Message
              </base-button>
            </div>
          </div>
        </div>
      </div>
    </BaseSection>
  </section>
</template>

<script setup lang="ts"></script>

<style scoped></style>
