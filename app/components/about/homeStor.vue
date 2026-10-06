<!-- app/components/sections/home/AboutStoreSection.vue -->

<template>
  <section class="bg-white py-16 px-28 max-md:px-8 max-lg:px-12">
    <div class="mx-auto text-right">
      <!-- Title -->
      <h2 class="mb-6 text-base font-bold text-gray-800">
        فروشگاه <span class="text-blue-600">سیسمونی جاوید</span> ، انتخابی شایسته
      </h2>

      <!-- Description -->
      <p
        class="mx-auto mb-8 text-base max-md:text-justify font-normal leading-9 text-gray-600"
      >
        {{ aboutData.description }}
      </p>

      <!-- CTA -->
      <NuxtLink
        :to="aboutData.ctaLink"
        class="inline-flex items-center justify-center rounded-lg bg-[#1c1395] px-6 py-3 text-sm font-medium text-white transition hover:opacity-90"
      >
        {{ aboutData.ctaText }}
      </NuxtLink>
    </div>
  </section>
</template>
<script setup lang="ts">
// ⛳️ بعداً فقط این data میاد از API / store
const aboutData = {
  title: "فروشگاه سیسمونی جاوید انتخابی شایسته",
  description: `سیسمونی جاوید متنوع‌ترین و با کیفیت‌ترین
  انواع وسایل مناسب کودک را در دسترس شما عزیزان قرار داده تا بتوانید متناسب با نیاز خود
  مدل دلخواه را انتخاب کنید.
  `,
  ctaText: "مشاهده بیشتر",
  ctaLink: "/about-us",
};
</script>
