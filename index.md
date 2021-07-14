<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">
  <title>Program Penggajian Karyawan</title>
</head>
<body>
<div class="container col-md-6 alert-primary pb-2 mt-2 rounded">
  <h1 class="text-center">Program Penggajian</h1>
  <div class="mb-3">
    <label  class="form-label" for="">Nama Pegawai</label>
    <input type="text" class="form-control" id="namapegawai" placeholder="Nama Pegawai">
  </div>
  <div class="mb-3">
    <label  class="form-label" for="">Jam Kerja Pegawai</label>
    <input type="number" class="form-control" id="jamkerja" placeholder="Jam Kerja">
  </div>
  <div class="mb-3">
    <label class="form-label" for="">Upah Per Jam</label>
    <input type="number" class="form-control" id="upahperjam" placeholder="Upah per Jam">
  </div>
  <div class="mb-3">
    <label class="form-label" for="">Jumlah Anak Pegawai</label>
    <input type="number" class="form-control" id="anak" placeholder="Anak">
  </div>
  <div class="mb-3">
    <label  class="form-label" for="">Gaji Pegawai</label>
    <input type="text" class="form-control" id="gajipegawai" placeholder="Gaji Pegawai" disabled>
  </div>
  <div class="mb-3">
    <label  class="form-label" for="">Tunjangan 10%</label>
    <input type="text" class="form-control" id="tunjangan" placeholder="Tunj Anak 10%" disabled>
  </div>
  <div class="mb-3">
    <label  class="form-label" for="">Total Gaji</label>
    <input type="text" class="form-control" id="totalgaji" placeholder="Total Gaji" disabled>
  </div>
  <div class="mb-3">
    <button type="submit" class="btn btn-outline-danger" onclick="gaji()">Proses</button>
  </div>
  <h6 id="hasil"></h6>
</div>
  <script>
    function gaji() {
    let namapegawai = document.getElementById('namapegawai').value;
    let jamkerja = document.getElementById('jamkerja').value;
    let upahperjam = document.getElementById('upahperjam').value;
    let anak = document.getElementById('anak').value;
    let gajipegawai = document.getElementById('gajipegawai').value;
    let tunjangan = document.getElementById('tunjangan').value = 'Belum Di Input';
    let totalgaji = document.getElementById('totalgaji').value = 'Belum Di Input';
    
    if(jamkerja >= 240) {
     if(anak > 1) {
       let potongan = gajipegawai * (anak / 100)
       totalgaji = gajipegawai - potongan
       document.getElementById('gajipegawai').value = upahperjam * jamkerja;
      document.getElementById('tunjangan').value = potongan;
      document.getElementById('totalgaji').value = totalgaji;
      document.getElementById('hasil').innerHTML = '<svg xmlns="http://www.w3.org/2000/svg" style="display: none;"><symbol id="check-circle-fill" fill="currentColor" viewBox="0 0 16 16"><path d="M16 8A8 8 0 1 1 0 8a8 8 0 0 1 16 0zm-3.97-3.03a.75.75 0 0 0-1.08.022L7.477 9.417 5.384 7.323a.75.75 0 0 0-1.06 1.06L6.97 11.03a.75.75 0 0 0 1.079-.02l3.992-4.99a.75.75 0 0 0-.01-1.05z"/></symbol></svg><div class="alert alert-success d-flex align-items-center" role="alert"><svg class="bi flex-shrink-0 me-2" width="24" height="24" role="img" aria-label="Success:"><use xlink:href="#check-circle-fill"/></svg><div>Anda Tidak Kena Potongan</div></div>'
     }
     else {
      let potongan = gajipegawai * (anak / 100)
       totalgaji = gajipegawai - potongan
       document.getElementById('gajipegawai').value = upahperjam * jamkerja;
      document.getElementById('tunjangan').value = 'Tidak Ada Potongan Tunjangan';
      document.getElementById('totalgaji').value = totalgaji;
      document.getElementById('hasil').innerHTML = '<svg xmlns="http://www.w3.org/2000/svg" style="display: none;"><symbol id="check-circle-fill" fill="currentColor" viewBox="0 0 16 16"><path d="M16 8A8 8 0 1 1 0 8a8 8 0 0 1 16 0zm-3.97-3.03a.75.75 0 0 0-1.08.022L7.477 9.417 5.384 7.323a.75.75 0 0 0-1.06 1.06L6.97 11.03a.75.75 0 0 0 1.079-.02l3.992-4.99a.75.75 0 0 0-.01-1.05z"/></symbol></svg><div class="alert alert-success d-flex align-items-center" role="alert"><svg class="bi flex-shrink-0 me-2" width="24" height="24" role="img" aria-label="Success:"><use xlink:href="#check-circle-fill"/></svg><div>Anda Tidak Kena Potongan</div></div>'
     }
      
    }
    else {
      if(anak > 1) {
       let potongan = gajipegawai * (anak / 100)
       totalgaji = gajipegawai - potongan
       let jamkeseluruhan = 245
      document.getElementById('gajipegawai').value = upahperjam * jamkerja;
      document.getElementById('tunjangan').value = potongan;
      document.getElementById('totalgaji').value = totalgaji;
      document.getElementById('hasil').innerHTML = '<svg xmlns="http://www.w3.org/2000/svg" style="display: none;"><symbol id="exclamation-triangle-fill" fill="currentColor" viewBox="0 0 16 16"><path d="M8.982 1.566a1.13 1.13 0 0 0-1.96 0L.165 13.233c-.457.778.091 1.767.98 1.767h13.713c.889 0 1.438-.99.98-1.767L8.982 1.566zM8 5c.535 0 .954.462.9.995l-.35 3.507a.552.552 0 0 1-1.1 0L7.1 5.995A.905.905 0 0 1 8 5zm.002 6a1 1 0 1 1 0 2 1 1 0 0 1 0-2z"/></symbol></svg><div class="alert alert-danger d-flex align-items-center" role="alert"><svg class="bi flex-shrink-0 me-2" width="24" height="24" role="img" aria-label="Danger:"><use xlink:href="#exclamation-triangle-fill"/></svg><div>Jam Kerja Anda Kurang Dari 245 Jam</div></div>'  
     }
     else {
      let potongan = gajipegawai * (anak / 100)
       totalgaji = gajipegawai - potongan
       let jamkeseluruhan = 245
      document.getElementById('gajipegawai').value = upahperjam * jamkerja;
      document.getElementById('tunjangan').value = "Tidak Ada Potongan Tunjangan";
      document.getElementById('totalgaji').value = totalgaji;
      document.getElementById('hasil').innerHTML = '<svg xmlns="http://www.w3.org/2000/svg" style="display: none;"><symbol id="exclamation-triangle-fill" fill="currentColor" viewBox="0 0 16 16"><path d="M8.982 1.566a1.13 1.13 0 0 0-1.96 0L.165 13.233c-.457.778.091 1.767.98 1.767h13.713c.889 0 1.438-.99.98-1.767L8.982 1.566zM8 5c.535 0 .954.462.9.995l-.35 3.507a.552.552 0 0 1-1.1 0L7.1 5.995A.905.905 0 0 1 8 5zm.002 6a1 1 0 1 1 0 2 1 1 0 0 1 0-2z"/></symbol></svg><div class="alert alert-danger d-flex align-items-center" role="alert"><svg class="bi flex-shrink-0 me-2" width="24" height="24" role="img" aria-label="Danger:"><use xlink:href="#exclamation-triangle-fill"/></svg><div>Jam Kerja Anda Kurang Dari 245 Jam </div></div>'
     }
    }
  }
  </script>
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-MrcW6ZMFYlzcLA8Nl+NtUVF0sA7MsXsP1UyJoMp4YLEuNSfAP+JcXn/tWtIaxVXM" crossorigin="anonymous"></script>
</body>
</html>
