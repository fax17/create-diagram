```mermaid
flowchart LR
    A[Data] --> B[Ekplorasi Data menggunakan Boxplot]
    B --> C[Pemeriksaan Keragaman Spatio-temporal dengan Chloropleth Map]
    C --> D[Uji Heterogenitas Spasial dan Temporal dengan Breusch-Pagan Test]
    D --> E{Heteroskedastisitas?}
    E -->|Ya| F[Pemodelan Spasio-Temporal]
    E -->|Tidak| G[Uji Pengaruh Spesifik Individu dan Waktu]
    G --> H{Pengaruh Spesifik?}
    H -->|Ya| F
    H -->|Tidak| I[Model Global]
    
    F --> F1[Menentukan parameter rasio spasio-temporal]
    F1 --> F2[Menetapkan fungsi pembobot spasio-temporal]
    F2 --> F3[Menghitung parameter estimasi]
    
    F --> G1[Menentukan parameter rasio spasial-temporal (GTWNN)]
    G1 --> G2[Inisialisasi parameter jaringan neural]
    G2 --> G3[Mendefinisikan arsitektur jaringan neural]
    G3 --> G4[Menghitung kontribusi lokal dalam pembelajaran neural network]
    G4 --> G5[Menggunakan fungsi loss untuk optimasi jaringan neural]
    G5 --> G6[Menghitung parameter estimasi]

    F3 --> J[Membandingkan Model GTWR dengan GTWNN dan Regresi Global]
    G6 --> J

    J --> K[Visualisasi dan Penarikan Kesimpulan]
    
    classDef step fill:#fff,stroke:#333,stroke-width:2px;
    class A,B,C,D,E,F,G,H,I,F1,F2,F3,G1,G2,G3,G4,G5,G6,J,K step;
