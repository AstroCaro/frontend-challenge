<template>
  <footer class="footer">
    <div class="footer-payments">
      <div class="container">
        <ul>
          <li v-for="(item, id) in paymentMethods" :key="name">
            <img :style="{ width: item.width }" :src="item.src" alt="Payment method" />
          </li>
          <li><span class="extra">and 50+ more</span></li>
        </ul>
      </div>
    </div>
    <div class="footer-site-map">
      <div class="container">
        <div class="footer-social">
          <ul>
            <li v-for="(item, id) in socialMedia" :key="name" class="icon-social">
              <img :style="{ width: item.width }" :src="item.src" alt="Social Media" />
            </li>
          </ul>
        </div>
        <div class="footer-list">
          <div class="logo">
            <img src="../assets/logos/chicks-logo-large.svg" alt="Chicks Gold Logo" />
            <p>support@chicksgold.com</p>
          </div>
          <div class="footer-navegation" v-for="(section, id) in sections" :key="id">
            <h6>{{ section.title }}</h6>
            <ul>
              <li v-for="sub in section.submenu" :key="sub">{{ sub }}</li>
            </ul>
          </div>
          <div>
            <div class="footer-reviews">
              <img
                src="../assets/icons/stars-5.svg"
                alt="trustpilot"
                style="width: 100px"
              />
              <p>Trustpilot Reviews</p>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="footer-copyright">
      &copy; 2017 - 2020 Chicksgold.com. All Rights Reserved.
    </div>
  </footer>
</template>
<script setup>
import { ref } from 'vue';

const paymentMethods = ref([
  {
    name: 'visa',
    src: 'src/assets/icons/payment-methods/visa.svg',
    width: '80px',
  },
  {
    name: 'mastercard',
    src: 'src/assets/icons/payment-methods/master.svg',
    width: '70px',
  },
  {
    name: 'american',
    src: 'src/assets/icons/payment-methods/american.png',
    width: '90px',
  },
  {
    name: 'skrill',
    src: 'src/assets/icons/payment-methods/skrill.svg',
    width: '90px',
  },
  {
    name: 'currency',
    src: 'src/assets/icons/payment-methods/currency.svg',
    width: '150px',
  },
]);

const socialMedia = ref([
  {
    name: 'facebook',
    src: 'src/assets/icons/social-media/facebook_white.svg',
    width: '12px',
  },
  {
    name: 'facebook',
    src: 'src/assets/icons/social-media/instagram_white.svg',
    width: '20px',
  },
  {
    name: 'facebook',
    src: 'src/assets/icons/social-media/twitter_white.svg',
    width: '20px',
  },
  {
    name: 'facebook',
    src: 'src/assets/icons/social-media/discord_white.svg',
    width: '20px',
  },
]);

const sections = ref([
  {
    title: 'Chicks Gold',
    submenu: ['Games', 'About Us', 'Blog', 'Sitemap'],
  },
  {
    title: 'Support',
    submenu: ['Contact Us', 'FAQ'],
  },
  {
    title: 'Legal',
    submenu: ['Privacy Policy', 'Terms of Service', 'Copyright Policy'],
  },
]);
</script>
<style scoped>
.footer {
  display: flex;
  flex-direction: column;
}
.footer-payments {
  background-color: #303141;
  padding: 1.8rem 0;
}
.footer-payments ul {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 1.5rem;
  list-style-type: none;
  margin: 0;
  padding: 0;
}
.footer-payments ul li {
  display: flex;
  justify-content: center;
  align-items: center;
}
.footer-site-map {
  background-color: var(--color-background);
}
.footer-social {
  border-bottom: 1px solid #4c6085;
}
.footer-social ul {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 20px;
  list-style-type: none;
  flex-wrap: wrap;
  margin: 2rem 0 1rem;
  padding: 0;
}

.footer-social ul li {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 10px;
  width: 40px;
  height: 40px;
  border: 1px solid white;
  border-radius: 40px;
}
.footer-list {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 2rem 0;
  gap: 0.3rem;
}
.footer-list > div {
  width: 100%;
}
.footer-reviews {
  display: flex;
  gap: 12px;
  font-size: 14px;
  justify-content: center;
}
.logo {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-bottom: 12px;
  gap: 20px;
  font-size: 14px;
}
.logo img {
  width: 40%;
}
.footer-navegation {
  width: 100%;
  text-align: center;
  margin-bottom: 16px;
}
.footer-navegation h6 {
  margin: 0;
  font-size: 18px;
  margin-bottom: 10px;
}
.footer-navegation ul {
  list-style: none;
  padding: 0;
  display: flex;
  flex-direction: column;
  gap: 8px;
}
.footer-navegation ul li {
  font-size: 14px;
  color: var(--color-text);
  opacity: 0.7;
  font-weight: 200;
}
.container {
  margin-left: auto;
  margin-right: auto;
  max-width: 640px;
}
.extra {
  display: none;
}
.footer-copyright {
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 20px 0;
  font-size: 14px;
}
@media (min-width: 768px) {
  .footer-social ul {
    justify-content: flex-start;
  }
  .footer-payments ul {
    justify-content: flex-start;
  }
  .logo {
    align-items: flex-start;
  }
  .logo img {
    width: 70%;
  }
  .footer-list {
    flex-direction: row;
    align-items: flex-start;
  }
  .footer-list > div {
    width: 25%;
  }
  .footer-navegation {
    width: 16.6667% !important;
    text-align: left;
  }
  .extra {
    display: none;
  }
  .container {
    max-width: 768px;
  }
}

@media (min-width: 1024px) {
  .extra {
    display: block;
  }
  .container {
    max-width: 1024px;
  }
}

@media (max-width: 1024px) {
  .footer-payments ul {
    flex-wrap: wrap;
  }
}
</style>
