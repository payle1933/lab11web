# Lab11Web
```
Nama	Maulana Hasanudin
NIM	312010106
Kelas	TI.20.D.1
```
# 1. Buat folder baru dengan nama lab11_php_ci pada docroot webserver (htdocs)
![1](https://user-images.githubusercontent.com/101716660/176259725-dfb328ef-0afe-4bef-8ae9-75fe06b0d453.png)


# 2. Untuk mengaktifkan ekstentsi tersebut, melalu XAMPP Control Panel, pada bagian Apache klik Config -> PHP.ini
![2](https://user-images.githubusercontent.com/101716660/176259804-f6441cad-9941-49b4-a9c8-fe1ce54250dc.png)


# 3. Pada bagian extention, hilangkan tanda ; (titik koma) pada ekstensi yang akan diaktifkan. Kemudian simpan kembali filenya dan restart Apache web server.
![69](https://user-images.githubusercontent.com/101716660/176260279-4984e32a-0876-4f3c-8046-b82f35688792.png)



# 4. Instalasi Codeigniter 4
## Untuk melakukan instalasi Codeigniter 4 dapat dilakukan dengan dua cara, yaitu cara manual dan menggunakan composer. Pada praktikum ini kita menggunakan cara manual.

## Unduh Codeigniter dari website https://codeigniter.com/download
Extrak file zip Codeigniter ke direktori htdocs/lab11_php_ci.
Ubah nama direktory framework-4.x.xx menjadi ci4.
Buka browser dengan alamat http://localhost/lab11_php_ci/ci4/public/
![3](https://user-images.githubusercontent.com/101716660/176260115-caba1474-2748-46f5-8cb9-9b347f64f3e5.png)


# 5. Menjalankan CLI (Command Line Interface)
![4](https://user-images.githubusercontent.com/101716660/176260371-02a98743-d50e-4f2a-8c91-653baace2f3f.png)


# 6. Mengaktifkan Mode Debugging
## Codeigniter 4 menyediakan fitur debugging untuk memudahkan developer untuk mengetahui pesan error apabila terjadi kesalahan dalam membuat kode program. Secara default fitur ini belum aktif. Ketika terjadi error pada aplikasi akan ditampilkan pesan kesalahan seperti berikut.
![5](https://user-images.githubusercontent.com/101716660/176260446-9a074f35-3821-4be1-8c07-376dd4dd23d5.png)


## Semua jenis error akan ditampilkan sama. Untuk memudahkan mengetahui jenis errornya, maka perlu diaktifkan mode debugging dengan mengubah nilai konfigurasi pada environment variable CI_ENVIRONMENT menjadi development. Kemudian mengubah nama file env menjadi .env lalu setelah itu buka file tersebut dan ubah nilai variable CI_ENVORNMENT menjadi development. Setelah itu hapus tanda tagar (#) pada awal baris CI_ENVIRONMENT, ubah kode pada file app/Controller/Home.php hilangkan titik koma (;) pada akhir kode seperti berikut.
![6](https://user-images.githubusercontent.com/101716660/176260490-77e83884-dbd7-41a2-81be-8c0da53c89c9.png)

![7](https://user-images.githubusercontent.com/101716660/176260533-b25843b9-5298-4ffc-999d-18792f1a15a3.png)


## Maka hasilnya akan terjadi error seperti berikut.
![8](https://user-images.githubusercontent.com/101716660/176260576-9fe26221-f774-4f45-bf72-fa604d63290c.png)


# 7. Routing dan Controller
## Router terletak pada file app/config/Routes.php. Pada file tersebut kita dapat mendefinisikan route untuk aplikasi yang kita buat. Contoh: ```$routes->get('/', 'Home::index'); Kode tersebut akan mengarahkan rute untuk halaman home.

# 8. Membuat Route Baru.
![9](https://user-images.githubusercontent.com/101716660/176260641-971b2dde-f9f4-4d87-9bf3-1576996e4595.png)


## Untuk mengetahui route yang ditambahkan sudah benar, buka CLI dan jalankan perintah berikut. php spark routes
![10](https://user-images.githubusercontent.com/101716660/176260697-02f01bbc-5508-4a3f-a2f5-fe3a9aa75b92.png)


## Selanjutnya coba akses route yang telah dibuat dengan mengakses alamat url http://localhost:8080/about
![11](https://user-images.githubusercontent.com/101716660/176260725-e23d83dd-3d76-4573-b6e6-b7b295064810.png)


## Ketika diakses akan mucul tampilan error 404 file not found, itu artinya file/page tersebut tidak ada. Untuk dapat mengakses halaman tersebut, harus dibuat terlebih dahulu Contoller yang sesuai dengan routing yang dibuat yaitu Contoller Page.

# 9. Membuat Controller
## Selanjutnya adalah membuat Controller Page. Buat file baru dengan nama page.php pada direktori Controller kemudian isi kodenya seperti berikut.

![12](https://user-images.githubusercontent.com/101716660/176260858-c6df0268-0112-40e8-8e63-c945c81e0bd3.png)


## Selanjutnya refresh Kembali browser, maka akan ditampilkan hasilnya yaitu halaman sudah dapat diakses.
![13](https://user-images.githubusercontent.com/101716660/176260905-405a629a-6e19-4da7-a575-c3626913950e.png)


# 10. Auto Routing
## Secara default fitur autoroute pada Codeiginiter sudah aktif. Untuk mengubah status autoroute dapat mengubah nilai variabelnya. Untuk menonaktifkan ubah nilai true menjadi false.

## Tambahkan method baru pada Controller Page seperti berikut

![14](https://user-images.githubusercontent.com/101716660/176260944-7a8df393-3581-4b10-a0b5-dd2325bf9bff.png)


## Method ini belum ada pada routing, sehingga cara mengaksesnya dengan menggunakan alamat: http://localhost:8080/page/tos
![15](https://user-images.githubusercontent.com/101716660/176260973-e14df00c-0eaa-4fa6-b787-4b2d1b4c9099.png)


# 11. Membuat View
## Selanjutnya adalam membuat view untuk tampilan web agar lebih menarik. Buat file baru dengan nama about.php pada direktori view (app/view/about.php) kemudian isi kodenya seperti berikut.

![16](https://user-images.githubusercontent.com/101716660/176261041-2eeecf79-9976-401e-9b25-3796437ed556.png)


## Ubah method about pada class Controller Page menjadi seperti berikut:
![17](https://user-images.githubusercontent.com/101716660/176261088-edf690fa-97dc-4d1a-b0f4-4eb795154fe0.png)


## Kemudian lakukan refresh pada halaman tersebut.
![18](https://user-images.githubusercontent.com/101716660/176261138-52be4490-643d-42b2-891d-133f5d868b7d.png)


# 12. Membuat Layout Web dengan CSS
## Pada dasarnya layout web dengan css dapat diimplamentasikan dengan mudah pada codeigniter. Yang perlu diketahui adalah, pada Codeigniter 4 file yang menyimpan asset css dan javascript terletak pada direktori public.

## Buat file css pada direktori public dengan nama style.css (copy file dari praktikum lab4_layout. Kita akan gunakan layout yang pernah dibuat pada praktikum 4.

![19 x](https://user-images.githubusercontent.com/101716660/176261246-8a6f8582-f253-4ec0-aee2-aa43aed67220.png)


## Kemudian buat folder template pada direktori view kemudian buat file header.php dan footer.php
File app/view/template/header.php
![20](https://user-images.githubusercontent.com/101716660/176261299-24c67f7e-1a30-4f8f-814b-357dd677c2fe.png)


## File app/view/template/footer.php
![21](https://user-images.githubusercontent.com/101716660/176261362-211883ec-fe64-466c-9823-369fad7fbb97.png)


## Kemudian ubah file app/view/about.php seperti berikut.
![22](https://user-images.githubusercontent.com/101716660/176261407-bcc6d526-4f04-4719-b1f5-28a6b48fb033.png)


## Selanjutnya refresh tampilan pada alamat http://localhost:8080/about
![23](https://user-images.githubusercontent.com/101716660/176261511-cfb59894-dc8e-4b5c-b6ff-05a4b272cf9a.png)


# Pertanyaan dan Tugas !
## Lengkapi kode program untuk menu lainnya yang ada pada Controller Page, sehingga semua link pada navigasi header dapat menampilkan tampilan dengan layout yang sama.

## About
![24](https://user-images.githubusercontent.com/101716660/176261570-09ace02c-aea8-4e45-8125-d589f3e09626.png)

## Hasil Browser


## Contact
![27](https://user-images.githubusercontent.com/101716660/176261720-23a3d917-52f1-4a89-b7a0-79725ba81224.png)


## Hasil Browser
![28](https://user-images.githubusercontent.com/101716660/176261769-e24dd1b3-1103-4a87-8886-275c36598e9e.png)


# PRAKTIKUM 12: FRAMEWORK LANJUTAN (CRUD)
## Langkah-langkah Praktikum
## 1. Untuk memulai membuat aplikasi CRUD sederhana, yang perlu disiapkan adalah database server menggunakan MySQL. Pastikan MySQL Server sudah dapat dijalankan melalui XAMPP.
![29](https://user-images.githubusercontent.com/101716660/176261884-23f8750c-d6dd-40c6-8110-d7e3ce17aafb.png)


# 2. Konfigurasi Koneksi Database
## Selanjutnya membuat konfigurasi untuk menghubungkan dengan database server. Konfigurasi dapat dilakukan dengan dua cara, yaitu pada file app/config/database.php atau menggunakan file .env. Pada praktikum ini kita gunakan konfigurasi pada file .env. Konfigurasi dapat dilakukan dengan cara mengubah beberapa kode pada file htdocs\lab11_ci\ci4\.env. Dan hilangkan tanda pagar # didepan

![30](https://user-images.githubusercontent.com/101716660/176261952-d140eb4f-c878-4fd4-b66b-97fbecde1dfb.png)


# 3. Membuat Model
## Selanjutnya adalah membuat Model untuk memproses data Artikel. Buat file baru pada direktori app/Models dengan nama ArtikelModel.php
![31](https://user-images.githubusercontent.com/101716660/176262033-643f4358-44ae-491c-bc9f-82d8e899239c.png)



# 4. Membuat Controller
## Buat Controller baru dengan nama Artikel.php pada direktori app/Controllers.
![70](https://user-images.githubusercontent.com/101716660/176262895-9cbdb739-8f75-4246-8b9f-7deff6ca463f.png)



# 5. Membuat View
## Buat direktori baru dengan nama artikel pada direktori app/views, kemudian buat file baru dengan nama index.php
![32](https://user-images.githubusercontent.com/101716660/176263003-5710aa13-0aa9-497b-9ca1-ca0646727f07.png)



## Selanjutnya buka browser kembali, dengan mengakses url http://localhost:8080/artikel
![33](https://user-images.githubusercontent.com/101716660/176263162-32806bdf-1856-4c90-876e-4839a3219442.png)


## jika Belum ada data yang diampilkan. Kemudian coba tambahkan beberapa data pada database agar dapat ditampilkan datanya.

![34](https://user-images.githubusercontent.com/101716660/176263396-fa95835f-4416-4a69-93fc-8e23cad01469.png)

## Refresh kembali browser, sehingga akan ditampilkan hasilnya.
![35](https://user-images.githubusercontent.com/101716660/176263509-25aca20c-6a7c-4fba-83e9-723e57ca108c.png)


# 6. Membuat Tampilan Detail Artikel
## Tampilan pada saat judul berita di klik maka akan diarahkan ke halaman yang berbeda. Tambahkan fungsi baru pada Controller Artikel dengan nama view().
![36](https://user-images.githubusercontent.com/101716660/176263687-a5eb8750-7048-4e2a-b780-3c725116a867.png)



# 7. Membuat View Detail
## Buat view baru untuk halaman detail dengan nama app/views/artikel/detail.php.
![37](https://user-images.githubusercontent.com/101716660/176263830-cabb0270-a487-4d13-876c-f00d02e6d13b.png)


# 8. Membuat Routing untuk artikel detail
## Buka Kembali file app/config/Routes.php, kemudian tambahkan routing untuk artikel detail.

![38](https://user-images.githubusercontent.com/101716660/176263928-bfe9d1da-939b-4888-9a88-bc71264efd72.png)


## Kemudian Refresh kembali
![39](https://user-images.githubusercontent.com/101716660/176264000-3ed74f56-70c0-4ece-a168-7676ea475290.png)


# 9. Membuat Menu Admin
## Menu admin adalah untuk proses CRUD data artikel. Buat method baru pada Controller Artikel dengan nama admin_index().
![40](https://user-images.githubusercontent.com/101716660/176264125-a245abf6-083c-455f-9960-0e737c6304c0.png)


## Selanjutnya buat view untuk tampilan admin dengan nama admin_index.php
![41](https://user-images.githubusercontent.com/101716660/176264189-24381dd0-33e4-46d3-9d28-b022060d0351.png)


## membuat file admin_header.php
![42](https://user-images.githubusercontent.com/101716660/176264339-dfd67d46-3c66-4df6-adbc-7826b89bd92e.png)


## Membuat file admin_footer.php
![44](https://user-images.githubusercontent.com/101716660/176264397-c32ba5ca-93f3-4f2f-b019-cb0b35d8f0aa.png)


## Membuat admin.css
![45](https://user-images.githubusercontent.com/101716660/176264490-dc140f39-4f7d-4346-8608-cdc787b1fea3.png)


## Refresh browser
![46 x](https://user-images.githubusercontent.com/101716660/176264829-572155b8-f3ed-495f-b42e-0778944337d6.png)


## Tambahkan routing untuk menu admin seperti berikut:
![47](https://user-images.githubusercontent.com/101716660/176264951-db2d87dd-2711-42ea-9d82-ff68341501f1.png)


## Akses menu admin dengan url http://localhost:8080/admin/artikel
![48](https://user-images.githubusercontent.com/101716660/176265207-a7846121-bda1-425f-a179-13f481af19f4.png)


# 10. Menambah Data Artikel
## Tambahkan fungsi/method baru pada Controller Artikel dengan nama add().
![49](https://user-images.githubusercontent.com/101716660/176265367-43cc1102-8c23-4a3c-a841-5c8085b2061b.png)


## Kemudian buat view untuk form tambah dengan nama form_add.php
![50](https://user-images.githubusercontent.com/101716660/176265446-8203482a-adda-41aa-8615-c18b419e5f1c.png)


## Setelah itu klik tambah artikel maka tampilan nya seperti berikut.
![51 x](https://user-images.githubusercontent.com/101716660/176265768-bfa0e7b2-17b2-45dc-924a-c951718554e7.png)


# 12. Mengubah Data
## Tambahkan fungsi/method baru pada Controller Artikel dengan nama edit().
![52](https://user-images.githubusercontent.com/101716660/176265829-236f1b7c-3df5-49b2-a537-66870ed4f4c7.png)


## Kemudian buat view untuk form tambah dengan nama form_edit.php
![53](https://user-images.githubusercontent.com/101716660/176265977-99658237-e2d7-4994-adb2-14ea2cdc6411.png)


## Hasil Browser
![54 x](https://user-images.githubusercontent.com/101716660/176266216-8aeec25c-3523-49c5-8cf6-be0bff93d2ad.png)


# 13. Menghapus Data
## Tambahkan fungsi/method baru pada Controller Artikel dengan nama delete().

![55](https://user-images.githubusercontent.com/101716660/176266328-e8c9b004-2b46-4488-bcfa-fd417de3b692.png)


# Praktikum 13 : FrameWork Lanjutan (Modul Login)
# 1. Membuat Tabel User
![56 x](https://user-images.githubusercontent.com/101716660/176266514-584b76fe-f28d-4614-9365-7a6eb57dbe0f.png)


# 2. Membuat Model User
## Selanjutnya adalah membuat Model untuk memproses data Login. Buat file baru pada direktori app/Models dengan nama UserModel.php
![57](https://user-images.githubusercontent.com/101716660/176266548-aaac1d2d-3f77-4e64-9af8-99990a66d02a.png)


# 3. Membuat Controller User
## Buat Controller baru dengan nama User.php pada direktori app/Controllers. Kemudian tambahkan method index() untuk menampilkan daftar user, dan method login() untuk proses login.
![58](https://user-images.githubusercontent.com/101716660/176266628-034b0ec2-b7a4-4d99-8264-b0749fa622d2.png)


# 4. Membuat View Login
## Buat direktori baru dengan nama user pada direktori app/views, kemudian buat file baru dengan nama login.php.
![59](https://user-images.githubusercontent.com/101716660/176266672-e133a7be-d692-43e1-901b-8f906a01a8c0.png)


# 5. Membuat Database Seeder
## Database seeder digunakan untuk membuat data dummy. Untuk keperluan ujicoba modul login, kita perlu memasukkan data user dan password kedaalam database. Untuk itu buat database seeder untuk tabel user. Buka CLI, kemudian tulis perintah berikut:
![60](https://user-images.githubusercontent.com/101716660/176266720-63322d74-7928-4ea7-ba1f-74ced6b6a928.png)


## Selanjutnya, buka file UserSeeder.php yang berada di lokasi direktori /app/Database/Seeds/UserSeeder.php kemudian isi dengan kode berikut:
![61](https://user-images.githubusercontent.com/101716660/176266756-6880e555-724d-4501-bb96-7f75ef47cd21.png)


## Selanjutnya buka kembali CLI dan ketik perintah berikut:
![62](https://user-images.githubusercontent.com/101716660/176266788-88603e4b-27a6-4bc7-bca2-0d089cb7301d.png)


## 6. Refresh Web
Selanjutnya buka url http://localhost:8080/user/login seperti berikut:
![63](https://user-images.githubusercontent.com/101716660/176266871-84c14cb9-b3cc-4577-95e3-c03a0afaf77f.png)


## 7. Menambahkan Auth Filter
Selanjutnya membuat filer untuk halaman admin. Buat file baru dengan nama Auth.php pada direktori app/Filters.
![64](https://user-images.githubusercontent.com/101716660/176266923-97b0ecdb-04eb-4dd1-bf71-0decd17122fd.png)


## Selanjutnya buka file app/Config/Filters.php tambahkan kode berikut:
![65](https://user-images.githubusercontent.com/101716660/176266993-17634066-e5d5-40f6-8c5b-1e7be63839eb.png)


## Selanjutnya buka file app/Config/Routes.php dan sesuaikan kodenya.
![66](https://user-images.githubusercontent.com/101716660/176267034-42d524fa-9889-4097-8060-5f3f1e6d6f2f.png)


## 8. Percobaan Akses Menu Admin
Buka url dengan alamat http://localhost:8080/user/login ketika alamat tersebut diakses maka, akan dimuculkan halaman login.
![67](https://user-images.githubusercontent.com/101716660/176267152-163f3902-6ddd-4b55-85dc-cc5569f8619f.png)


## 9. Fungsi Logout
Tambahkan method logout pada Controller User seperti berikut:
![68](https://user-images.githubusercontent.com/101716660/176267205-b4679d89-f3d4-47b9-865e-16272df2d5e4.png)
