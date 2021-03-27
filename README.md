# Mikrotik To Discord

Ini adalah script yang digunakan untuk mengirimkan Log Hotspot dan lain-lain yang ada di Mikrotik ke aplikasi gaming chat yang bernama Discord, Discord sendiri memiliki sebuah webhook yang mudah dipakai, kalian bisa melihat dokumentasinya [disini](https://discord.com/developers/docs/resources/webhook), sebenarnya script ini tidak hanya untuk di mikrotik saja, melainkan bisa dimana aja yang menggunakan webhook discord, karena kebetulan saya memiliki RT/RW NET di rumah yang menggunakan perangkat dari Mikrotik dan digunakan untuk memantau jaringan RT/RW NET saya seperti hotspot dan lain-lainnya yang awalnya menggunakan bot telegram untuk memantaunya tapi karena saya lebih sering menggunakan Discord dan juga sering bereksperimen jadi saya putuskan untuk membuat script ini, simak cara penggunaannya dibawah ya!

# Hal-hal yang harus dibutuhkan
| Butuh | Keterangan |
| --- | --- |
| Discord | Kalian harus memiliki sebuah discord server dimana kalian adalah ownernya, dan sudah di setup sedemikian rupa |
| Webhook Discord | Webhook Discord kalian juga harus sudah siap |
| Heroku | Ini adalah layanan cloud hosting untuk menaruh script ini secara online dan ini gratis dan juga ini hanyalah optional, kalian bisa menggunakan script yang sudah saya deploy ke heroku nanti |

# Discord
Disini saya beranggapan kalian sudah memiliki sebuah server discord dan untuk membuat discord webhook bisa kalian simak dibawah ini :

- Pertama kalian harus membuka **Server Settings** terlebih dahulu

![serversettings](https://cdn.discordapp.com/attachments/701452257102921738/825408588020842506/unknown.png)

- Kedua cari tab **Integrations** dan klik **Create Webhook**

![integrations](https://support.discord.com/hc/article_attachments/1500000463501/Screen_Shot_2020-12-15_at_4.41.53_PM.png)

- Ketiga pada saat membuat Webhook, kalian bebas mengaturnya sesuai kebutuhan kalian, yang harus diperhatikan adalah bagian **Channel** yang dimana itu akan digunakan sebagai tempat pesan dari webhook

![webhook](https://support.discord.com/hc/article_attachments/360101553853/Screen_Shot_2020-12-15_at_4.51.38_PM.png)

- Keempat yaitu **copy webhook url** simpan dulu urlnya buat next tutorial

![url](https://support.discord.com/hc/article_attachments/1500000455142/Screen_Shot_2020-12-15_at_4.45.52_PM.png)

# Heroku (Optional)
Pada bagian ini jika kalian tertarik untuk hosting script ini, kalian bisa mengikuti tutorial ini, oh ya script ini bisa kalian hosting selain heroku, mungkin bisa diserver kalian masing-masing jika sudah punya

- Pertama kalian cukup fork terlebih dahulu repository ini menggunakan akun GitHub kalian sendiri
- Kedua kalian login ke Heroku yang sudah linked dengan akun github kalian
- Ketiga kalian klik tombol `New` untuk membuat apps baru, kemudian bebas diisi apa. Untuk server kalian hanya diberikan 2 pilihan yaitu US dan EU, saran sih pakai US saja lalu klik `Create app`
- Keempat setelah menekan tombol tadi, kalian akan diarahkan ke dashboard apps kalian, nah silahkan cari `Deploment method` disana terdapat pilihan `Heroku CLI` , `GitHub` dan `Container Registry` nah kalian tinggal tekan `GitHub`
- Kelima disana kalian harus mengisi repository name yang tadi kalian fork, silahkan isi repository name nya sesuai dengan yang kalian fork tadi lalu klik `Search`
- Keenam nanti akan muncul repository nya dan kalian cukup klik `Connect` tunggu hingga muncul opsi paling bawah cari dan klik `Deploy to branch`
- Ketujuh tunggu hingga proses selesai dan berisikan tulisan `Your app was successfully deployed.` pada tombol View disana itulah yang akan jadi url scripts ini nanti

Simpan url tersebut (contoh https://namaprojectkalian.herokuapp.com) untuk next tutorial

# Mikrotik
Disini saya akan menjelaskannya secara singkat, dimana kalian cukup menambahkan code ini disetiap `mikrotik scripts` kalian

```java
/tool fetch url="https://namaprojectkalian.herokuapps.com/form.php?text=MASUKIN_TEXT_KALIAN&id=MASUKAN_ID_WEBHOOK&token=MASUKKAN_TOKEN_WEBHOOK" keep-result=no;
```
Keterangan :
- pada bagian url itu adalah url dari apps yang sudah kalian deploy ke heroku tadi
- pada bagian `MASUKIN_TEXT_KALIAN` kalian bebas mengisi apa aja sesuai kebutuhan, untuk spasi wajib gunakan tanda `+` contoh (SAYA+GILA+SEKALI)
- pada bagian `MASUKAN_ID_WEBHOOK` gunakanlah ID WEBHOOK yang kalian simpan tadi
- pada bagian `MASUKAN_TOKEN_WEBHOOK` gunakanlah TOKEN WEBHOOK yang kalian simpan tadi

Keterangan URL Webhook Discord yang kalian simpan tadi :
`https://discord.com/api/webhooks/7939909737777777/REl22gJR5WIp0I7BwCiMu2UPHG3_jXMNPddddddddddddddddna9EmmW39buWI3`
- Pada bagian angka `7939909737777777` itu adalah `id` kalian
- Pada bagian terakhir `REl22gJR5WIp0I7BwCiMu2UPHG3_jXMNPddddddddddddddddna9EmmW39buWI3` itu adalah `token` kalian

### Contoh penggunaan pada mikrotik netwatch
## Settingan pada netwatch Up
![image](https://user-images.githubusercontent.com/10250068/112728650-4067a280-8f63-11eb-8945-da7d2cec3184.png)
## Hasilnya
![image](https://user-images.githubusercontent.com/10250068/112728601-10200400-8f63-11eb-95cd-1378b27458c0.png)

