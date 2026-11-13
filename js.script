
const data = [
    {
        name: "Motherboard",
        icon: "▦",
        label: "MAIN CIRCUIT BOARD",
        description: "Motherboard adalah papan sirkuit utama yang menjadi tempat terhubungnya berbagai komponen komputer. Komponen ini memungkinkan seluruh bagian komputer saling berkomunikasi dan bekerja sebagai satu sistem.",
        functions: [
            "Menghubungkan CPU, RAM, GPU, dan SSD.",
            "Menyediakan jalur komunikasi antar komponen.",
            "Menyalurkan daya ke berbagai bagian komputer.",
            "Menyediakan port dan konektor untuk perangkat tambahan."
        ]
    },
    {
        name: "CPU",
        icon: "▣",
        label: "CENTRAL PROCESSING UNIT",
        description: "CPU (Central Processing Unit) adalah unit pemrosesan utama yang sering disebut sebagai otak komputer. CPU bertugas menjalankan instruksi program, melakukan perhitungan, dan mengatur proses kerja komputer.",
        functions: [
            "Memproses instruksi dari program.",
            "Melakukan operasi matematika dan logika.",
            "Mengatur jalannya berbagai proses komputer.",
            "Mengontrol koordinasi kerja komponen lainnya."
        ]
    },
    {
        name: "RAM",
        icon: "▤",
        label: "RANDOM ACCESS MEMORY",
        description: "RAM (Random Access Memory) merupakan memori sementara yang menyimpan data dan instruksi yang sedang digunakan oleh komputer. RAM membantu CPU mengakses informasi dengan cepat saat menjalankan aplikasi.",
        functions: [
            "Menyimpan data sementara saat komputer bekerja.",
            "Mempercepat akses data yang sedang digunakan.",
            "Mendukung multitasking atau penggunaan banyak aplikasi.",
            "Mengurangi kebutuhan mengambil data langsung dari SSD."
        ]
    },
    {
        name: "SSD",
        icon: "▤",
        label: "SOLID STATE DRIVE",
        description: "SSD (Solid State Drive) adalah perangkat penyimpanan data yang menggunakan memori flash dan tidak memiliki komponen mekanis yang bergerak. SSD digunakan untuk menyimpan sistem operasi, aplikasi, dan berbagai file.",
        functions: [
            "Menyimpan sistem operasi dan aplikasi.",
            "Menyimpan dokumen, foto, dan video.",
            "Mempercepat proses booting komputer.",
            "Mempercepat proses membuka dan memuat aplikasi."
        ]
    },
    {
        name: "GPU",
        icon: "▧",
        label: "GRAPHICS PROCESSING UNIT",
        description: "GPU (Graphics Processing Unit) adalah komponen yang bertugas memproses dan menghasilkan tampilan grafis. GPU membantu komputer menampilkan gambar, video, animasi, serta menjalankan aplikasi dengan kebutuhan grafis tinggi.",
        functions: [
            "Mengolah dan merender gambar serta video.",
            "Membantu menjalankan game dan aplikasi grafis.",
            "Memproses visualisasi dan animasi 3D.",
            "Mempercepat komputasi paralel pada pekerjaan tertentu."
        ]
    }
];

let current = 0;

const buttons = document.getElementById("buttons");

function createButtons() {
    buttons.innerHTML = "";

    data.forEach((item, index) => {
        const btn = document.createElement("button");
        btn.className = "component-btn";

        btn.innerHTML = `
            <span class="symbol">${item.icon}</span>
            <strong>${item.name}</strong>
        `;

        btn.addEventListener("click", () => {
            showComponent(index);
        });

        buttons.appendChild(btn);
    });
}

function showComponent(index) {
    current = index;

    const item = data[current];

    document.getElementById("visualIcon").textContent = item.icon;
    document.getElementById("visualLabel").textContent = item.label;
    document.getElementById("number").textContent =
        `COMPONENT 0${current + 1} / 05`;

    document.getElementById("title").textContent = item.name;
    document.getElementById("description").textContent =
        item.description;

    const list = document.getElementById("functions");
    list.innerHTML = "";

    item.functions.forEach(func => {
        const li = document.createElement("li");
        li.textContent = func;
        list.appendChild(li);
    });

    document.querySelectorAll(".component-btn").forEach((btn, i) => {
        btn.classList.toggle("active", i === current);
    });

    document.getElementById("progress").style.width =
        ((current + 1) / data.length * 100) + "%";

    document.getElementById("prev").disabled = current === 0;
    document.getElementById("next").disabled =
        current === data.length - 1;
}

document.getElementById("prev").addEventListener("click", () => {
    if (current > 0) showComponent(current - 1);
});

document.getElementById("next").addEventListener("click", () => {
    if (current < data.length - 1) showComponent(current + 1);
});

createButtons();
showComponent(0);
