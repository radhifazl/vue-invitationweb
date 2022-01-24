<template>
  <div class="date-countdown container-fluid text-center wood-bg">
      <div class="countdown-content wrapper-z-idx">
        <div class="savedate m-auto">
            <button class="savedate-btn py-2 px-5 font-title">
                Save The Date
            </button>
        </div>
        <div class="countdown font-title" v-if="loaded">
            <div class="countdown-wrapper row d-flex justify-content-center">
                <div class="box-date col-lg-2 col-4 m-3" id="box-hari">
                    <h2>{{ displayDays }}</h2>
                    <h6>Hari</h6>
                </div>
                <div class="box-date col-lg-2 col-4 m-3" id="box-jam">
                    <h2>{{ displayHours }}</h2>
                    <h6>Jam</h6>
                </div>
                <div class="box-date col-lg-2 col-4 m-3" id="box-menit">
                    <h2>{{ displayMinutes }}</h2>
                    <h6>Menit</h6>
                </div>
                <div class="box-date col-lg-2 col-4 m-3" id="box-detik">
                    <h2>{{ displaySeconds }}</h2>
                    <h6>Detik</h6>
                </div>
            </div>
        </div>
      </div>
  </div>
</template>

<script>
export default {
    data: () => ({
        displayDays: 0,
        displayHours: 0,
        displayMinutes: 0,
        displaySeconds: 0,
        loaded: false, // Agar Ketika di Refresh, Countdown Tidak Berubah Jadi 00:00:00:00
        expired: false //Mengatur jika waktu countdown sudah habis
    }),
    computed: {
        _seconds: () => 1000,
        _minutes() {
            return this._seconds * 60
        },
        _hours() {
            return this._minutes * 60
        },
        _days() {
            return this._hours * 24
        },
    },
    mounted() {
        this.showRemaining();
    },
    methods: {
        formatNum: num => (num < 10 ? "0" + num : num), // Format Untuk Mendisplay Date
        showRemaining() {
            const timer = setInterval(() => {
                const date = new Date(); // Mengambil Date 
                const dateEnd = new Date(2022, 0, 12, 10, 10, 10, 10); //Atur Countdown
                const distance = dateEnd.getTime() - date.getTime(); //Mencari jarak detik antara tanggal yang ditentukan dan tanggal sekarang

                if(distance < 0) { // Jika waktu countdown sudah habis, clearInterval Timer
                    clearInterval(timer);
                    this.expired = true;
                    this.loaded = true;
                    return
                }

                const days = Math.floor((distance / this._days));
                const hours = Math.floor((distance % this._days) / this._hours);
                const minutes = Math.floor((distance % this._hours) / this._minutes);
                const seconds = Math.floor((distance % this._minutes) / this._seconds);

                this.displaySeconds = this.formatNum(seconds);
                this.displayMinutes = this.formatNum(minutes);
                this.displayHours = this.formatNum(hours);
                this.displayDays = this.formatNum(days);
                this.loaded = true;
            }, 1000);
        }
    }
}
</script>

<style>
    .date-countdown {
        height: 300px;
    }


    .savedate-btn {
        background-color: var(--tertiary-color);
        border: none;
        border-radius: 10px;
        outline: none;
        font-size: 1.5rem;
        transform: translateY(-5rem);
        cursor: pointer;
    }
    
    .countdown-content {
        width: 90%;
    }

    .countdown {
        margin-top: -2rem;
    }

    .box-date {
        background: var(--tertiary-color);
        padding: .5rem 3rem;
        border-radius: 11px;
    }

</style>