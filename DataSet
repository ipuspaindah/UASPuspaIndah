#include <iostream>
#include <vector>
#include <algorithm>
#include <cctype>  // Untuk fungsi isspace dan trim

using namespace std;

// Struktur untuk menyimpan data item fashion
struct FashionItem {
    string name;
    string category;
    double price;
    
    // Konstruktor untuk menginisialisasi FashionItem
    FashionItem(string n, string c, double p) : name(n), category(c), price(p) {}
};

// Fungsi untuk mengurutkan dataset berdasarkan nama
bool compareByName(const FashionItem& a, const FashionItem& b) {
    return a.name < b.name;
}

// Fungsi Binary Search untuk mencari item berdasarkan nama
int binarySearch(const vector<FashionItem>& data, const string& target) {
    int low = 0;
    int high = data.size() - 1;
    
    while (low <= high) {
        int mid = (low + high) / 2;
        if (data[mid].name == target) {
            return mid;  // Ditemukan
        } else if (data[mid].name < target) {
            low = mid + 1;
        } else {
            high = mid - 1;
        }
    }
    return -1;  // Tidak ditemukan
}

// Fungsi untuk menghapus spasi di awal dan akhir string
string trim(const string& str) {
    size_t first = str.find_first_not_of(' ');
    if (first == string::npos) return ""; // Jika hanya spasi
    size_t last = str.find_last_not_of(' ');
    return str.substr(first, (last - first + 1));
}

int main() {
	// Menampilkan Nama dan NIM
    cout << "Nama: Puspa Indah Maya Dewi\n";
    cout << "NIM: 241011400837\n\n";

    // Dataset fashion terurut berdasarkan nama
    vector<FashionItem> fashionItems;

    // Menambahkan elemen menggunakan konstruktor
    fashionItems.push_back(FashionItem("Dress Floral", "Dress", 49.99));
    fashionItems.push_back(FashionItem("Leather Jacket", "Outerwear", 99.99));
    fashionItems.push_back(FashionItem("Sneakers White", "Shoes", 59.99));
    fashionItems.push_back(FashionItem("T-shirt Graphic", "T-shirt", 19.99));
    fashionItems.push_back(FashionItem("Wool Scarf", "Accessories", 29.99));

    // Mengurutkan dataset berdasarkan nama item
    sort(fashionItems.begin(), fashionItems.end(), compareByName);

    // Menampilkan dataset yang sudah terurut
    cout << "Dataset Fashion Terurut:\n";
    for (size_t i = 0; i < fashionItems.size(); ++i) {
        cout << "Nama: " << fashionItems[i].name << ", Kategori: " 
             << fashionItems[i].category << ", Harga: $" << fashionItems[i].price << endl;
    }

    // Input nama item yang ingin dicari
    string target;
    cout << "\nMasukkan nama item fashion yang ingin dicari: ";
    getline(cin, target);
    target = trim(target); // Menghapus spasi ekstra dari input

    // Mencari item dengan Binary Search
    int result = binarySearch(fashionItems, target);
    
    if (result != -1) {
        cout << "Item '" << target << "' ditemukan!\n";
        cout << "Kategori: " << fashionItems[result].category << ", Harga: $" << fashionItems[result].price << endl;
    } else {
        cout << "Item '" << target << "' tidak ditemukan dalam dataset.\n";
    }

    return 0;
}
