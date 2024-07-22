```mermaid
flowchart TD
    A[Data] --> B[Ekplorasi Data menggunakan Boxplot]
    B --> C[Pemeriksaan Keragaman Spatio-temporal dengan Chloropleth Map]
    C --> D[Uji Heterogenitas Spasial dan Temporal dengan Breusch-Pagan Test]
    D --> E{Heteroskedastisitas?}
    E -->|Ya| F[Pemodelan Spasio-Temporal]
    E -->|Tidak| G[Uji Pengaruh Spesifik Individu dan Waktu]
    G --> H{Pengaruh Spesifik?}
    H -->|Ya| F
    H -->|Tidak| I[Model Global]
    
    subgraph Pemodelan Spasio-Temporal
        F1[GTWR]
        F2[GTWNN]
        F1 --> F3[Menentukan parameter rasio spasio-temporal]
        F3 --> F4[Menetapkan fungsi pembobot spasio-temporal]
        F4 --> F5[Menghitung parameter estimasi]
        
        F2 --> G1[Menentukan parameter rasio spasio-temporal]
        G1 --> G2[Inisialisasi parameter jaringan neural]
        G2 --> G3[Mendefinisikan arsitektur jaringan neural]
        G3 --> G4[Menghitung kontribusi lokal dalam pembelajaran neural network]
        G4 --> G5[Menggunakan fungsi loss untuk optimasi jaringan neural]
        G5 --> G6[Menghitung parameter estimasi]
    end
    
    F --> J[Membandingkan Model GTWR dengan GTWNN dan Regresi Global]
    J --> K[Visualisasi dan Penarikan Kesimpulan]
    
    classDef step fill:#fff,stroke:#333,stroke-width:2px;
    class A,B,C,D,E,F,G,H,I,F1,F2,F3,F4,F5,G1,G2,G3,G4,G5,G6,J,K step;
