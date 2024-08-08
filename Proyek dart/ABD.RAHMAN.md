# contoh proyek
```dart
void main() {
  // Daftar tugas
  List<String> tugas = ['Belajar Dart', 'Mengerjakan PR', 'Membaca buku'];
  print('Daftar tugas awal: $tugas');

  // Menambahkan tugas baru
  tugas.add('Pergi berolahraga');
  print('Daftar tugas setelah penambahan: $tugas');

  // Status tugas
  Map<String, bool> statusTugas = {
    'Belajar Dart': true,
    'Mengerjakan PR': false,
    'Membaca buku': false,
    'Pergi berolahraga': true
  };
  print('Status tugas: $statusTugas');

  // Memeriksa status tugas
  for (var tugas in tugas) {
    if (statusTugas[tugas] == true) {
      print('$tugas sudah selesai');
    } else {
      print('$tugas belum selesai');
    }
  }

  // Menambah tugas
  void tambahTugas(String tugasBaru) {
    tugas.add(tugasBaru);
    statusTugas[tugasBaru] = false;
  }
  tambahTugas('Belajar pemrograman');
  print('Daftar tugas setelah menambah: $tugas');

  // Menghapus tugas
  void hapusTugas(String tugasUntukDihapus) {
    tugas.remove(tugasUntukDihapus);
    statusTugas.remove(tugasUntukDihapus);
  }
  hapusTugas('Membaca buku');
  print('Daftar tugas setelah menghapus: $tugas');

  // Menghitung tugas selesai
  int hitungTugasSelesai() {
    int jumlahSelesai = 0;
    for (var status in statusTugas.values) {
      if (status) jumlahSelesai++;
    }
    return jumlahSelesai;
  }
  print('Jumlah tugas selesai: ${hitungTugasSelesai()}');

  // Menghitung tugas belum selesai
  int hitungTugasBelumSelesai() => tugas.length - hitungTugasSelesai();
  print('Jumlah tugas belum selesai: ${hitungTugasBelumSelesai()}');

  // Menampilkan tugas
  void tampilkanTugas() {
    for (var t in tugas) {
      print('Tugas: $t');
    }
  }
  tampilkanTugas();

  // Menandai tugas sebagai selesai
  void tandaiTugasSelesai(String tugasNama) {
    statusTugas[tugasNama] = true;
  }
  tandaiTugasSelesai('Mengerjakan PR');
  print('Status tugas setelah menandai selesai: $statusTugas');

  // Menyaring tugas yang belum selesai
  List<String> filterTugasBelumSelesai() {
    List<String> belumSelesai = [];
    for (var t in tugas) {
      if (!statusTugas[t]!) belumSelesai.add(t);
    }
    return belumSelesai;
  }
  List<String> tugasBelumSelesai = filterTugasBelumSelesai();
  print('Tugas belum selesai: $tugasBelumSelesai');
}
```