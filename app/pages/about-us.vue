<template>
  <main class="jb-about-page">
    <div class="container mx-auto px-4 md:px-8 lg:px-12 xl:px-28">
      <SharedBreadCrumb :items="[{ label: 'درباره ما', href: '/about-us' }]" />

      <AboutHeroCollage
        :image-src="aboutData.hero.imageSrc"
        :alt="aboutData.hero.alt"
        :fallback-src="aboutData.hero.fallbackSrc"
      />

      <AboutStorySection
        :title="aboutData.story.title"
        :paragraphs="aboutData.story.paragraphs"
        :highlight="aboutData.story.highlight"
        :image-src="aboutData.story.imageSrc"
        :image-alt="aboutData.story.imageAlt"
        :fallback-src="aboutData.story.fallbackSrc"
      />

      <AboutFAQSection />
    </div>
  </main>
</template>

<script setup>
import { computed } from "vue";

const defaultAbout = {
  hero: {
    imageSrc: "/about/Group.jpg",
    alt: "سیسمونی جاوید",
    fallbackSrc: "/contact/Group.svg",
  },
  story: {
    title: "فروشگاه سیسمونی جاوید، انتخابی شایسته",
    paragraphs: [
      "مجموعه سیسمونی جاوید از سال ۱۳۹۵ فعالیت خود را با عشق و علاقه به دنیای کودکان آغاز کرد و با تلاش سه خواهر، از یک فروشگاه محلی به یکی از فروشگاه‌های محبوب سیسمونی در سطح کشور تبدیل شد.",
      "ما همواره در تلاشیم با ارائه‌ی محصولات باکیفیت و قیمت‌های مناسب، بهترین تجربه‌ی خرید را برای والدین عزیز و کوچولوی دوست‌داشتنی‌شان فراهم کنیم.",
      "سیسمونی جاوید مجموعه‌ای متنوع از لباس نوزاد، اسباب‌بازی، لوازم بهداشتی و سیسمونی را در اختیار شما قرار می‌دهد تا متناسب با سلیقه و نیاز خود، بهترین انتخاب را داشته باشید.",
    ],
    highlight:
      "ما به دنبال ایجاد تعادل میان کیفیت، ایمنی و زیبایی برای کوچولوی شما هستیم. محصولاتی که با مواد باکیفیت، دوخت دقیق و دغدغه‌ی سلامت پوست نوزاد طراحی شده‌اند؛ چون برای ما، آرامش و لبخند کودک شما، مهم‌ترین است.",
    imageSrc: "/about/model-pink.jpg",
    imageAlt: "سیسمونی جاوید",
    fallbackSrc: "/contact/Group.svg",
  },
};

const { data } = await useAsyncData("about-page", async () => {
  return null;
});

const aboutData = computed(() => data.value ?? defaultAbout);
</script>

<style scoped>
.jb-about-page {
  padding-bottom: 80px;
  background: linear-gradient(135deg, #fff8fb 0%, #fff0f5 50%, #ffeaf2 100%);
  background-attachment: fixed;
  min-height: 100vh;
}
</style>