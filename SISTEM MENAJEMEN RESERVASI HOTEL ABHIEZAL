class ReservasiHotel:
    def __init__(self):
        self.reservasi = []  # Queue (FIFO) untuk daftar reservasi aktif
        self.riwayat = []    # Stack (LIFO) untuk riwayat reservasi selesai

    # CREATE: Menambahkan reservasi baru
    def tambah_reservasi(self, nama, kamar, durasi):
        reservasi = {
            'nama': nama,
            'kamar': kamar,
            'durasi': durasi
        }
        self.reservasi.append(reservasi)
        print(f"Reservasi untuk {nama} berhasil ditambahkan.")

    # READ: Menampilkan daftar reservasi aktif
    def lihat_reservasi(self):
        if not self.reservasi:
            print("Tidak ada reservasi aktif.")
        else:
            print("Daftar Reservasi Aktif:")
            for i, reservasi in enumerate(self.reservasi, start=1):
                print(f"{i}. Nama: {reservasi['nama']}, Kamar: {reservasi['kamar']}, Durasi: {reservasi['durasi']} malam")

    # UPDATE: Mengedit data reservasi
    def edit_reservasi(self, index, nama=None, kamar=None, durasi=None):
        if 0 <= index < len(self.reservasi):
            if nama:
                self.reservasi[index]['nama'] = nama
            if kamar:
                self.reservasi[index]['kamar'] = kamar
            if durasi:
                self.reservasi[index]['durasi'] = durasi
            print(f"Data reservasi pada indeks {index + 1} berhasil diperbarui.")
        else:
            print("Indeks tidak valid.")

    # DELETE: Menghapus reservasi dan memindahkannya ke riwayat
    def hapus_reservasi(self, index):
        if 0 <= index < len(self.reservasi):
            reservasi = self.reservasi.pop(index)
            self.riwayat.append(reservasi)
            print(f"Reservasi untuk {reservasi['nama']} telah dihapus dan dipindahkan ke riwayat.")
        else:
            print("Indeks tidak valid.")

    # SEARCHING: Mencari reservasi berdasarkan nama
    def cari_reservasi(self, nama):
        hasil = [reservasi for reservasi in self.reservasi if nama.lower() in reservasi['nama'].lower()]
        if hasil:
            print("Hasil Pencarian:")
            for reservasi in hasil:
                print(f"Nama: {reservasi['nama']}, Kamar: {reservasi['kamar']}, Durasi: {reservasi['durasi']} malam")
        else:
            print("Reservasi tidak ditemukan.")

    # SORTING: Mengurutkan reservasi berdasarkan durasi
    def urutkan_reservasi(self):
        self.reservasi.sort(key=lambda x: x['durasi'])
        print("Reservasi berhasil diurutkan berdasarkan durasi.")

    # Menampilkan riwayat reservasi
    def lihat_riwayat(self):
        if not self.riwayat:
            print("Riwayat reservasi kosong.")
        else:
            print("Riwayat Reservasi Selesai:")
            while self.riwayat:
                reservasi = self.riwayat.pop()
                print(f"Nama: {reservasi['nama']}, Kamar: {reservasi['kamar']}, Durasi: {reservasi['durasi']} malam")

# Program Utama
if __name__ == "__main__":
    sistem = ReservasiHotel()

    while True:
        print("\nSistem Manajemen Tiket Reservasi Hotel Abhiezal")
        print("1. Tambah Reservasi")
        print("2. Lihat Reservasi")
        print("3. Edit Reservasi")
        print("4. Hapus Reservasi")
        print("5. Cari Reservasi")
        print("6. Urutkan Reservasi")
        print("7. Lihat Riwayat")
        print("8. Keluar")

        pilihan = input("Pilih menu: ")

        if pilihan == "1":
            nama = input("Masukkan nama tamu: ")
            kamar = input("Masukkan nomor kamar: ")
            durasi = int(input("Masukkan durasi menginap (malam): "))
            sistem.tambah_reservasi(nama, kamar, durasi)
        elif pilihan == "2":
            sistem.lihat_reservasi()
        elif pilihan == "3":
            indeks = int(input("Masukkan indeks reservasi yang ingin diedit (dimulai dari 1): ")) - 1
            nama = input("Masukkan nama baru (kosongkan jika tidak ingin mengubah): ")
            kamar = input("Masukkan nomor kamar baru (kosongkan jika tidak ingin mengubah): ")
            durasi = input("Masukkan durasi baru (kosongkan jika tidak ingin mengubah): ")
            durasi = int(durasi) if durasi else None
            sistem.edit_reservasi(indeks, nama if nama else None, kamar if kamar else None, durasi)
        elif pilihan == "4":
            indeks = int(input("Masukkan indeks reservasi yang ingin dihapus (dimulai dari 1): ")) - 1
            sistem.hapus_reservasi(indeks)
        elif pilihan == "5":
            nama = input("Masukkan nama tamu yang dicari: ")
            sistem.cari_reservasi(nama)
        elif pilihan == "6":
            sistem.urutkan_reservasi()
        elif pilihan == "7":
            sistem.lihat_riwayat()
        elif pilihan == "8":
            print("Keluar dari program.")
            break
        else:
            print("Pilihan tidak valid. Coba lagi.")

