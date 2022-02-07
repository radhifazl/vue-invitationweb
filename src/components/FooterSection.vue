<template>
  <div class="footer-angpao container-fluid text-center wood-bg">
      <div class="footer-wrapper wrapper-z-idx">
          <h1 class="font-title">Angpao Digital</h1>
          <p class="font-sub mt-3">
            Dan jika memberi adalah ungkapan tanda kasih Anda, 
            Anda dapat memberi kado secara cashless dengan mengirim amplop digital 
            secara transfer pada akun di bawah ini :
          </p>

          <div class="payment-barcode-container container mt-5">
            <div class="payment bca">
              <h5 class="payment-num">
                BCA - 4980131187
              </h5>

              <img src="../assets/images/barcodes/bcabarcodes.svg" alt="BCA">
            </div>
            
            <div class="payment ovo">
              <h5 class="payment-num">
                OVO - 087780933640
              </h5>

              <img src="../assets/images/barcodes/ovobarcodes.svg" alt="OVO">
            </div>
          </div>

          <div class="footer-couple-name m-5">
            <h1 class="font-title">Qeza & Novan</h1>
          </div>

          <footer class="footer">
            <div class="social-media d-flex justify-content-center align-items-center gap-3">
              <a href="">
                <div class="sosmed instagram">
                  <i class='bx bxl-instagram'></i>
                </div>
              </a>

              <a href="">
                <div class="sosmed whatsapp">
                  <i class='bx bxl-whatsapp'></i>
                </div>
              </a>
            </div>

            <div class="footer-text mt-4">
              <p>
                Copyright 2021 © All rights Reserved. Design by yaninvitation
              </p>
            </div>
          </footer>
      </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>
  .footer-angpao {
     height: 1000px
  }
  @media screen and (min-width: 768px) {
    .footer-angpao {
      height: 700px;
    }
  }
  .footer-wrapper {
    width: 90%;
  }
  .payment-barcode-container {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    row-gap: 2rem;
  }

  .payment {
    width: 100%;
    padding: 1.5rem 0;
    background: #F8F8F8;
    box-shadow: 0px 1px 10px 4px rgba(0, 0, 0, 0.25);
    border-radius: 10px;
  }

  .payment-num {
    color: #0B0D11;
    font-family: var(--cabin);
    font-weight: 400;
  }

  @media screen and (min-width: 768px) {
    .footer-wrapper {
      width: 70%;
    }

    .payment-barcode-container {
      flex-direction: row;
      row-gap: 0;
      gap: 2rem;
    }

    .payment {
      width: 300px;
    }
  }

  .social-media a {
    background: #FFFFFF;
    width: 25px;
    height: 35px;
    border-radius: 50%;
    padding: 1.5rem;
    display: flex;
    justify-content: center;
    align-items: center;
    transition: all 0.3s ease;
  }

  .social-media a:hover {
    background: #F8F8F8;
    transform: translateY(-1rem);
  }

  .sosmed i {
    color: #3E3F3F;
    font-size: 1.5rem;
  }

  .footer-text p {
    font-family: var(--footer-font);
  }
</style>