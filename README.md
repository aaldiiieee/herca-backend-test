# Marketing Commission API

Repository ini merupakan jawaban dari soal terkait perhitungan komisi marketing berdasarkan omzet bulanan serta implementasi API untuk pembayaran secara kredit.

---

## **Fitur**

### **Backend API**
1. Menampilkan data komisi marketing berdasarkan omzet bulanan:
   - Perhitungan sesuai ketentuan persentase komisi dari omzet.
2. Melakukan pembayaran kredit:
   - Simpan data pembayaran ke dalam tabel pembayaran.
   - Mengurangi sisa kredit setelah pembayaran.

### **Frontend**
- Menampilkan tabel hasil perhitungan komisi marketing.
- Fitur input dan visualisasi pembayaran kredit.

---

## **Backend**

### **1. Struktur Database**

#### **Table: Marketing**
| id | name    |
|----|---------|
| 1  | Alfandy |
| 2  | Mery    |
| 3  | Danang  |

#### **Table: Penjualan**
| id  | transaction_number | marketing_id | date       | cargo_fee | total_balance | grand_total |
|-----|---------------------|--------------|------------|-----------|---------------|-------------|
| 1   | TRX001             | 1            | 2023-05-22 | 25000     | 3000000       | 3025000     |

#### **Table: Pembayaran**
| id  | transaction_id | amount  | payment_date |
|-----|----------------|---------|--------------|
| 1   | 1              | 1000000 | 2023-06-01   |

---

### **2. API Endpoint**

#### **Endpoint 1: Get Marketing Commission**
- **Method**: `GET`
- **URL**: `/api/commission/get-commission-by-month`
- **Response**:
```json
[
  {
    "marketing": "Alfandy",
    "month": "Mei",
    "omzet": 138000000,
    "commission_percentage": 2.5,
    "commission_nominal": 3450000
  }
]
```

#### **Endpoint 2: Create Payment**
- **Method**: `POST`
- **URL**: `/api/payment/make-payment`
- **Body**:
```json
{
  "transaction_id": 1,
  "amount": 1000000
}
```
- **Response**:
```json
{
  "message": "Payment recorded successfully",
  "remaining_credit": 2025000
}
```

---

### **3. Instalasi Backend**

#### **Step 1: Clone Repository**
```bash
git clone https://github.com/username/marketing-commission-api.git
cd marketing-commission-api/backend
```

#### **Step 2: Install Dependencies**
```bash
npm install
```

#### **Step 3: Start Server**
```bash
npm start
```
Server akan berjalan di `http://localhost:5000`.

---

## **Postman Collection**
Postman collection tersedia dalam file `HercaCollection.postman_collection.json` di root folder.

### Cara Import:
1. Buka Postman.
2. Klik tombol **Import**.
3. Pilih file `HercaCollection.postman_collection.json`.
4. Koleksi siap digunakan.
