import json

# Nama file
filename = 'matkul.json'

# Fungsi untuk menambahkan data ke dalam file JSON
def tambah_matkul(matkul_baru):
    # Membaca data yang ada, jika file ada
    try:
        with open(filename, 'r') as file:
            data = json.load(file)
    except FileNotFoundError:
        # Jika file tidak ada, buat list baru
        data = []

    # Menambahkan data baru
    data.append(matkul_baru)

    # Menyimpan kembali ke file JSON
    with open(filename, 'w') as file:
        json.dump(data, file, indent=4)

# Input data baru
nama_matkul = input("Masukkan nama mata kuliah: ")
kode_matkul = input("Masukkan kode mata kuliah: ")

# Membuat dictionary untuk mata kuliah baru
matkul_baru = {
    'nama': nama_matkul,
    'kode': kode_matkul
}

# Memanggil fungsi untuk menambah mata kuliah
tambah_matkul(matkul_baru)
print("Data mata kuliah berhasil ditambahkan!")
