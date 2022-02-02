<template>
  <div class="gallery-photo container-fluid text-center wood-bg">
    <div class="gallery-wrapper wrapper-z-idx">
      <div class="gallery-title">
        <h1 class="font-title">Gallery Photos</h1>
      </div>

      <div class="gallery-grid container mx-auto mt-5">
        <div class="photos mx-auto">
          <div v-for="i in 7" :key="i" :class="'photo-items img-' + i"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style>
.gallery-photo {
    height: 500px;
}
@media screen and (min-width: 768px) {
    .gallery-photo {
        height: 900px;
    }
}
.modal-btn {
  width: 10rem;
  height: 2rem;
  font-family: var(--first-font);
  font-size: 1.2rem;
  background: #b3541e;
  border: none;
  border-radius: 15px;
  outline: none;
  transition: all 0.5s ease;
}

.modal-btn:hover {
  background: #c95b1b;
}

.photos {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-template-rows: auto;
  grid-gap: 0.5rem;
  grid-template-areas:
    "img-1 img-2 img-2"
    "img-3 img-4 img-5"
    "img-6 img-6 img-7";
}

.photos .photo-items {
  min-width: 100px;
  height: 120px;
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  border-radius: 1rem;
  transition: all 0.35s ease;
}

.img-1 {
  grid-area: img-1;
  background: url("../assets/images/gallery/img-1.png");
}

.img-2 {
  grid-area: img-2;
  background: url("../assets/images/gallery/img-2.png");
}

.img-3 {
  grid-area: img-3;
  background: url("../assets/images/gallery/img-3.png");
}

.img-4 {
  grid-area: img-4;
  background: url("../assets/images/gallery/img-4.png");
}

.img-5 {
  grid-area: img-5;
  background: url("../assets/images/gallery/img-5.png");
}

.img-6 {
  grid-area: img-6;
  background: url("../assets/images/gallery/img-6.png");
}

.img-7 {
  grid-area: img-7;
  background: url("../assets/images/gallery/img-7.png");
}

@media screen and (min-width: 768px) {
  .photos .photo-items {
    min-width: 230px;
    min-height: 180px;
  }
}

@media screen and (min-width: 992px) {
  .photos .photo-items {
    min-width: 300px;
    min-height: 250px;
  }
}
</style>
