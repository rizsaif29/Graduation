<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Pengumuman Kelulusan MI Miftahul Huda Guyangan</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:'Segoe UI',sans-serif;
}

body{
    background:#f4f7fb;
    color:#333;
}

header{
    background:linear-gradient(135deg,#0d47a1,#1976d2);
    color:white;
    padding:30px;
    text-align:center;
}

header h1{
    margin-bottom:10px;
}

.container{
    max-width:900px;
    margin:30px auto;
    padding:20px;
}

.card{
    background:white;
    border-radius:15px;
    padding:30px;
    box-shadow:0 4px 12px rgba(0,0,0,0.1);
}

.info{
    background:#e3f2fd;
    border-left:5px solid #1976d2;
    padding:15px;
    margin-bottom:25px;
    border-radius:8px;
}

.search-box{
    display:flex;
    gap:10px;
    margin-bottom:20px;
}

.search-box input{
    flex:1;
    padding:12px;
    border:1px solid #ccc;
    border-radius:8px;
    font-size:16px;
}

.search-box button{
    background:#1976d2;
    color:white;
    border:none;
    padding:12px 25px;
    border-radius:8px;
    cursor:pointer;
}

.search-box button:hover{
    background:#1259a7;
}

.result{
    display:none;
    margin-top:20px;
    padding:20px;
    border-radius:10px;
}

.lulus{
    background:#e8f5e9;
    border-left:5px solid #2e7d32;
}

.notfound{
    background:#ffebee;
    border-left:5px solid #c62828;
}

.nama{
    font-size:24px;
    font-weight:bold;
    margin-bottom:10px;
}

.nilai{
    font-size:20px;
    margin-bottom:10px;
}

.status{
    font-size:22px;
    font-weight:bold;
    color:#2e7d32;
}

footer{
    text-align:center;
    padding:20px;
    color:#666;
    margin-top:30px;
}
</style>
</head>
<body>

<header>
    <h1>PENGUMUMAN KELULUSAN</h1>
    <h2>MI Miftahul Huda Guyangan</h2>
    <p>Kelas VI Tahun Pelajaran 2025/2026</p>
</header>

<div class="container">

    <div class="card">

        <div class="info">
            <strong>Petunjuk:</strong><br>
            Ketik nama lengkap siswa pada kolom pencarian kemudian klik tombol
            <b>Cari Hasil</b> untuk melihat nilai rata-rata dan status kelulusan.
        </div>

        <div class="search-box">
            <input type="text" id="namaSiswa" placeholder="Masukkan Nama Siswa">
            <button onclick="cariData()">Cari Hasil</button>
        </div>

        <div id="hasil" class="result"></div>

    </div>

</div>

<footer>
    © 2026 MI Miftahul Huda Guyangan - Pengumuman Kelulusan Kelas VI
</footer>

<script>

const dataSiswa = [
{nama:"AFIKA MARTA FITRIANA", nilai:"86,76", status:"LULUS"},
{nama:"ANDIKA SAPUTRA", nilai:"87,07", status:"LULUS"},
{nama:"ARJUNA AR RIZQI", nilai:"82,36", status:"LULUS"},
{nama:"AVIKA FADILLAH", nilai:"86,86", status:"LULUS"},
{nama:"BAGUS DWI PRATAMA PUTRA", nilai:"81,29", status:"LULUS"},
{nama:"DESKA FEBRIANO VIKENZO", nilai:"80,29", status:"LULUS"},
{nama:"DICKY ALFIAN MUSAFA", nilai:"88,71", status:"LULUS"},
{nama:"DZAKIRA KARIMA BILQIS", nilai:"95,14", status:"LULUS"},
{nama:"EDO DWI SAPUTRA", nilai:"81,57", status:"LULUS"},
{nama:"FADHIL MUHAMMAD", nilai:"84,86", status:"LULUS"},
{nama:"FIKRIA AKMAL ASSHOFI", nilai:"92,14", status:"LULUS"},
{nama:"GAMMA BRILIANT SYAPUTRA", nilai:"80,00", status:"LULUS"},
{nama:"LANGIT DWI ALVIANO", nilai:"79,93", status:"LULUS"},
{nama:"MAURA DWI ALIYANI", nilai:"80,43", status:"LULUS"},
{nama:"MUHAMMAD AFRIZAL EVAN NUGROHO", nilai:"83,36", status:"LULUS"},
{nama:"MUHAMMAD FADLAN IRSYAD", nilai:"89,29", status:"LULUS"},
{nama:"MUHAMMAD ROZIF MAHLUL AZAM", nilai:"84,43", status:"LULUS"},
{nama:"PUTRI AYU AZALIA", nilai:"85,50", status:"LULUS"},
{nama:"RAFAELIANSYAH FAHMI ANGGARA", nilai:"80,07", status:"LULUS"},
{nama:"RIFANA MEYKA SYAHWA", nilai:"85,14", status:"LULUS"},
{nama:"VANIA CARISSA SALSABILLA", nilai:"77,93", status:"LULUS"},
{nama:"AHMAD BAGAS DWI RAMDHANI", nilai:"89,57", status:"LULUS"}
];

function cariData(){

    const keyword = document
        .getElementById("namaSiswa")
        .value
        .trim()
        .toUpperCase();

    const hasil = document.getElementById("hasil");

    const siswa = dataSiswa.find(
        item => item.nama === keyword
    );

    if(siswa){

        hasil.style.display = "block";
        hasil.className = "result lulus";

        hasil.innerHTML = `
            <div class="nama">${siswa.nama}</div>
            <div class="nilai">
                Rata-rata Nilai : <b>${siswa.nilai}</b>
            </div>
            <div class="status">
                STATUS : ${siswa.status}
            </div>
        `;

    }else{

        hasil.style.display = "block";
        hasil.className = "result notfound";

        hasil.innerHTML = `
            <div class="nama">Data tidak ditemukan</div>
            <p>Pastikan nama siswa ditulis dengan benar.</p>
        `;
    }
}

document.getElementById("namaSiswa")
.addEventListener("keypress", function(event){
    if(event.key === "Enter"){
        cariData();
    }
});

</script>

</body>
</html>
