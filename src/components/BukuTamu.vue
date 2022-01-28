<template>
  <div class="bukutamu-section container-fluid wood-bg" style="height: 1000px">
      <div class="bukutamu-wrapper wrapper-z-idx">
        <div class="bukutamu-title text-center">
            <h1 class="font-title">Buku Tamu</h1>
            <p class="font-sub">Berikan Doa / Ucapan Terbaik Anda Kepada Kedua Mempelai</p>
        </div>

        <div class="buku-tamu mt-5 p-4">
            <form>
                <div class="box-nama mb-3">
                    <input 
                        type="text" class="form-control"
                        name="nama" 
                        id="nama" 
                        placeholder="Nama anda" 
                        required
                    >
                </div>

                <div class="box-pesan mb-3">
                    <textarea 
                        name="pesan" class="form-control"
                        id="pesan" 
                        placeholder="Berikan ucapan & doa" 
                        required style="resize: none;"></textarea>
                </div>

                <div class="box-buttons d-flex justify-content-around align-items-center">
                    <div class="absence-box box-hadir">
                        <input type="checkbox" name="hadir" id="hadir" @click="onlyOne(this)">
                        <label for="hadir">Hadir</label>
                    </div>

                    <div class="absence-box box-akanhadir">
                        <input type="checkbox" name="akanhadir" id="akanhadir" @click="onlyOne(this)">
                        <label for="akanhadir">Akan hadir</label>
                    </div>

                    <div class="absence-box box-tidakhadir">
                        <input type="checkbox" name="tidakhadir" id="tidakhadir" @click="onlyOne(this)">
                        <label for="tidakhadir">Tidak hadir</label>
                    </div>

                    <button type="submit" name="submit" class="submit-btn">Post</button>
                </div>
            </form>
        </div>
      </div>
  </div>
</template>

<script>
export default {
    methods: {
        onlyOne(checkbox) {
            var checkboxes = document.getElementsByName('check')
            checkboxes.forEach((item) => {
                if (item !== checkbox) item.checked = false
            })
        }
    }
}
</script>

<style>
    .buku-tamu {
        background: #C57752;
        border-radius: 9px;
    }

    .absence-box {
        display: flex;
        align-items: center;
        gap: 5px;
    }

    .radio-box input {
        background-color: #C57752;
    }
</style>