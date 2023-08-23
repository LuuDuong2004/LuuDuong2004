#include <iostream>
#include <string>

using namespace std;

struct NhanVien {
    string id, name, gender, dob, address, tax, date;
};

void nhap(NhanVien& a) {
    cin.ignore();
    getline(cin, a.name); cin.ignore();
    getline(cin, a.gender); cin.ignore();
    getline(cin, a.dob); cin.ignore();
    getline(cin, a.address); cin.ignore();
    getline(cin, a.tax); cin.ignore();
    getline(cin, a.date); cin.ignore();
}

string STT(int i) {
    string r = to_string(i);
    while (r.length() < 5)
        r = '0' + r;
    return r;
}

void inds(NhanVien ds[], int n) {
    for (int i = 0; i < n; i++) {
        cout << STT(i + 1) << " ";
        cout << ds[i].name << " " << ds[i].gender << " " << ds[i].dob << " " << ds[i].address << " " << ds[i].tax << " " << ds[i].date << endl;
    }
}


int main() {
    struct NhanVien ds[50];
    int N, i;
    cin >> N; cin.ignore();
    for (i = 0; i < N; i++) nhap(ds[i]);
    inds(ds, N);
    return 0;
}
