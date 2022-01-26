<template>
  <div class="gallery-photo container-fluid text-center wood-bg" style="height: 1000px">
      <div class="gallery-wrapper wrapper-z-idx">
          <div class="gallery-title">
              <h1 class="font-title">Gallery Photos</h1>
          </div>
          
          <div class="gallery-grid container mx-auto mt-5">
              <div class="photos mx-auto">
                  <div v-for="i in 7" :key="i" :class="'photo-items img-'+i">
                    <i class="bx bx-expand"></i>
                  </div>
              </div>
          </div>
      </div>
  </div>
</template>

<script>
export default {
    methods: {
        showModal(image) {
            const modal = document.createElement('div');
            modal.innerHTML = `
                <div class="modal-img">
                    <img src="${image}" alt="Gallery Pengantin">
                    <button class="close-btn"></button>
                </div>
            `;
        }
    }
}
</script>

<style>
    .photos {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
        grid-template-rows: auto;
        grid-gap: 0.5rem;
        grid-template-areas: 'img-1 img-2 img-2'
                             'img-3 img-4 img-5'
                             'img-6 img-6 img-7';
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
    }

    .photos .photo-items::before {
        content: '';
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: rgba(0, 0, 0, 0.4);
        opacity: 0;
        transition: opacity .5s;
    }

    .photos .photo-items i {
        font-size: 1.5rem;
        position: relative;
        z-index: 100;
        padding: 0.5rem;
        border: 2px solid rgba(255, 255, 255, 0.6);
        color: #ebebeb;
        border-radius: .4rem;
        opacity: 0;
        transition: .5s;
    }

    .photos .photo-items i:hover {
        color: #fff;
        background: rgba(172, 171, 171, 0.377);
        border: 2px solid rgb(245, 245, 245);
    }

    .photos .photo-items:hover i,
    .photos .photo-items:hover::before {
        opacity: 1;
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
            min-width: 250px;
            min-height: 200px;
        }
    }

    @media screen and (min-width: 992px) {
        .photos .photo-items {
            min-width: 300px;
            min-height: 250px;
        }
    }
</style>