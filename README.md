```mermaid
flowchart LR
    A[Data] --> B[Ekplorasi Data menggunakan Boxplot]
    B --> C[Pemeriksaan Keragaman Spatio-temporal dengan Chloropleth Map]
    C --> D[Uji Heterogenitas Spasial dan Temporal dengan Breusch-Pagan Test]
    D --> E{Heteroskedastisitas?}
    E -->|Ya| F[Pemodelan Spasio-Temporal dengan GTWR dan GTWNN]
    E -->|Tidak| G[Uji Pengaruh Spesifik Individu dan Waktu]
    G --> H{Pengaruh Spesifik?}
    H -->|Ya| F
    H -->|Tidak| I[Model Global]
    
    subgraph Pemodelan Spasio-Temporal
        direction TB
        F1[Menentukan parameter rasio spasio-temporal]
        F2[Menetapkan fungsi pembobot spasio-temporal]
        F3[Menghitung parameter estimasi]
    end
    
    subgraph GTWNN
        direction TB
        G1[Menentukan parameter rasio spasial-temporal]
        G2[Inisialisasi parameter jaringan neural]
        G3[Mendefinisikan arsitektur jaringan neural]
        G4[Menghitung kontribusi lokal dalam pembelajaran neural network]
        G5[Menggunakan fungsi loss untuk optimasi jaringan neural]
        G6[Menghitung parameter estimasi]
    end
    
    F --> Pemodelan Spasio-Temporal
    Pemodelan Spasio-Temporal --> GTWNN
    GTWNN --> J[Membandingkan Model GTWR dengan GTWNN dan Regresi Global]
    J --> K[Visualisasi dan Penarikan Kesimpulan]
    
    classDef step fill:#fff,stroke:#333,stroke-width:2px;
    class A,B,C,D,E,F,G,H,I,F1,F2,F3,G1,G2,G3,G4,G5,G6,J,K step;
