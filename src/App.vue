<template>
  <div id="app">
    <!-- <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/> -->

    <!-- <head> -->
    <div class="sections-menu">
      <div class="right-div">
        <span class="menu-point" v-bind:class="{ active: activeSection == index }" v-on:click="scrollToSection(index)" v-for="(offset, index) in offsets" v-bind:key="index">{{ menuString[index] }} </span>
      </div>
    </div>
    <!-- </head> -->
    <div>
      <!-- Nanti tambahkan @scroll="onScroll" untuk pakai event onScroll -->
      <div class="fullpage turunsikit">
        <section class="turunY">
          <!-- <h1>Vue.js Fullpage Scroll</h1>
        <p>by <a href="https://webdeasy.de/?referer=cp-NVOEBL" target="_blank">WebDEasy</a></p>
        <ul class="no-dot-list">
          <li>
            <img src="http://riadentalcare.com/asset-user/images/dental2.png" alt="Image" class="size-quarter">
          </li>
        </ul> -->
          <!-- ini copas SC bang dandi -->
          <!-- Ini setengah pertama beranda -->
          <div class="container margin-bottom-large">
            <div class="row align-items-left">
              <div class="col-lg-6 float-left">
                <span class="subheading above-title">Praktek Dokter Gigi Batam</span>
                <div class="title-blue text-size-large" style="text-align: left">Ria Dental Care</div>
                <p class="mb-4">Saat ini Ria Dental Care Terdiri dari 3 Cabang yaitu Ria Dental Care Botania, Ria Dental Care Batu Aji, dan Ria Dental Care Nagoya</p>
                <div class="container mt-5">
                  <div>
                    <b-button pill variant="info" v-b-modal.modal-1> <div class="white-text">Klik Disini Untuk Reservasi !</div></b-button>

                    <b-modal id="modal-1" title="Informasi Reservasi" size="lg" hide-header-close header-class="above-title">
                      <div class="modal-dialog modal-lg">
                        <div class="modal-content">
                          <div class="modal-body">
                            <!-- <button type="button" class="btn-close" data-dismiss="modal">&times;</button> -->

                            <p class="text-center">Hubungi Admin untuk melakukan reservasi</p>
                            <div class="row">
                              <div class="col-lg-6">
                                <div class="card">
                                  <img src="http://riadentalcare.com/asset-user/images/reservasi1.jpg" width="100%" height="250px" />

                                  <div class="card-body">
                                    <b-button pill variant="info" v-b-modal.modal-2> <div class="white-text">Reservasi Mandiri</div></b-button>
                                    <b-modal id="modal-2" title="Reservasi Mandiri" size="lg" hide-header-close header-class="above-title">
                                      <div class="modal-content">
                                        <div class="modal-body">
                                          <!-- <button type="button" class="close" data-dismiss="modal" data-toggle="modal" data-target="#myModal">&times;</button> -->
                                          <!-- <h2 class="text-center text-primary"><b></b></h2> -->
                                          <p class="text-center">Lakukan Reservasi Mandiri Untuk Mempermudah Anda Dalam Mendapatkan Nomor Antrian</p>
                                          <form action="http://riadentalcare.com/antrian" method="post">
                                            <input type="hidden" name="_token" value="U4a6KQdeRUAcCV3jN8YVVDtOUJZEr5VT1Oczl2TJ" />
                                            <div id="validation-errors"></div>
                                            <div class="form-group">
                                              <label for="id_admin">Cabang</label>
                                              <select name="id_admin" id="id_admin" class="form-control" required>
                                                <option value="ID0001">RDC Botania</option>
                                                <option value="ID0002">RDC Batu Aji</option>
                                                <option value="ID0003">RDC Nagoya</option>
                                              </select>
                                            </div>
                                            <div class="row">
                                              <div class="col-md-6">
                                                <div class="form-group tgl">
                                                  <label for="tgl">Tanggal Booking Antrian<sup>*</sup></label>
                                                  <input type="date" class="form-control" name="tgl" id="tgl" value="2022-01-21" required />
                                                  <span id="alert-tgl" class="" role="alert"></span>
                                                </div>
                                              </div>
                                              <div class="col-md-6">
                                                <div class="form-group jam">
                                                  <label for="jam">Jam Booking Antrian<sup>*</sup></label>
                                                  <input type="time" class="form-control is-valid" name="jam" id="jam" min="12:00" max="23:59" value="12:00" required />
                                                  <span id="alert-jam" class="" role="alert"></span>
                                                </div>
                                              </div>
                                            </div>
                                            <div class="form-group pasien">
                                              <label for="pasien">Pasien<sup>*</sup></label>
                                              <input type="text" class="form-control" name="pasien" id="pasien" placeholder="Masukkan ID Pasien atau NIK atau No. HP terdaftar..." required />
                                              <span id="alert-pasien" class="" role="alert"></span>
                                            </div>
                                            <div class="form-group">
                                              <label for="keluhan">Keluhan<sup>*</sup></label>
                                              <textarea name="keluhan" id="keluhan" rows="5" class="form-control" required placeholder="Masukkan Keluhan..."></textarea>
                                            </div>
                                            <div class="card">
                                              <div class="card-body">
                                                <button type="submit" class="btn btn-primary col-12" id="submit">Dapatkan Antrian</button>
                                              </div>
                                            </div>
                                          </form>
                                        </div>
                                        <div class="modal-footer">
                                          <p>Belum terdaftar? Daftarkan diri secara manual <a href="#" data-toggle="modal" data-target="#myModal4">di sini</a>.</p>
                                        </div>
                                      </div>
                                      <template #modal-footer> <p></p> </template>
                                      <template #modal-header-close>
                                        <button type="button" class="btn-close" data-dismiss="modal">&times;</button>
                                      </template>
                                    </b-modal>
                                    <!-- <a href="#" data-toggle="modal" data-target="#myModal3" class="btn btn-primary btn-block">Reservasi Mandiri</a> -->
                                  </div>
                                </div>
                              </div>
                              <div class="col-lg-6">
                                <div class="card">
                                  <img src="http://riadentalcare.com/asset-user/images/reservasi2.jpg" width="100%" height="250px" />
                                  <div class="card-body">
                                    <!-- <a href="#" data-toggle="modal" data-target="#myModal2" data-dismiss="modal" class="btn btn-primary btn-block">Reservasi Via Admin Receptionist</a> -->
                                    <b-button pill variant="info" v-b-modal.modal-3> <div class="white-text">Reservasi Via Admin Receptionist</div></b-button>
                                    <b-modal id="modal-3" title="Pilihan Cabang Reservasi" size="lg" hide-header-close header-class="above-title">
                                      <!-- <button type="button" class="close" data-dismiss="modal" data-toggle="modal" data-target="#myModal">&times;</button> -->

                                      <p class="text-center">Silahkan Pilih Cabang Ria Dental Care Yang Ingin Dihubungi</p>
                                      <div class="row">
                                        <div class="col-md-4">
                                          <div class="card">
                                            <img src="http://riadentalcare.com/asset-user/images/modal/rdc1.jpg" width="100%" height="150px" />
                                            <div class="card-body">
                                              <a
                                                href="https://api.whatsapp.com/send?phone=6285363127424&text=Hallo Admin Ria Dental Care Botania, Saya ingin melakukan reservasi, Mohon Dibantu"
                                                target="_blank"
                                                class="btn btn-primary btn-block"
                                                >RDC Botania</a
                                              >
                                            </div>
                                          </div>
                                        </div>
                                        <div class="col-md-4">
                                          <div class="card">
                                            <img src="http://riadentalcare.com/asset-user/images/modal/rdc2.jpg" width="100%" height="150px" />
                                            <div class="card-body">
                                              <a
                                                href="https://api.whatsapp.com/send?phone=6282360190016&text=Hallo Admin Ria Dental Care Batu Aji, Saya ingin melakukan reservasi, Mohon Dibantu"
                                                target="_blank"
                                                class="btn btn-primary btn-block"
                                                >RDC Aji</a
                                              >
                                            </div>
                                          </div>
                                        </div>
                                        <div class="col-md-4">
                                          <div class="card">
                                            <img src="http://riadentalcare.com/asset-user/images/modal/rdc3.jpg" width="100%" height="150px" />
                                            <div class="card-body">
                                              <a href="" target="_blank" class="btn btn-primary btn-block">RDC Nagoya</a>
                                            </div>
                                          </div>
                                        </div>
                                      </div>
                                      <template #modal-footer> <p></p> </template>
                                    </b-modal>
                                  </div>
                                </div>
                              </div>
                            </div>
                          </div>
                        </div>
                      </div>
                      <template #modal-footer> <p></p> </template>
                    </b-modal>
                  </div>
                </div>
                <br /><br /><br />
              </div>
              <div class="col-lg-6">
                <figure class="illustration">
                  <img src="http://riadentalcare.com/asset-user/images/dental2.png" alt="Image" class="img-fluid" />
                </figure>
              </div>
              <div class="col-lg-6"></div>
            </div>
          </div>
          <!-- Ini setengah terakhir beranda -->
          <!-- <a href="https://api.whatsapp.com/send?phone=6282360190016&text=Hallo Admin Ria Dental Care Batu Aji, Saya ingin melakukan reservasi, Mohon Dibantu">Hubungin Admin RDC Botania</a> -->

          <div class="container">
            <div>
              <p class="above-title text-size-large" style="text-align: center">Cabang Ria Dental Care</p>
              <p class="text-subtitle" style="text-align: center">Saat ini Ria Dental Care Terdiri Dari 3 Cabang Sebagai Berikut</p>
              <div class="row d-flex justify-content-center turun-sikit-card" style="width: 100%">
                <div class="card margin-horizontal border-0" style="width: 20rem">
                  <img src="http://riadentalcare.com/asset-user/images/cabang/rdc1.jpg" class="card-img-top" alt="..." />
                  <div class="card-body">
                    <h5 class="card-title above-title">RDC Botania</h5>
                    <b-button pill variant="info"> <div class="white-text">Hubungin Admin RDC Botania</div></b-button>
                  </div>
                </div>
                <div class="card margin-horizontal border-0 turun-sikit-card" style="width: 20rem">
                  <img src="http://riadentalcare.com/asset-user/images/cabang/rdc2.jpg" class="card-img-top" alt="..." />
                  <div class="card-body">
                    <h5 class="card-title above-title">RDC Batu Aji</h5>
                    <b-button pill variant="info"> <div class="white-text">Hubungin Admin RDC Botania</div></b-button>
                  </div>
                </div>
                <div class="card margin-horizontal border-0 turun-sikit-card" style="width: 20rem">
                  <img src="http://riadentalcare.com/asset-user/images/cabang/rdc3.jpg" class="card-img-top" alt="..." />
                  <div class="card-body">
                    <h5 class="card-title above-title">RDC Nagoya</h5>
                    <b-button pill variant="info"> <div class="white-text">Hubungin Admin RDC Botania</div></b-button>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </section>
        <div class="halfpage background blue"></div>
      </div>

      <section class="fullpage">
        <div class="container p-5">
          <b-row align-h="between">
            <b-col>
              <img src="http://riadentalcare.com/asset-user/images/new/rdc1.jpeg" style="width: 100%" />
            </b-col>
            <b-col>
              <!-- <h2 class="above-title">Ria Dental Care</h2> -->
              <h3 class="mb-0 text-primary"><b>Ria Dental Care</b></h3>
              <p>Ria Dental Care merupakan sebuah tempat Praktek Dokter Gigi yang dikelola oleh drg Ria Oktamilda yang memiliki 3 cabang sebagai berikut:</p>
              <p></p>
              <p>Ria Dental Care Botania<br />Alamat : Ruko Pesona Niaga blok C no 7 Dekat plaza botania 1, didepan perumahan holliwood hill</p>
              <p>Ria Dental Care Batu Aji<br />Alamat : Ruko Batu Permata Blok B nomor 9, Batam City Depan SP Plaza sederetan Holland Bakery dan KFC</p>
              <p>Ria Dental Care Nagoya<br />Alamat : Batam, Match River, Batu Ampar, Kota Batam, Kepulauan Riau 29444</p>
              <p>Jadwal praktek sebagai berikut :</p>
              <ul class="list-check list-unstyled mb-5">
                <li>Senin - Minggu : 12.00 - 19.00 WIB</li>
                <li>Tanggal Merah : On Call</li>
              </ul>
              <div class="d-flex align-items-center m-5">
                <img src="http://riadentalcare.com/asset-user/images/person_1.jpg" width="100px" height="100px" class="rounded-circle" style="object-fit: cover" />
                <div class="text pl-3">
                  <div class="mx-3">
                    <h3 class="mb-0 text-primary"><b>drg. Ria Oktamilda</b></h3>
                    <span class="position">Owner</span>
                  </div>
                </div>
              </div>
            </b-col>
          </b-row>
        </div>
        <div class="fullpage aligning-items-between light-pink p-5">
          <b-row>
            <b-col>
              <div class="m-5">
                <b-row>
                  <b-col>
                    <b-card img-src="https://drive.google.com/uc?export=view&id=1EyXunKbsAY8SWvFv58OcrE1tYlK6dn3_" img-alt="Image" img-top tag="article" style="max-width: 20rem; transform: translateZ(-100px)" class="mb-2 border-0">
                      <b-card-text class="above-title">Memiliki 3 Cabang</b-card-text>
                      <b-card-text class="text-subtitle">Saat ini Ria Dental Care Memiliki 3 Cabang yaitu : Ria Dental Care Cabang Botania, Ria Dental Care Cabang Batu Aji, dan Ria Dental Care Cabang Batu Nagoya</b-card-text>
                    </b-card>
                  </b-col>
                  <b-col>
                    <b-card img-src="https://drive.google.com/uc?export=view&id=1PHChaOV4p62Hjs_d_w9QMOLy2w9L-t0H" img-alt="Image" img-top tag="article" style="max-width: 20rem" class="mb-2 border-0">
                      <b-card-text class="above-title">Sudah Banyak Pasien Yang Berlangganan</b-card-text>
                      <b-card-text class="text-subtitle">Data Pasien yang sudah terdaftar lebih dari 13.826+ Pasien</b-card-text>
                    </b-card>
                  </b-col>
                </b-row>
                <b-row>
                  <b-col>
                    <b-card img-src="https://drive.google.com/uc?export=view&id=1bC9v6nNv6ZndRbCT5OmXGKnyZCmQeyM2" img-alt="Image" img-top tag="article" style="max-width: 20rem" class="mb-2 border-0">
                      <b-card-text class="above-title">Memiliki Banyak Promosi</b-card-text>
                      <b-card-text class="text-subtitle">Setiap ada event - event besar memiliki promosi cek terus instagramnya untuk mendapatkan informasi lebih efektif</b-card-text>
                    </b-card>
                  </b-col>
                  <b-col>
                    <b-card img-src="https://drive.google.com/uc?export=view&id=1LfDJvOcvhlfS8nm38i19UfTvU-78L8AD" img-alt="Image" img-top tag="article" style="max-width: 20rem" class="mb-2 border-0">
                      <b-card-text class="above-title">Harga Terjangkau</b-card-text>
                      <b-card-text class="text-subtitle">Pelayanan dokter gigi dengan harga terjangkau</b-card-text>
                    </b-card>
                  </b-col>
                </b-row>
              </div>
            </b-col>
            <b-col>
              <img src="http://riadentalcare.com/asset-user/images/new/rdc2.jpeg" />
            </b-col>
          </b-row>
        </div>
        <!-- <ul class="no-dot-list">
          <li><div>Something</div></li>
          <li><div>Something</div></li>
        </ul> -->
      </section>

      <section class="fullpage">
        <div class="container mt-5">
          <div>
            <p class="above-title text-size-large" style="text-align: center">Our Portofolio</p>
            <p class="text-subtitle" style="text-align: center">Portofolio Ria Dental Care Cabang Botania dan Batu Aji</p>
            <b-row align-h="between">
              <b-col cols="4">
                <b-card img-src="http://riadentalcare.com/asset-user/images/rdc1.jpeg" img-height="250px" img-alt="Image" img-top tag="article" style="max-width: 20rem; transform: translateZ(-100px)" class="mb-2 border-0">
                  <b-card-text class="above-title text-center">Dentist Room</b-card-text>
                </b-card>
              </b-col>
              <b-col cols="4">
                <b-card img-src="http://riadentalcare.com/asset-user/images/new/rdc3.jpeg" img-height="250px" img-alt="Image" img-top tag="article" style="max-width: 20rem; transform: translateZ(-100px)" class="mb-2 border-0">
                  <b-card-text class="above-title text-center">Lobby Room</b-card-text>
                </b-card>
              </b-col>
              <b-col cols="4">
                <b-card img-src="http://riadentalcare.com/asset-user/images/new/rdc5.jpeg" img-height="250px" img-alt="Image" img-top tag="article" style="max-width: 20rem; transform: translateZ(-100px)" class="mb-2 border-0">
                  <b-card-text class="above-title text-center">Receptionist</b-card-text>
                </b-card>
              </b-col>
            </b-row>
            <b-row align-h="between">
              <b-col cols="4">
                <b-card img-src="http://riadentalcare.com/asset-user/images/new/rdc4.jpeg" img-height="250px" img-alt="Image" img-top tag="article" style="max-width: 20rem; transform: translateZ(-100px)" class="mb-2 border-0">
                  <b-card-text class="above-title text-center">RDC Room</b-card-text>
                </b-card>
              </b-col>
              <b-col cols="4">
                <b-card img-src="http://riadentalcare.com/asset-user/images/new/rdc6.jpeg" img-height="250px" img-alt="Image" img-top tag="article" style="max-width: 20rem; transform: translateZ(-100px)" class="mb-2 border-0">
                  <b-card-text class="above-title text-center">Lobby Room</b-card-text>
                </b-card>
              </b-col>
              <b-col cols="4">
                <b-card img-src="http://riadentalcare.com/asset-user/images/rdc8.jpg" img-height="250px" img-alt="Image" img-top tag="article" style="max-width: 20rem; transform: translateZ(-100px)" class="mb-2 border-0">
                  <b-card-text class="above-title text-center">Relationship</b-card-text>
                </b-card>
              </b-col>
            </b-row>
          </div>
        </div>
        <div class="container">
          <div>
            <p class="above-title text-size-large" style="text-align: center">Our Video</p>
            <p class="text-subtitle" style="text-align: center">Video Promosi Ria Dental Care Cabang Botania dan Batu Aji</p>
            <b-row class="my-5">
              <b-col>
                <iframe id="player" type="text/html" width="500" src="http://riadentalcare.com/asset-user/video/rdc1.mp4" frameborder="0"></iframe>
              </b-col>
              <b-col>
                <iframe id="player" type="text/html" width="500" src="http://riadentalcare.com/asset-user/video/rdc2.mp4" frameborder="0"></iframe>
              </b-col>
            </b-row>
          </div>
        </div>
      </section>
      <section class="fullpage green">
        <h1>Section 4</h1>
        <p>Tutorial <a href="https://webdeasy.de/en/programming-vue-js-fullpage-scroll/?referer=cp-NVOEBL" target="_blank">here</a></p>
      </section>
    </div>
    <footer>
      <div style="text-align: center">Copyright ©2022 All rights reserved | Designed by Aldi Irsan Majid</div>
    </footer>
  </div>
</template>

<script>
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: "App",
  // el: "#app",
  // components: {
  //   HelloWorld,
  // },
  data: function () {
    return {
      inMove: false,
      activeSection: 0,
      offsets: [],
      menuString: ["Home", "About", "Portofolio", "Contact"],
      touchStartY: 0,
    };
  },
  methods: {
    // onScroll ({ target: { scrollTop, clientHeight, scrollHeight }}) {
    //   if (scrollTop + clientHeight >= scrollHeight) {
    //     this.moveDown();
    //     console.log('moveDown onScroll Called');
    //   } else {
    //     this.moveUp();
    //     console.log('moveDown onScroll Called');
    //   }
    // },
    calculateSectionOffsets() {
      let sections = document.getElementsByTagName("section");
      let length = sections.length;
      console.log("ini terpanggil kok " + sections.length);

      for (let i = 0; i < length; i++) {
        let sectionOffset = sections[i].offsetTop;
        this.offsets.push(sectionOffset);
      }
    },
    someThingToDo() {},
    // handleMouseWheel: function(e) {

    //   if (e.wheelDelta < 30 && !this.inMove) {
    //     this.moveUp();
    //   } else if (e.wheelDelta > 30 && !this.inMove) {
    //     this.moveDown();
    //   }

    //   e.preventDefault();
    //   return false;
    // },
    // handleMouseWheelDOM: function(e) {

    //   if (e.detail > 0 && !this.inMove) {
    //     this.moveUp();
    //   } else if (e.detail < 0 && !this.inMove) {
    //     this.moveDown();
    //   }

    //   return false;
    // },
    // moveDown() {
    //   this.inMove = true;
    //   this.activeSection--;

    //   // if(this.activeSection < 0) this.activeSection = this.offsets.length - 1;
    //   if(this.activeSection < 0) this.activeSection = 0;

    //   this.scrollToSection(this.activeSection, true);
    //   console.log('moveDown Terpanggil');
    // },
    // moveUp() {
    //   this.inMove = true;
    //   this.activeSection++;

    //   // if(this.activeSection > this.offsets.length - 1) this.activeSection = 0;
    //   if(this.activeSection > this.offsets.length - 1) this.activeSection = this.offsets.length-1;

    //   this.scrollToSection(this.activeSection, true);
    //   console.log('moveUp Terpanggil');

    // },
    scrollToSection(id, force = false) {
      if (this.inMove && !force) return false;

      this.activeSection = id;
      this.inMove = true;

      let sections = document.getElementsByTagName("section");
      sections[id].scrollIntoView({ behavior: "smooth" });

      setTimeout(() => {
        this.inMove = false;
      }, 400);
    },
    // touchStart(e) {
    //   e.preventDefault();

    //   this.touchStartY = e.touches[0].clientY;
    // },
    // touchMove(e) {
    //   if(this.inMove) return false;
    //   e.preventDefault();

    //   const currentY = e.touches[0].clientY;

    //   if(this.touchStartY < currentY) {
    //     this.moveDown();
    //   } else {
    //     this.moveUp();
    //   }

    //   this.touchStartY = 0;
    //   return false;
    // }
  },
  // beforeCreate(){
  //   this.calculateSectionOffsets();

  // },

  mounted() {
    this.calculateSectionOffsets();
  },
  created() {
    // this.calculateSectionOffsets();
    // window.addEventListener('scroll', this.onScroll, { passive: false })
    // window.addEventListener('DOMMouseScroll', this.handleMouseWheelDOM);  // Mozilla Firefox
    // window.addEventListener('mousewheel', this.handleMouseWheel, { passive: false }); // Other browsers
    // window.addEventListener('touchstart', this.touchStart, { passive: false }); // mobile devices
    // window.addEventListener('touchmove', this.touchMove, { passive: false }); // mobile devices
  },
  // updated() {
  //   this.calculateSectionOffsets();

  // },
  destroyed() {
    // window.removeEventListener('scroll', this.onScroll);  // Other browsers
    // window.removeEventListener('mousewheel', this.handleMouseWheel, { passive: false });  // Other browsers
    // window.removeEventListener('DOMMouseScroll', this.handleMouseWheelDOM); // Mozilla Firefox
    // window.removeEventListener('touchstart', this.touchStart); // mobile devices
    // window.removeEventListener('touchmove', this.touchMove); // mobile devices
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

body {
  margin: 0;
  color: #fff;
  font-family: Helvetica, arial, sans-serif;
  /* overflow: hidden; */
}

.margin-horizontal {
  margin-right: 10px;
  margin-left: 10px;
}

.title-blue {
  color: #42bfd0;
  font-weight: bold;
  size: 40px;
}

.above-title {
  color: #42bfd0;
  font-weight: bold;
}

.text-subtitle {
  color: #b8b5b5;
  font-size: small;
}

.text-size-large {
  font-size: 30px;
}

.white-text {
  color: #fff;
}

h2 {
  position: fixed;
}

.size-quarter {
  width: 40%;
}

.background {
  color: #a86895;
  position: absolute;
  top: 0;
  left: 0;
  z-index: -100;
}

.sections-menu {
  /* align-items: center; */

  position: fixed;
  /* left: 50%; */
  /* top: 1rem; */
  width: 100%;
  height: 10%;
  /* transform: translateZ(1000px); */
  /* position: relative; */
  z-index: +1;
  /* overflow: auto; */

  background-color: #fff;
  /* transform: translateY(10%); */

  /* right: 1rem;
  top: 50%; */
  /* transform: translateY(-50%); */
}
.sections-menu .right-div {
  width: 50%;
  height: 100%;
  float: right;
  /* transform: translateY(20%); */
  /* text-decoration-color: #000; */
  /* background-color: #111; */
}
.sections-menu .right-div .menu-point {
  width: 10px;
  height: 10%;
  /* background-color: #FFF; */
  /* top: 50%; */
  display: inline-block;
  margin: 2rem 4rem 2rem 4rem;
  opacity: 0.6;
  transition: 0.4s ease all;
  cursor: pointer;
}

.sections-menu .right-div .active {
  height: 100%;

  /* background-color: #000; */
  margin: 2rem 2rem 2rem 2rem;
  opacity: 1;
  /* margin: 2rem; */
  transform: scale(1.5) translateX(-100%);
  transform-origin: center;
}

.custom-button-info {
  background-color: #42bfd0;
}

.fullpage {
  min-height: 200%;
  /* height:100%; */
  width: 100%;
  overflow: auto;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.halfpage {
  min-height: 100%;
  /* height:100%; */
  width: 100%;
  overflow: auto;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
.aligning-items-between {
  align-items: stretch;
}
h1 {
  font-size: 6em;
  margin: 0;
  text-align: center;
  padding: 0 1rem;
}

p {
  font-size: 1em;
}

.fullpage a {
  text-decoration: none;
  font-weight: 600;
  background: rgba(255, 255, 255, 0.3);
  padding: 5px 10px;
  color: #fff;
  margin-left: 5px;
}

.red {
  background-color: #ab4545;
}

.light-pink {
  background-color: #fffde2;
}

.fullpage .turunsikit {
  transform: translateZ(-150px);
}

.turun-sikit-card {
  position: relative;
  z-index: -1;
}

.fullpage .turunY {
  /* transform: translateY(10%); */
  padding-top: 10%;
  margin-bottom: 15%;
}

.blue {
  background-color: #ffdcf4;
  border-radius: 0px 0px 500px 0px;
  /* border: 2px solid #73AD21; */
  /* padding: 20px;
  width: 200px;
  height: 150px;  */
}

.green {
  background-color: #68c368;
}

h1.black {
  color: #000;
}
.no-dot-list {
  list-style-type: none;
  display: inline-block;
}
.margin-bottom-large {
  margin-bottom: 15%;
}
@media screen and (max-width: 1200px) {
  h1 {
    font-size: 2.5em;
  }
}
</style>
