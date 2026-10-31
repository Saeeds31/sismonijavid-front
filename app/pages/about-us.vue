<template>
  <main class="jb-about-page">
    <div class="container mx-auto px-4 md:px-8 lg:px-12 xl:px-28">
      <SharedBreadCrumb :items="[{ label: 'درباره ما', href: '/about-us' }]" />

      <AboutHeroCollage :image-src="aboutData.hero.imageSrc" :alt="aboutData.hero.alt"
        :fallback-src="aboutData.hero.fallbackSrc" />

      <AboutStorySection :title="aboutData.story.title" :paragraphs="aboutData.story.paragraphs"
        :highlight="aboutData.story.highlight" :image-src="aboutData.story.imageSrc"
        :image-alt="aboutData.story.imageAlt" :fallback-src="aboutData.story.fallbackSrc" />

      <AboutFAQSection />
    </div>
  </main>
</template>

<script setup>
import { computed } from "vue";

const defaultAbout = {
  hero: {
    imageSrc: "/about/Group.jpg",
    alt: "فروشگاه سیسمونی جاوید در گرگان",
    fallbackSrc: "/contact/Group.svg",
  },
  story: {
    title: "فروشگاه سیسمونی جاوید، انتخابی شایسته",
    paragraphs: [
      "مجموعه سیسمونی جاوید از سال ۱۳۹۵ فعالیت خود را با عشق و علاقه به دنیای کودکان آغاز کرد و با تلاش آقای رحیمی نژاد از یک فروشگاه محلی به یکی از فروشگاه‌های محبوب سیسمونی در سطح کشور تبدیل شد.",
      "ما همواره در تلاشیم با ارائه‌ی محصولات باکیفیت و قیمت‌های مناسب، بهترین تجربه‌ی خرید را برای والدین عزیز و کوچولوی دوست‌داشتنی‌شان فراهم کنیم.",
      "سیسمونی جاوید مجموعه‌ای متنوع از لباس نوزاد، اسباب‌بازی، لوازم بهداشتی و سیسمونی را در اختیار شما قرار می‌دهد تا متناسب با سلیقه و نیاز خود، بهترین انتخاب را داشته باشید.",
    ],
    highlight:
      "ما به دنبال ایجاد تعادل میان کیفیت، ایمنی و زیبایی برای کوچولوی شما هستیم. محصولاتی که با مواد باکیفیت، دوخت دقیق و دغدغه‌ی سلامت پوست نوزاد طراحی شده‌اند؛ چون برای ما، آرامش و لبخند کودک شما، مهم‌ترین است.",
    imageSrc: "/about/model-pink.jpg",
    imageAlt: "لباس نوزاد و سیسمونی باکیفیت در سیسمونی جاوید",
    fallbackSrc: "/contact/Group.svg",
  },
};

const { data } = await useAsyncData("about-page", async () => {
  return null;
});

const aboutData = computed(() => data.value ?? defaultAbout);
useSeoMeta({
  title: 'درباره ما | سیسمونی جاوید - فروشگاه سیسمونی و لوازم نوزاد در گرگان',
  description: 'آشنایی با فروشگاه سیسمونی جاوید؛ از سال ۱۳۹۵ با تلاش سه خواهر، ارائه‌دهنده لباس نوزاد، اسباب‌بازی و لوازم سیسمونی باکیفیت در گرگان و سراسر کشور.',
  ogTitle: 'درباره سیسمونی جاوید',
  ogDescription: 'داستان سیسمونی جاوید؛ از یک فروشگاه محلی در گرگان تا یکی از فروشگاه‌های محبوب سیسمونی در کشور.',
  ogImage: 'https://sismonijavid.ir/about/Group.jpg', // آدرس کامل تصویر هیرو
  ogUrl: 'https://sismonijavid.ir/about-us',
  ogType: 'website',
  twitterCard: 'summary_large_image',
  robots: 'index, follow',
})

useHead({
  link: [{ rel: 'canonical', href: 'https://sismonijavid.ir/about-us' }],
  script: [
    {
      type: 'application/ld+json',
      key: 'about-jsonld',
      innerHTML: JSON.stringify({
        '@context': 'https://schema.org',
        '@type': 'AboutPage',
        'mainEntity': {
          '@type': 'OnlineStore',
          'name': 'سیسمونی جاوید',
          'url': 'https://sismonijavid.ir',
          'logo': 'https://sismonijavid.ir/logo.png',
          'foundingDate': '2016', // سال ۱۳۹۵ شمسی ≈ ۲۰۱۶ میلادی
          'description': 'فروشگاه سیسمونی جاوید از سال ۱۳۹۵ با تلاش سه خواهر فعالیت خود را آغاز کرد و اکنون یکی از فروشگاه‌های محبوب سیسمونی در سطح کشور است.',
          'telephone': '+989375015769',
          'address': {
            '@type': 'PostalAddress',
            'streetAddress': 'خیابان سرخواجه، مجتمع آفتاب، طبقه همکف',
            'addressLocality': 'گرگان',
            'addressRegion': 'گلستان',
            'addressCountry': 'IR',
          },
          'sameAs': [
            'https://t.me/sismonijavid',
            'https://instagram.com/sismonijavid',
          ],
        },
      }),
    },
  ],
})
</script>

<style scoped>
.jb-about-page {
  padding-bottom: 80px;
  background: linear-gradient(135deg, #fff8fb 0%, #fff0f5 50%, #ffeaf2 100%);
  background-attachment: fixed;
  min-height: 100vh;
}
</style>