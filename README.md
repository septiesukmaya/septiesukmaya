- 👋 Hi, I’m @septiesukmaya
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
septiesukmaya/septiesukmaya is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
// Kelompok 3D  : 
// Apriyan Fillah Ginansyah 065121109 
// Habib Fiman Choiri       065121114
// Vindi Muthia Salsabila   065121106
// Mutiara Shakila          065121094
// Septie Sukmaya           065121108


#include <iostream> /* merupakan header utama yaitu iosteream -> file yang terdapat dalam sistem komputer */

using namespace std; /* agar tidak memakai std berulang pada setiap fungsi */

struct Booking /* merupakan tipe data */
{ /* anggota dari struct yakni char nama, char tgl, int jml, int menu, int tot dan int lama */
    char nama[10][10], tgl[10][10];
    int jml, menu, tot, lama[10];
    string jam[10];
} book; /* untuk mengidentifikasi variabel dari anggota struct */

void header() /* memakai fungsi void karena tidak mengembalikan nilai */
{
    cout << "==================================================" << endl;
    cout << "|       PROGRAM PENYEWAAN LAPANGAN BASKET        |" << endl;
    cout << "==================================================" << endl;
}

int main() /* merupakan program utama dari source code ini */
{
    header();
    cout << "Masukkan jumlah pembooking             : ";
    cin >> book.jml; /* memasukkan jumlah pembooking kedalam variabel book.jml agar masuk kedalam struct */
    cout << endl;

    for (int i = 0; i < book.jml; i++) /* merupakan bentuk perulangan dengan komposisi:
    inisialisasi variabel / kondisi variabel / update variabel -> inisialisasi yakni nilai awal dari variabel tsb.,
    kondisi yakni pengujian bahwa perulangan akan terus dilakukan selama kondisi bernilai true,
    update yakni instruksi untuk mengubah nilai variabel agar membatasi perulangan sehingga akan selessai suatu saat */
    {
        cout << "Masukkan nama                          : ";
        cin >> book.nama[i];
        cout << "Masukkan lama penyewaan                : ";
        cin >> book.lama[i];
        cout << "Masukkan tanggal penyewaan (dd/mm/yy)  : ";
        cin >> book.tgl[i];
        cout << "Masukkan Jam Penyewaan                 : ";
        cin >> book.jam[i];
        cout << endl;
    }

    cout << endl;
    header();
    cout << "1. Lihat daftar pembooking" << endl;
    cout << "2. Keluar" << endl;
    cout << "Pilih Menu : ";
    cin >> book.menu;
    if (book.menu == 1)
    {
        for (int j = 0; j < book.jml; j++)
        {
            cout << "==================================================" << endl;
            cout << "---------||   ***RESERVATION SLIP***   ||---------" << endl;
            cout << "==================================================" << endl;
            cout << "Nama pembooking  : " << book.nama[j] << endl;
            cout << "Lama penyewaan   : " << book.lama[j] << " jam" <<endl;
            cout << "Tanggal sewa     : " << book.tgl[j] <<endl;
            book.tot = 75000 * book.lama[j];
            cout << "Jam Sewa         : " << book.jam[j] <<endl;
            cout << "Biaya sewa       : " << book.tot <<  endl;
        }
    }
    else if (book.menu == 2)
    {
        exit(0);
    }
    else
    {
        cout << "Menu tidak ada!";
    }
}
