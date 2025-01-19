<template>
  <section id="request-demo" class="w-full lg:pb-24 pb-12 bg-[#FAFAFA]">
    <BaseSection class="lg:max-w-[1200px]">
      <div class="col-span-12 text-black text-left lg:pt-24 lg:pb-22 pt-12">
        <div class="lg:grid lg:grid-cols-12 gap-x-16 py-10">
          <div
            class="lg:col-span-6 max-w-full mb-5 lg:mb-0 flex flex-col justify-center"
          >
            <h1 class="lg:text-5xl text-3xl font-bold mb-8 uppercase">
              Request Demo
            </h1>
            <p class="lg:pr-6">
              Curious about FEZtool and how it can transform your geology
              projects? We're excited to give you a firsthand experience! Fill
              out the form below with your details, and we'll send you a demo
              registration link to explore FEZtool's powerful features. Whether
              you're looking for advanced tools, innovative solutions, or just a
              sneak peek at what we offer, this demo is the perfect starting
              point. Have questions? Feel free to reach out to us at
              <a class="text-[#72B01D]" href="mailto:support@feztool.com"
                >support@feztool.com</a
              >
              or connect with us on our social media channels. We're here to
              help and can't wait to show you what FEZtool can do!
            </p>
          </div>
          <div class="lg:col-span-6 max-w-full">
            <div class="bg-white p-10 rounded-2xl">
              <label
                for="email"
                class="block mb-2 text-sm font-medium text-gray-900"
                >Your email</label
              >
              <input
                type="email"
                id="email"
                aria-describedby="helper-text-explanation"
                class="bg-gray-50 mb-5 border border-gray-300 text-gray-900 text-sm rounded-lg block w-full p-2.5"
                placeholder="name@feztool.com"
              />
              <label
                for="company"
                class="block mb-2 text-sm font-medium text-gray-900"
                >Your company name</label
              >
              <input
                type="company"
                id="company"
                aria-describedby="helper-text-explanation"
                class="bg-gray-50 mb-5 border border-gray-300 text-gray-900 text-sm rounded-lg block w-full p-2.5"
                placeholder="FEZtool"
              />
              <label
                for="message"
                class="block mb-2 text-sm font-medium text-gray-900"
              >
                Message
              </label>
              <textarea
                id="message"
                rows="2"
                class="block mb-5 p-2.5 w-full text-sm text-gray-900 bg-gray-50 rounded-lg border border-gray-300"
                placeholder="Your message..."
              ></textarea>
              <base-button class="px-8 py-3 bg-[#72B01D] text-white font-bold">
                Send Request
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
