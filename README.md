# Aplikasi Cek Nomor Ganjil/Genap
Tugas 1 - Adrian Akhmad Firdaus (2210010491)

---
# Deskripsi

Aplikasi berbasis Java ini memungkinkan pengguna untuk memasukkan angka, memeriksa apakah angka tersebut adalah **ganjil** atau **genap**, dan memberikan hasil validasi. Aplikasi ini juga dapat diperluas untuk mengecek apakah angka merupakan **bilangan prima**.

## Fitur Utama
1. **Cek Ganjil/Genap**: Memvalidasi input angka dan menentukan apakah angka tersebut ganjil atau genap.
2. **Validasi Input**: Hanya menerima angka, dengan error handling menggunakan `JOptionPane`.
3. **Fitur Tambahan**:
   - Pemeriksaan bilangan prima.
   - Membersihkan input secara otomatis saat teks difokuskan.
4. **Antarmuka GUI**:
   - **Komponen**: `JTextField`, `JButton`, `JLabel`, dan `JPanel`.
   - Event handling menggunakan `ActionListener`, `KeyAdapter`, dan `FocusListener`.

## Tampilan GUI
Aplikasi menggunakan layout sederhana dengan:
- `JTextField` untuk input angka.
- Tombol "Cek" untuk memvalidasi angka.
- `JLabel` untuk menampilkan hasil.

## Kode Sumber
Berikut adalah contoh kode untuk beberapa fitur.

### Cek Ganjil atau Genap
```java
private void cekGanjilGenap() {
    try {
        int angka = Integer.parseInt(txtInput.getText());
        if (angka % 2 == 0) {
            lblHasil.setText("Angka " + angka + " adalah Genap");
        } else {
            lblHasil.setText("Angka " + angka + " adalah Ganjil");
        }
    } catch (NumberFormatException e) {
        JOptionPane.showMessageDialog(this, "Masukkan angka yang valid!", "Error", JOptionPane.ERROR_MESSAGE);
    }
}
```

### Pemeriksaan Bilangan Prima
```java
private boolean isPrima(int angka) {
    if (angka <= 1) return false;
    for (int i = 2; i <= Math.sqrt(angka); i++) {
        if (angka % i == 0) return false;
    }
    return true;
}
```

### Event Listener
```java
btnCek.addActionListener(e -> cekGanjilGenap());

txtInput.addKeyListener(new KeyAdapter() {
    public void keyTyped(KeyEvent e) {
        if (!Character.isDigit(e.getKeyChar())) {
            e.consume();
        }
    }
});

txtInput.addFocusListener(new FocusAdapter() {
    public void focusGained(FocusEvent e) {
        txtInput.setText("");
    }
});
```

## Petunjuk Penggunaan
1. Masukkan angka pada kotak teks.
2. Tekan tombol "Cek".
3. Hasil akan ditampilkan di bawah kotak input.
4. Jika angka tidak valid, pesan error akan muncul.

## Gambar pada saat Aplikasi Dijalankan

![image](https://github.com/user-attachments/assets/ca6b481a-c817-4b4d-a9ac-1edc7a43924e)


---
## Indikator Penilaian
| No  | Komponen            | Persentase |
| --- | ------------------- | ---------- |
| 1   | Komponen GUI        | 20%        |
| 2   | Logika Program      | 20%        |
| 3   | Event Handling      | 15%        |
| 4   | Kesesuaian UI       | 15%        |
| 5   | Memenuhi Variasi    | 30%        |

---
## Pembuat

Nama: Adrian Akhmad Firdaus

NPM: 2210010491

Kelas: 5A Reguler Pagi

Tugas : Tugas 1 - Aplikasi Pertambahan Dua Angka

Fakultas : Fakultas Teknologi Informasi (FTI)

Unversitas : Universitas Islam Kalimantan Muhammad Arsyad Al Banjari Banjarmasin
