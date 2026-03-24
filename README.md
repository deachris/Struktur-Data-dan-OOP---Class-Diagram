# Struktur-Data-dan-OOP---Class-Diagram

## Sistem Manajemen Event
### Deskripsi Kasus:
Pada saat ini, terdapat banyak jenis hiburan yang diminati banyak orang sebagai tempat untuk beristirahat sejenak dari kesibukan dunia. Jenis hiburan tersebut mencakup konser, festival, maupun fanmeeting yang saat ini semakin diminati kalangan muda. Dalam sebuah event, terdapat hal-hal yang penting untuk dikelola, seperti informasi event (nama, tanggal, lokasi), pembelian tiket, dan notifikasi status pembayaran. Untuk itu, Sistem Manajemen Event ini sangat penting digunakan dalam mengelola event tersebut.
OOP dapat:
1. Menyimpan informasi setiap event: nama, tanggal pelaksanaan, lokasi, kapasitas.
2. Memberitahu memngenai informasi harga tiket berdasarkan kategori VIP dan reguler.
3. Memberikan notifikasi untuk aktivitas pembayaran dan lokasi event.

### Class Diagram


    classDiagram
    direction TB
      class Event {
	    #nama : String
	    #tanggal : String
	    #lokasi : String
	    -kapasitas : int
	    +Event(nama: String, tanggal: String, lokasi : String, kapasitas: int)
	    +tampilTiket(infoTiket: String) void
	    +notif(pesan: String) void
    }

     class Konser {
      #penyanyi : String
	    +Konser(nama: String, tanggal: String, lokasi: String, kapasitas: int)
	    +tampilInfo() void
    }

    class Festival {
      #jenis : String
      +Festival(nama: String, tanggal: String, lokasi: String, kapasitas: int)
      +tampilInfo() void
    }

    class FanMeeting {
      #artis : String
      +FanMeeting(nama: String, tanggal: String, lokasi: String, kapasitas: int)
      +tampilInfo() void
    }
    class Tiket {
	    +tampilTiket(infoTiket: String) void
    }

    class Notifikasi {
	    +notif(pesan: String) void
    }

    class TiketVIP {
	    +tampilTiket(infoTiket: String) void
    }

    class TiketReguler {
	    +tampilTiket(infoTiket: String) void
    }

    class NotifikasiPembayaran {
	    +notif(pesan: String) void
    }

    class NotifikasiLokasi {
	    +notif(pesan: String) void
    }

	<<Abstract>> Event
	<<Interface>> Tiket
	<<Interface>> Notifikasi

    Event <|-- Konser
    Event <|-- Festival
    Event <|-- FanMeeting
    Event "--> Tiket : menggunakan
    Event --> Notifikasi : menggunakan
    Tiket <|.. TiketVIP
    Tiket <|.. TiketReguler
    Notifikasi <|.. NotifikasiPembayaran
    Notifikasi <|.. NotifikasiLokasi


