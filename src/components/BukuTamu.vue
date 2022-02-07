<template>
  <div class="bukutamu-section container-fluid wood-bg" style="height: 750px">
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
                autocomplete="off"
              />
            </div>

            <div class="box-pesan mb-4">
              <textarea
                name="pesan"
                class="form-control"
                id="pesan"
                placeholder="Berikan ucapan & doa" v-model="inpValues.messages"
                autocomplete="off" spellcheck="false"
                style="resize: none"
              ></textarea>
            </div>

            <div class="box-buttons">
              <div class="absence-box box-hadir">
                <input type="radio" name="absences" @change="testVal" id="hadir" v-model="inpValues.absences" value="Hadir" />
                <label for="hadir">Hadir</label>
              </div>

              <div class="absence-box box-akanhadir">
                <input type="radio" name="absences" @change="testVal" id="akanhadir" v-model="inpValues.absences" value="Akan Hadir" />
                <label for="akanhadir">Akan hadir</label>
              </div>

              <div class="absence-box box-tidakhadir">
                <input type="radio" name="absences" @change="testVal" id="tidakhadir" v-model="inpValues.absences" value="Tidak Hadir"/>
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
        nama: `<h1 class="slide-nama">Riska</h1><span class="absence hadir">Hadir</span>`,
        pesan:
          '<p class="slide-pesan">Selamat menempuh bahtera rumah tangga yang bahagia. Jangan berantem perkara pencet odol dari tengah sama dari ujung, ya!</p>',
      },
      {
        nama: '<h1 class="slide-nama">Riska</h1><span class="absence hadir">Hadir</span>',
        pesan:
          '<p class="slide-pesan">Selamat menempuh bahtera rumah tangga yang bahagia. Jangan berantem perkara pencet odol dari tengah sama dari ujung, ya!</p>',
      },
      {
        nama: '<h1 class="slide-nama">Erlangga</h1><span class="absence akan_hadir">Akan Hadir</span>',
        pesan:
          '<p class="slide-pesan">Selamat atas janji pernikahannya hari ini. Semoga dengan bersatunya kalian dalam ikatan perkawinan menjadi titik awal perjalanan hidup bersama yang lebih membahagiakan.</p>',
      },
      {
        nama: '<h1 class="slide-nama">Mutiara</h1><span class="absence tdk_hadir">Tidak Hadir</span>',
        pesan:
          '<p class="slide-pesan">Selamat menempuh hidup yang baru. Semoga pernikahannya menjadi awal yang membahagiakan.</p>',
      },
      {
        nama: '<h1 class="slide-nama">Erlangga</h1><span class="absence hadir">Hadir</span>',
        pesan:
          '<p class="slide-pesan">Selamat atas janji pernikahannya hari ini. Semoga dengan bersatunya kalian dalam ikatan perkawinan menjadi titik awal perjalanan hidup bersama yang lebih membahagiakan.</p>',
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
    testVal() {
      // const absenceInfo = this.$refs.absenceCbx
    },
    postSlide() {
      let name = this.inpValues.names;
      let msg = this.inpValues.messages;
      let absence = this.inpValues.absences;


      if(name && msg && absence) {
        this.slides.push({
          nama: `<h1 class="slide-nama">${name}</h1><span class="absence">${absence}</span>`,
          pesan: `<p class="slide-pesan">${msg}</p>`
        })

        const absenceInfo = document.querySelector('.absence');
        switch(this.inpValues.absences) {
          case "Hadir":
            console.log("User dipastikan hadir !");
            absenceInfo.classList.add('hadir');
            break;
          case "Akan Hadir":
            console.warn("User akan hadir :D");
            absenceInfo.classList.remove('hadir');
            absenceInfo.classList.add('akan_hadir');
            break;
          case "Tidak Hadir":
            console.error("User tidak akan hadir :(");
            absenceInfo.classList.remove('akan_hadir');
            absenceInfo.classList.add('tdk_hadir');
            break;
          default:
            console.log("Gak tau");
        }

        this.successAlert();
        this.$refs.absenceForm.reset();
      } else {
        this.warnAlert();
        return false;
      } 
    },

    successAlert() { 
      Swal.fire({
        icon: 'success',
        title: 'Card ditambahkan!',
        text: 'Kartu ucapan berhasil ditambahkan ke dalam slide!',
        showCloseButton: true,
      })
    },

    warnAlert() {
      Swal.fire({
        icon: 'error',
        title: 'Mohon isi semua datanya!',
        text: 'Wajib buat ngisi semua fieldnya, terima kasih!',
        showCloseButton: true,
      })
    },
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
  background: #AE6745;
  overflow-y: auto;
  overflow-x: hidden;
  border-radius: 10px;
  position: relative;
}

.vueperslide__content-wrapper:not(.vueperslide__content-wrapper--outside-top):not(.vueperslide__content-wrapper--outside-bottom) {
  padding: 1rem;
}

.vueperslides--fixed-height { height: 200px; }
.vueperslide__title {
  margin-bottom: 1rem;
}

/* === Variables for slide === */
:root {
  --content-color: #292B3A;
}

.slide-nama {
  font-size: 18px;
  font-family: var(--third-font);
  color: var(--content-color);
}

.slide-pesan {
  font-size: 14px;
  font-family: var(--third-font);
  color: var(--content-color);
  font-weight: 500;
}

.absence {
  position: absolute;
  right: 5%;
  top: 8%;
  font-size: 14px;
  border-radius: 5px;
  justify-content: center;
  align-items: center;
  font-family: var(--third-font);
  font-weight: 400;
}

.absence.hadir, .absence.akan_hadir {
  background: #444444;
  width: 75px;
  height: 27px;
  display: flex;
}

.absence.akan_hadir {
  padding: 0 0.2rem;
  width: 78px;
}

.absence.tdk_hadir {
  background: #BB1E1E;
  padding: 0 0.4rem;
  width: 85px;
}

</style>
