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
          <form>
            <div class="box-nama mb-3">
              <input
                type="text"
                class="form-control"
                name="nama"
                id="nama"
                placeholder="Nama anda"
                required
              />
            </div>

            <div class="box-pesan mb-4">
              <textarea
                name="pesan"
                class="form-control"
                id="pesan"
                placeholder="Berikan ucapan & doa"
                required
                style="resize: none"
              ></textarea>
            </div>

            <div
              class="box-buttons d-flex justify-content-between align-items-center"
            >
              <div class="absence-box box-hadir">
                <input type="radio" name="absence" id="hadir" required />
                <label for="hadir">Hadir</label>
              </div>

              <div class="absence-box box-akanhadir">
                <input type="radio" name="absence" id="akanhadir" required />
                <label for="akanhadir">Akan hadir</label>
              </div>

              <div class="absence-box box-tidakhadir">
                <input type="radio" name="absence" id="tidakhadir" required />
                <label for="tidakhadir">Tidak hadir</label>
              </div>

              <button type="submit" name="submit" class="submit-btn">
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
          fixed-height="200px"
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
            :key="slide.id"
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

export default {
  components: {
    VueperSlides,
    VueperSlide,
  },
  data: () => ({
    slides: [
      {
        id: 1,
        nama: "Riska",
        pesan:
          "Selamat menempuh bahtera rumah tangga yang bahagia. Jangan berantem perkara pencet odol dari tengah sama dari ujung, ya!",
      },
      {
        id: 2,
        nama: "Riska",
        pesan:
          "Selamat menempuh bahtera rumah tangga yang bahagia. Jangan berantem perkara pencet odol dari tengah sama dari ujung, ya!",
      },
      {
        id: 3,
        nama: "Erlangga",
        pesan:
          "Selamat atas janji pernikahannya hari ini. Semoga dengan bersatunya kalian dalam ikatan perkawinan menjadi titik awal perjalanan hidup bersama yang lebih membahagiakan.",
      },
      {
        id: 4,
        nama: "Mutiara",
        pesan:
          "Selamat menempuh hidup yang baru. Semoga pernikahannya menjadi awal yang membahagiakan.",
      },
      {
        id: 5,
        nama: "Erlangga",
        pesan:
          "Selamat atas janji pernikahannya hari ini. Semoga dengan bersatunya kalian dalam ikatan perkawinan menjadi titik awal perjalanan hidup bersama yang lebih membahagiakan.",
      },
    ],
    breakpoints: {
        600: {
            visibleSlides: 3,
        },
    },
  }),
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
}

.form-wrapper {
  width: 100%;
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
  padding: 0.1rem 1.5rem;
}

.slides {
  background: var(--secondary-color);
}

.vueperslide__content-wrapper:not(.vueperslide__content-wrapper--outside-top):not(.vueperslide__content-wrapper--outside-bottom) {
  padding: 1rem;
}
</style>
