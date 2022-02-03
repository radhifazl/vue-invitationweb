<template>
  <div class="bukutamu-section container-fluid wood-bg" style="height: 1000px">
    <div class="bukutamu-wrapper container-fluid wrapper-z-idx">
      <div class="bukutamu-title text-center">
        <h1 class="font-title">Buku Tamu</h1>
        <p class="font-sub">
          Berikan Doa / Ucapan Terbaik Anda Kepada Kedua Mempelai
        </p>
      </div>

      <div class="buku-tamu mx-auto mt-5 p-4">
        <div class="form-wrapper">
          <form @submit.prevent="postSlide" method="post" ref="absenceForm">
            <div class="box-nama mb-3">
              <input
                type="text"
                class="form-control"
                name="nama"
                id="nama"
                placeholder="Nama anda" v-model="inpValues.names"
                required
              />
            </div>

            <div class="box-pesan mb-4">
              <textarea
                name="pesan"
                class="form-control"
                id="pesan"
                placeholder="Berikan ucapan & doa" v-model="inpValues.messages"
                required
                style="resize: none"
              ></textarea>
            </div>

            <div class="box-buttons">
              <div class="absence-box box-hadir">
                <input type="radio" name="absence" id="hadir" v-model="inpValues.absences" value="Hadir" required />
                <label for="hadir">Hadir</label>
              </div>

              <div class="absence-box box-akanhadir">
                <input type="radio" name="absence" id="akanhadir" v-model="inpValues.absences" value="Akan Hadir" required />
                <label for="akanhadir">Akan hadir</label>
              </div>

              <div class="absence-box box-tidakhadir">
                <input type="radio" name="absence" id="tidakhadir" v-model="inpValues.absences" value="Tidak Hadir" required />
                <label for="tidakhadir">Tidak hadir</label>
              </div>

              <button type="submit" name="submit" class="submit-btn" @click="postToSlide">
                Post
              </button>
            </div>
          </form>
        </div>
      </div>

      <div class="slide-ucapan mt-5">
        <vueper-slides
          autoplay
          :arrows="false"
          :fixed-height="true"
          class="no-shadow slides-wrapper"
          slide-multiple
          :visible-slides="5"
          :gap="1"
          :slide-ratio="1 / 3"
          :dragging-distance="70"
          :breakpoints="breakpoints"
        >
          <vueper-slide
            class="slides"
            v-for="slide in slides"
            :key="slide.nama"
            :title="slide.nama"
            :content="slide.pesan"
          />
        </vueper-slides>
      </div>
    </div>
  </div>
</template>

<script>
import { VueperSlides, VueperSlide } from "vueperslides";
import "vueperslides/dist/vueperslides.css";

import Swal from 'sweetalert2'

export default {
  components: {
    VueperSlides,
    VueperSlide,
  },
  data: () => ({
    slides: [
      {
        nama: "Riska",
        pesan:
          "Selamat menempuh bahtera rumah tangga yang bahagia. Jangan berantem perkara pencet odol dari tengah sama dari ujung, ya!",
      },
      {
        nama: "Riska",
        pesan:
          "Selamat menempuh bahtera rumah tangga yang bahagia. Jangan berantem perkara pencet odol dari tengah sama dari ujung, ya!",
      },
      {
        nama: "Erlangga",
        pesan:
          "Selamat atas janji pernikahannya hari ini. Semoga dengan bersatunya kalian dalam ikatan perkawinan menjadi titik awal perjalanan hidup bersama yang lebih membahagiakan.",
      },
      {
        nama: "Mutiara",
        pesan:
          "Selamat menempuh hidup yang baru. Semoga pernikahannya menjadi awal yang membahagiakan.",
      },
      {
        nama: "Erlangga",
        pesan:
          "Selamat atas janji pernikahannya hari ini. Semoga dengan bersatunya kalian dalam ikatan perkawinan menjadi titik awal perjalanan hidup bersama yang lebih membahagiakan.",
      },
    ],
    breakpoints: {
        600: {
            visibleSlides: 1,
            bulletsOutside: true
        },
    },
    inpValues: {
      names: null,
      messages: null,
      absences: false
    }
  }),
  methods: {
    postSlide() {
      let name = this.inpValues.names;
      let msg = this.inpValues.messages;
      this.slides.push({
        nama: name,
        pesan: msg
      })

      this.successAlert();

      this.$refs.absenceForm.reset();
    },

    successAlert() { 
      Swal.fire({
        icon: 'success',
        title: 'Card ditambahkan!',
        text: 'Kartu ucapan berhasil ditambahkan ke dalam slide!',
        showCloseButton: true,
      })
    }
  }
};
</script>

<style>
.buku-tamu {
  background: #c57752;
  width: 500px;
  height: 250px;
  display: grid;
  place-items: center;
  border-radius: 9px;
}

@media screen and (max-width: 768px) {
    .buku-tamu {
        width: 90%;
    }

    .box-buttons {
      display: grid;
      grid-template-columns: 1fr 1fr 1fr;
      grid-template-rows: auto;
      grid-gap: 1rem;
      grid-template-areas: 
        "btn-1 btn-2 btn-3"
        "btn-4 btn-4 btn-4"
      ;
    }
    .box-hadir {
      grid-area: btn-1;
    }

    .box-akanhadir {
      grid-area: btn-2;
      margin-left: -1.3rem;
    }

    .box-tidakhadir {
      grid-area: btn-3;
      margin-left: -1rem;
    }

    .submit-btn {
      grid-area: btn-4;
    }
}

.form-wrapper {
  width: 100%;
}

@media screen and (min-width: 768px) {
  .box-buttons {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
}

.absence-box {
  display: flex;
  align-items: center;
  gap: 8px;
}

.absence-box {
  width: 15px;
  height: 15px;
  cursor: pointer;
  position: relative;
  visibility: hidden;
}

.absence-box label {
  visibility: visible;
  font-size: 0.838rem;
  white-space: nowrap;
}

.absence-box input::before,
.absence-box input::after {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border-radius: 50%;
}

.absence-box input::before {
  background: white;
  visibility: visible;
}

.absence-box input::after {
  background: var(--secondary-color);
  border: 2px solid white;
  visibility: visible;
  transform: scale(0);
  transition: 0.3s ease;
}

.absence-box input:checked::after {
  transform: scale(1);
}

.submit-btn {
  border: none;
  outline: none;
  background: var(--secondary-color);
  padding: 0.3rem 2rem;
  transition: 0.3s ease;
}

.submit-btn:hover {
  background: #be571b;
  border-radius: 3px;
}

.slides {
  background: var(--secondary-color);
  overflow-y: auto;
  overflow-x: hidden;
}

.vueperslide__content-wrapper:not(.vueperslide__content-wrapper--outside-top):not(.vueperslide__content-wrapper--outside-bottom) {
  padding: 1rem;
}

.vueperslides--fixed-height { height: 200px; }
.vueperslide__title {
  margin-bottom: 1rem;
}
</style>
