<template>
  <div class="event container-fluid text-center wood-bg">
      <img src="../assets/images/pinkflower1.svg" alt="Pink Flower" id="topleft-flower">
      <img src="../assets/images/pinkflower2.svg" alt="Pink Flower" id="topright-flower">
      <img src="../assets/images/midflower.svg" alt="Flower" id="mid-flower">
      <div class="event-wrapper pt-5 mt-5 wrapper-z-idx">
        <div class="event-section-title mb-5">
            <h1 class="font-title mb-3">Save The Date</h1>
            <h4 class="font-sub">Yang insyaallah akan dilaksanakan pada</h4>
        </div>

        <div class="event-card-wrapper container d-flex justify-content-around align-items-center flex-lg-row flex-column my-5">
            <div class="akad-nikah event-card text-center mx-lg-5 py-5">
                <h2 class="font-title card-title">Akad Nikah</h2>

                <div class="logo-tanggal">
                    <img src="../assets/images/LogoTanggal.svg" alt="Tanggal 9">
                </div>

                <div class="card-jadwal">
                    <h2 class="font-title jadwal-hari mx-auto">Minggu</h2>
                    <h5 class="font-title">Januari 2022</h5>
                </div>

                <div class="card-jam my-3 mx-auto p-2">
                    <h5 class="font-title">09.00 WIB s/d selesai</h5>
                </div>

                <div class="card-alamat">
                    <h6 class="font-sub">
                        Kediaman Mempelai Wanita Kp. Cibogo RT 04/06, Desa Tugu Jaya, Kec. Cigombong, Kab, Bogor
                    </h6>
                </div>
            </div>

            <div class="resepsi event-card text-center mx-lg-5 py-5">
                <h2 class="font-title card-title">Resepsi</h2>

                <div class="logo-tanggal">
                    <img src="../assets/images/LogoTanggal.svg" alt="Tanggal 9">
                </div>

                <div class="card-jadwal">
                    <h2 class="font-title jadwal-hari mx-auto">Minggu</h2>
                    <h5 class="font-title">Januari 2022</h5>
                </div>

                <div class="card-jam my-3 mx-auto p-2">
                    <h5 class="font-title">09.00 WIB s/d selesai</h5>
                </div>

                <div class="card-alamat">
                    <h6 class="font-sub">
                        Kediaman Mempelai Wanita Kp. Cibogo RT 04/06, Desa Tugu Jaya, Kec. Cigombong, Kab, Bogor
                    </h6>
                </div>
            </div>
        </div>
        <a class="font-sub gmap" href="#">
            <div class="map-button m-auto">
                <i class='bx-fw bx bxs-map'></i> Google Maps
            </div>
        </a>
        <div class="salam-keluarga text-center mt-5">
            <h5 class="font-sub">Kami yang berbahagia : <br>
                Keluarga Besar Bpk. Suparman (Icit) & Ibu Sundarti <br>
                Keluarga Besar Bpk. Purohman &
                Ibu Nining Winingsih (Almh)
            </h5>
        </div>
      </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>
  .event {
    min-height: 1900px;
    position: relative;
    margin-top: -5rem;
  }

  #topleft-flower, #topright-flower, #mid-flower {
      position: absolute;
      z-index: 1000;
  }

  #topleft-flower, #topright-flower {
      top: 0;
      width: 200px;
  }

  #topleft-flower {
      left: 0;
  }

  #topright-flower {
      right: 0;
  }

  #mid-flower {
      width: 300px;
      bottom: 0;
      left: 50%;
      transform: translateX(-50%);
  }

  @media screen and (min-width: 992px) {
      .event {
          min-height: 1400px;
      }

      #topleft-flower, #topright-flower {
          width: 400px;
      }

      #topleft-flower {
          left: 1%;
      }

      #topright-flower {
          right: 1%;
      }

      #mid-flower {
          width: 500px;
      }
  }

  .event-section-title h1 {
    color: var(--first-fc);
  }

  .event-card {
    background: var(--white-fc);
    height: 100%;
    border: 5px solid var(--second-fc);
    border-radius: 15px;
  }

  .card-title {
      color: var(--second-fc);
      font-size: 2.5rem;
  }

  .event-card .card-jadwal h2, h5 {
      color: var(--second-fc);
  }

  .card-jam {
      background: url("../assets/images/tanggalbg.png") no-repeat;
      background-size: cover;
      width: 80%;
  }

  .jadwal-hari {
      position: relative;
      width: 150px;
  }

  .jadwal-hari::before, .jadwal-hari::after {
      content: '';
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      width: 10px;
      height: 10px;
      background: var(--second-fc);
      border-radius: 50%;
  }

  .jadwal-hari::before {
      left: 0;
  }

  .jadwal-hari::after {
      right: 0;
  }

  .card-jam h5 {
      transform: translateY(.5rem);
      color: var(--white-fc);
  }

  .card-alamat h6 {
      color: var(--black-fc);
  }

  .gmap {
      text-decoration: none;
  }

  .map-button {
      color: var(--white-fc);
      background: #B3541E;
      box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
      border-radius: 5px;
      width: 200px;
      padding: 0.5rem;
      transition: 0.3s ease;
      font-size: 1.2rem;
  }

  .map-button:hover {
      box-shadow: 3px 8px 8px rgba(0, 0, 0, 0.445);
      transform: translateY(-0.3rem);
  }

  .salam-keluarga h5 {
      color: var(--white-fc);
  }
</style>