<template>
  <div class="brides-name container-fluid text-center wood-bg">
    <img src="../assets/images/pinkflo3.svg" alt="Pink Flower" class="pinkflo" id="pf-3">
    <img src="../assets/images/pinkflo4.svg" alt="Pink Flower" class="pinkflo" id="pf-4">
      <div class="brides-name-content wrapper-z-idx">
        <div class="invitation-text">
            <h1 class="font-title">Assalamualaikum Warahmatullahi Wabarakatuh</h1>
            <p class="font-sub">
                Tanpa mengurangi rasa hormat, kami bermaksud mengundang <br>
                Bapak/Ibu/Saudara/i untuk menghadiri acara pernikahan kami
            </p>
        </div>

        <div class="brides container mt-5 pt-3">
          <div class="women-bride">
            <div class="women-pic bride-pic mb-3">
              <img src="../assets/images/wanita.png" alt="Foto Wanita">
            </div>
            <div class="women-name name">
              <h1 class="font-title">Haqeza Kaldha</h1>
              <h4 class="font-sub">Putri dari bpk. Suparman (Icit) & Ibu Sundarti</h4>
            </div>
          </div>

          <div class="separator m-5">
            <h1 class="font-title">&</h1>
          </div>

          <div class="men-bride">
            <div class="men-pic bride-pic mb-3">
              <img src="../assets/images/pria.png" alt="Foto Pria">
            </div>
            <div class="men-name name">
              <h1 class="font-title">Novandiansyah</h1>
              <h4 class="font-sub">Putra dari bpk.Purohman & Ibu Nining winingsih (alm)</h4>
            </div>
          </div>
        </div>
      </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>
  .brides-name {
    min-height: 1400px;
    position: relative;
  }

  .brides-name .pinkflo {
    position: absolute;
    z-index: 100;
    bottom: -2%;
    max-width: 200px;
  }

  .brides-name #pf-3 {
    left: 0;
  }

  .brides-name #pf-4 {
    right: 0;
  }

    .women-bride, .men-bride {
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
    }

  .bride-pic {
    width: 200px;
    border: 5px solid #ffffff;
    border-radius: 50%;
  }

  .bride-pic img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  .separator h1 {
    font-size: 4rem;
  }

  .name h1 {
    font-size: 2rem;
  }

  .name h4 {
    font-size: 1rem;
  }

  @media screen and (min-width: 992px) {
    .brides-name {
      min-height: 1300px;
    }

    .brides-name .pinkflo {
      max-width: 350px;
      bottom: -5%;
    }

    .name h1 {
      font-size: 3rem;
    }
    .separator h1 {
      font-size: 5rem;
    }
    .name h4 {
      font-size: 1.5rem;
    }
  }
</style>