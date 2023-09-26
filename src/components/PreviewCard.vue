<template>
  <div class="main-card">
    <div class="card-image">
      <img
        class="img-background"
        :src="isMobile?imgUrl.mobile:imgUrl.desktop"
        height="400"
      />
    </div>
    <div class="card-info-container">
      <div class="card-info">
        <span class="card-info__title">PERFUME</span>
        <span class="card-info__subtitle">Gabrielle Essence Eau De Parfum</span>
        <p class="card-info__description">
          A floral, solar and voluptuous interpretation composed by Olivier
          Polge, Perfumer-Creator for the House of CHANEL.
        </p>
        <div class="card-info__price">
          <span class="card-info__price__discount">$149.99</span
          ><span class="card-info__price__original">$169.99</span>
        </div>
        <div class="card-info__button">
          <img
            src="../assets/images/icon-cart.svg"
            height="14px"
            width="16px"
          />
          <span class="card-info__button__text">Add to cart</span>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      isMobile: false,
      imgUrl:{
        desktop: require("@/assets/images/image-product-desktop.jpg"),
        mobile: require("@/assets/images/image-product-mobile.jpg"),
      }
    };
  },
  mounted() {
    window.addEventListener("resize", this.handleResize);
    let width = window.innerWidth;
    if (width <= 768) {
      this.isMobile = true;
    } else {
      this.isMobile = false;
    }
  },
  methods: {
    handleResize() {
      let width = window.innerWidth;
      if (width <= 768) {
        this.isMobile = true;
      } else {
        this.isMobile = false;
      }
    }
  },
};
</script>
<style>
@import url("https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,700&display=swap");
.main-card {
  width: auto;
  height: 400px;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  text-align: start;
}
.img-background {
  border-radius: 1em;
  border-top-right-radius: 0px;
  border-bottom-right-radius: 0px;
  width: 100%;
}
@media (max-width: 768px) {
  .img-background {
    border-radius: 1em!important;
    border-bottom-right-radius: 0px !important;
    border-bottom-left-radius: 0px !important;
    width: 300px;
    height: 100%;
    background-position: bottom;
  }
}
.card-info-container {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: flex-start;
  width: auto;
  height: 400px;
}
.card-info {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: flex-start;
  padding: 1em 2em;
  width: 100%;
  max-width: 220px;
  height: 100%;
  background: white;
  border-radius: 1em;
  border-top-left-radius: 0px;
  border-bottom-left-radius: 0px;
  row-gap: 1em;
  word-wrap: break-word;
}
span,
p {
  font-family: "Montserrat", sans-serif;
}
.card-info__subtitle {
  color: #1c232b;
  font-size: 32px;
  font-family: Fraunces;
  font-weight: 700;
  line-height: 32px;
  word-wrap: break-word;
}
.card-info__title {
  color: #6c7289;
  font-size: 12px;
  font-family: Montserrat;
  font-weight: 500;
  letter-spacing: 5px;
  word-wrap: break-word;
}
.card-info__description {
  color: #6c7289;
  font-size: 14px;
  font-family: Montserrat;
  font-weight: 500;
  line-height: 23px;
  word-wrap: break-word;
}
.card-info__price {
  display: flex;
  align-items: center;
}
.card-info__price__discount {
  color: #3d8168;
  font-size: 32px;
  font-family: Fraunces;
  font-weight: 700;
  line-height: 32px;
  word-wrap: break-word;
}
.card-info__price__original {
  color: #6c7289;
  margin-left: 1em;
  font-size: 13px;
  font-family: Montserrat;
  font-weight: 500;
  text-decoration: line-through;
  line-height: 23px;
  word-wrap: break-word;
}
.card-info__button {
  margin: 0 auto;
  width: 75%;
  background: #3d8168;
  padding: 1em 3em;
  border-radius: 0.5em;
  color: white;
  font-size: 14px;
  font-family: Montserrat;
  font-weight: 700;
  display: flex;
  flex-direction: row;
  justify-content: center;
}
.card-info__button:hover {
  cursor: pointer;
  background: #1a4032;
}
.card-info__button__text {
  margin-left: 1em;
}
@media (max-width: 768px) {
  .main-card {
    flex-direction: column !important;
    display: flex;
    height: 100%;
    overflow-y: auto !important;
  }
}
</style>