Berikut README yang bisa kamu gunakan untuk **Praktikum Modul 6 – Form dan Input Validation (Flutter)** sesuai dengan hasil tampilan pada gambar:

---

# Praktikum Mobile – Pertemuan 6

## Form & Input Validation pada Flutter

## Deskripsi

Praktikum ini membahas tentang pembuatan **form input** pada Flutter serta implementasi **validasi input** menggunakan `Form`, `TextFormField`, dan `Validator`.

Aplikasi yang dibuat berupa **halaman login sederhana** yang memvalidasi input pengguna sebelum diproses.

## Tujuan Pembelajaran

Berdasarkan modul praktikum :

* Membuat form input di Flutter
* Menggunakan `TextField` dan `TextEditingController`
* Menggunakan `Form` dan `GlobalKey`
* Membuat validasi input menggunakan `TextFormField`

## Fitur Aplikasi

* Form input:

  * Username
  * Password
* Validasi:

  * Tidak boleh kosong
* Tombol:

  * **Login / Submit**
* Feedback:

  * Menampilkan pesan error jika input kosong
  * Menampilkan pesan sukses jika valid

## Tampilan Aplikasi

### Halaman Login

<img width="749" height="867" alt="image" src="https://github.com/user-attachments/assets/ae90c065-3de3-4be9-91f9-acd6a6306b65" />


### Validasi Error

<img width="749" height="868" alt="image" src="https://github.com/user-attachments/assets/21326ad4-88f3-4af8-97a0-82b544a11840" />


### Validasi Berhasil

<img width="748" height="866" alt="image" src="https://github.com/user-attachments/assets/0eac394b-12a2-4492-b45c-273a5c6bc842" />

## Konsep yang Digunakan

### 1. Form & GlobalKey

Digunakan untuk mengelola dan memvalidasi form:

```dart
final _formKey = GlobalKey<FormState>();
```

### 2. TextEditingController

Digunakan untuk mengambil nilai input:

```dart
TextEditingController usernameController = TextEditingController();
TextEditingController passwordController = TextEditingController();
```

### 3. TextFormField + Validator

Contoh validasi:

```dart
validator: (value) {
  if (value == null || value.isEmpty) {
    return 'Field tidak boleh kosong';
  }
  return null;
}
```

### 4. Proses Validasi

Saat tombol ditekan:

```dart
if (_formKey.currentState!.validate()) {
  // sukses
} else {
  // error
}
```

## Cara Kerja Aplikasi

* User mengisi form login
* Saat tombol ditekan:

  * Sistem mengecek validasi melalui `_formKey`
  * Jika ada field kosong → tampil pesan error
  * Jika semua valid → tampil pesan sukses

## Teknologi yang Digunakan

* Flutter
* Dart

## Kesimpulan

Pada praktikum ini dapat disimpulkan bahwa:

* Form digunakan untuk mengelola input user
* `TextEditingController` digunakan untuk mengambil nilai input
* Validasi sangat penting untuk memastikan data yang dimasukkan benar
* `TextFormField` mempermudah implementasi validasi
