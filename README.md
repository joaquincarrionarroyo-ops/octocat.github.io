<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CompraCity | Inteligencia de Mercado 2026</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;600;800&display=swap');
        body { font-family: 'Plus Jakarta Sans', sans-serif; background-color: #ffffff; color: #1d1d1f; scroll-behavior: smooth; }
        .glass-nav { background: rgba(255, 255, 255, 0.9); backdrop-filter: blur(10px); border-bottom: 1px solid #eee; }
        .product-card { background: #f5f5f7; border-radius: 24px; border: 1px solid transparent; transition: 0.3s; display: flex; flex-direction: column; height: 100%; overflow: hidden; }
        .product-card:hover { border-color: #0071e3; background: #fff; transform: translateY(-4px); box-shadow: 0 10px 30px rgba(0,0,0,0.05); }
        .img-box { height: 140px; background: #fff; display: flex; align-items: center; justify-content: center; font-size: 40px; color: #d2d2d7; }
        
        /* Colores de Marca */
        .badge-ml { background: #fff159; color: #000; }
        .badge-fravega { background: #4b0082; color: #fff; }
        .badge-musimundo { background: #e30613; color: #fff; }
        .badge-oncity { background: #00aeef; color: #fff; }
        .badge-compumundo { background: #808080; color: #fff; }
        
        .no-stock { color: #ff3b30; font-weight: 800; font-size: 8px; }
        .alt-label { font-size: 7px; color: #86868b; display: block; line-height: 1.1; margin-top: 2px; font-weight: 600; }
        section { padding: 80px 24px; }
    </style>
</head>
<body class="pt-20">

    <nav class="fixed top-0 w-full z-50 glass-nav px-6 md:px-10 py-4 flex flex-col md:flex-row justify-between items-center gap-4">
        <div class="flex items-center gap-2">
            <div class="w-8 h-8 bg-black rounded-lg flex items-center justify-center shadow-md"><i class="fa-solid fa-bolt text-white text-xs"></i></div>
            <span class="text-xl font-extrabold tracking-tighter uppercase">Compra<span class="text-blue-600">City</span></span>
        </div>
        <input type="text" id="searchInput" placeholder="Buscá en el radar de 42 productos..." class="bg-gray-100 px-6 py-2 rounded-full w-full max-w-lg outline-none border focus:border-blue-500 transition text-sm">
        <div class="hidden lg:flex gap-6 text-[10px] font-bold text-gray-400 uppercase tracking-widest italic">
            <a href="#radar" class="hover:text-black">Radar</a>
            <a href="#nosotros" class="hover:text-black">Nosotros</a>
            <a href="#faq" class="hover:text-black">Ayuda</a>
            <a href="#legales" class="hover:text-black">Legales</a>
        </div>
    </nav>

    <header class="pt-32 pb-16 px-10 text-center bg-gray-50">
        <span class="text-blue-600 font-extrabold text-[10px] uppercase tracking-[0.3em] mb-4 block italic">Radar Multi-Retailer v4.0</span>
        <h1 class="text-5xl md:text-7xl font-black tracking-tighter leading-tight mb-6 uppercase">Transparencia <br><span class="text-gray-400">en cada precio.</span></h1>
        <p class="text-gray-500 font-medium max-w-2xl mx-auto italic leading-relaxed text-lg">
            Comparamos las 5 tiendas más grandes de Argentina contra el polo productivo. Si no hay stock exacto, buscamos la alternativa más fiel para que siempre sepas dónde ahorrar.
        </p>
    </header>

    <section id="radar" class="max-w-[1700px] mx-auto">
        <div class="flex justify-between items-end mb-10 border-b pb-6">
            <h2 class="text-3xl font-black tracking-tighter uppercase italic">Radar de Mercado</h2>
            <div class="text-[10px] font-black text-gray-400" id="counter">Cargando...</div>
        </div>
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 xl:grid-cols-5 gap-6" id="radarGrid"></div>
    </section>

    <section id="nosotros" class="bg-gray-900 text-white">
        <div class="max-w-4xl mx-auto text-center">
            <h2 class="text-3xl font-black mb-8 italic uppercase tracking-tighter">Nosotros no vendemos, <span class="text-blue-500">analizamos.</span></h2>
            <p class="text-gray-400 leading-relaxed text-lg mb-12">
                CompraCity nació para democratizar el acceso a los beneficios del régimen industrial. Somos una plataforma de inteligencia que rastrea inventarios en tiempo real para conectar al consumidor final con la mejor oferta posible. 
            </p>
            
            <div class="bg-gray-800 p-8 rounded-3xl border border-gray-700 text-left mb-12">
                <h3 class="text-blue-500 font-black uppercase text-sm mb-4 tracking-widest italic">¿Por qué comparamos alternativas?</h3>
                <p class="text-gray-300 text-sm leading-relaxed italic">
                    Nuestro compromiso es darte una opción de compra real. Cuando un retailer no dispone del modelo exacto (ej. color específico o capacidad base), nuestro algoritmo selecciona el <strong>producto más similar</strong> disponible en su catálogo. <br><br>
                    Si ves una etiqueta de <strong>"Alt:"</strong> bajo el precio, te estamos indicando que ese valor corresponde a una variante (otro color, pack o modelo gemelo) para que no pierdas la oportunidad de comparar el precio de esa tienda frente a las demás.
                </p>
            </div>

            <div class="grid grid-cols-2 md:grid-cols-4 gap-8">
                <div><p class="text-3xl font-black text-blue-500 tracking-tighter">42</p><p class="text-[9px] font-bold uppercase text-gray-600 tracking-widest">Productos Pro</p></div>
                <div><p class="text-3xl font-black text-blue-500 tracking-tighter">5</p><p class="text-[9px] font-bold uppercase text-gray-600 tracking-widest">Tiendas Líderes</p></div>
                <div><p class="text-3xl font-black text-blue-500 tracking-tighter">24/7</p><p class="text-[9px] font-bold uppercase text-gray-600 tracking-widest">Radar Activo</p></div>
                <div><p class="text-3xl font-black text-blue-500 tracking-tighter">0%</p><p class="text-[9px] font-bold uppercase text-gray-600 tracking-widest">Comisiones</p></div>
            </div>
        </div>
    </section>

    <section id="faq" class="max-w-5xl mx-auto">
        <h2 class="text-3xl font-black mb-12 text-center uppercase tracking-tighter italic underline decoration-blue-600 decoration-4 underline-offset-8">Centro de Ayuda</h2>
        <div class="grid md:grid-cols-2 gap-8">
            <div class="product-card p-8">
                <h4 class="font-bold mb-3 uppercase text-xs tracking-widest">¿Qué es el precio de "Alternativa"?</h4>
                <p class="text-gray-500 text-xs italic">Si un retailer no tiene stock del modelo exacto (ej: S25 Navy 256GB), nuestro sistema busca el modelo más cercano disponible (ej: S25 Silver 256GB) para que la comparativa de mercado sea justa y actualizada.</p>
            </div>
            <div class="product-card p-8">
                <h4 class="font-bold mb-3 uppercase text-xs tracking-widest">¿El envío está incluido?</h4>
                <p class="text-gray-500 text-xs italic">Los precios mostrados corresponden al valor del producto en plataforma. Los costos de envío dependen de la logística de cada tienda (Courier TDF, Newsan Logistics o Mercado Envíos).</p>
            </div>
        </div>
    </section>

    <section id="legales" class="bg-gray-50 border-t border-gray-200">
        <div class="max-w-4xl mx-auto">
            <h2 class="text-xs font-black mb-6 uppercase tracking-[0.4em] text-gray-400">Aspectos Legales y Transparencia</h2>
            <div class="text-[10px] text-gray-400 leading-loose space-y-4 font-medium uppercase text-justify">
                <p>1. CompraCity funciona exclusivamente como un agregador de información de precios públicos. No procesamos pagos ni gestionamos envíos de forma directa.</p>
                <p>2. Los beneficios impositivos mencionados están amparados bajo la Ley 19.640 de Tierra del Fuego. El usuario final es responsable de verificar los términos y condiciones de garantía de cada fabricante.</p>
                <p>3. Todos los logos y marcas mencionadas (Frávega, Mercado Libre, Musimundo, OnCity, Compumundo) son propiedad de sus respectivos dueños y se utilizan aquí con fines meramente comparativos e informativos.</p>
            </div>
        </div>
    </section>

    <footer class="py-12 text-center text-gray-300 text-[10px] font-bold uppercase tracking-[0.3em]">
        CompraCity 2026 • Buenos Aires / Tierra del Fuego
    </footer>

    <script>
        const icons = { "Celular": "fa-mobile-screen", "Notebook": "fa-laptop", "Lavarropas": "fa-soap", "Heladera": "fa-refrigerator", "Aire": "fa-wind", "Microondas": "fa-mound", "Ventilador": "fa-fan", "Auricular": "fa-headphones" };

        const products = [
            // 10 CELULARES
            { name: "Samsung Galaxy S25+ Navy", cat: "Celular", prices: { "ML": {p: 2113125}, "Frávega": {p: 2689999}, "Musimundo": {p: 2645000}, "OnCity": {p: 2710000}, "Compumundo": {p: 2750000, alt: "Color Mint"} } },
            { name: "Motorola Edge 50 Pro", cat: "Celular", prices: { "ML": {p: 999999}, "Frávega": {p: 1050000}, "Musimundo": {p: null}, "OnCity": {p: 1100000}, "Compumundo": {p: 1080000, alt: "Edge 50 Fusion"} } },
            { name: "iPhone 15 128GB Black", cat: "Celular", prices: { "ML": {p: 1850000}, "Frávega": {p: 1950000, alt: "Blue"}, "Musimundo": {p: 2050000}, "OnCity": {p: null}, "Compumundo": {p: 2100000} } },
            { name: "Galaxy A55 5G 256GB", cat: "Celular", prices: { "ML": {p: 850000}, "Frávega": {p: 799000}, "Musimundo": {p: 830000}, "OnCity": {p: 820000}, "Compumundo": {p: 810000} } },
            { name: "Moto G85 5G Cobalt", cat: "Celular", prices: { "ML": {p: 450000}, "Frávega": {p: 425000}, "Musimundo": {p: 430000}, "OnCity": {p: 445000}, "Compumundo": {p: null} } },
            { name: "Xiaomi Redmi Note 13", cat: "Celular", prices: { "ML": {p: 480000}, "Frávega": {p: 520000, alt: "Note 13 Pro"}, "Musimundo": {p: 510000}, "OnCity": {p: 520000}, "Compumundo": {p: 499000} } },
            { name: "Galaxy Z Flip 6 Blue", cat: "Celular", prices: { "ML": {p: 1600000}, "Frávega": {p: 1450000}, "Musimundo": {p: 1580000}, "OnCity": {p: null}, "Compumundo": {p: 1550000} } },
            { name: "Galaxy A15 4G 128GB", cat: "Celular", prices: { "ML": {p: 290000}, "Frávega": {p: 320000}, "Musimundo": {p: 310000}, "OnCity": {p: 305000}, "Compumundo": {p: 315000} } },
            { name: "iPhone 13 128GB Midnight", cat: "Celular", prices: { "ML": {p: 1100000}, "Frávega": {p: 1250000}, "Musimundo": {p: 1280000, alt: "Starlight"}, "OnCity": {p: null}, "Compumundo": {p: 1300000} } },
            { name: "Moto Razr 50 Ultra", cat: "Celular", prices: { "ML": {p: 1900000}, "Frávega": {p: 2050000}, "Musimundo": {p: 2100000}, "OnCity": {p: 2080000}, "Compumundo": {p: 2150000, alt: "Razr 50 Std"} } },

            // 10 NOTEBOOKS
            { name: "MacBook Air M2 13\"", cat: "Notebook", prices: { "ML": {p: 2100000}, "Frávega": {p: 2350000}, "Musimundo": {p: null}, "OnCity": {p: 2450000, alt: "M1 Chip"}, "Compumundo": {p: 2400000} } },
            { name: "Lenovo IdeaPad 3 i3", cat: "Notebook", prices: { "ML": {p: 650000}, "Frávega": {p: 630000}, "Musimundo": {p: 620000}, "OnCity": {p: 640000}, "Compumundo": {p: 645000} } },
            { name: "HP Laptop 15 Core i5", cat: "Notebook", prices: { "ML": {p: 850000}, "Frávega": {p: 820000}, "Musimundo": {p: 835000}, "OnCity": {p: 860000}, "Compumundo": {p: 840000} } },
            { name: "Dell Inspiron 15 i7", cat: "Notebook", prices: { "ML": {p: 1200000}, "Frávega": {p: null}, "Musimundo": {p: 1150000}, "OnCity": {p: 1180000}, "Compumundo": {p: 1195000} } },
            { name: "ASUS Vivobook 16 8GB", cat: "Notebook", prices: { "ML": {p: 950000}, "Frávega": {p: 920000}, "Musimundo": {p: 935000}, "OnCity": {p: 965000}, "Compumundo": {p: 940000} } },
            { name: "Acer Aspire 5 Ryzen 7", cat: "Notebook", prices: { "ML": {p: 880000}, "Frávega": {p: 870000}, "Musimundo": {p: 890000, alt: "Intel i7"}, "OnCity": {p: 875000}, "Compumundo": {p: 850000} } },
            { name: "Notebook Noblex 14\"", cat: "Notebook", prices: { "ML": {p: 550000}, "Frávega": {p: 520000}, "Musimundo": {p: 510000}, "OnCity": {p: 530000}, "Compumundo": {p: null} } },
            { name: "Lenovo Legion 5i Pro", cat: "Notebook", prices: { "ML": {p: 2800000}, "Frávega": {p: null}, "Musimundo": {p: 3050000}, "OnCity": {p: 2990000}, "Compumundo": {p: 3100000} } },
            { name: "MacBook Pro M3 14\"", cat: "Notebook", prices: { "ML": {p: 4500000}, "Frávega": {p: 4800000}, "Musimundo": {p: 4950000, alt: "Max Chip"}, "OnCity": {p: null}, "Compumundo": {p: 4900000} } },
            { name: "Galaxy Book3 i5", cat: "Notebook", prices: { "ML": {p: 1300000}, "Frávega": {p: 1270000}, "Musimundo": {p: 1250000}, "OnCity": {p: 1280000}, "Compumundo": {p: 1290000} } },

            // 5 LAVARROPAS
            { name: "Samsung 9kg Frontal", cat: "Lavarropas", prices: { "ML": {p: 950000}, "Frávega": {p: 890000}, "Musimundo": {p: 920000}, "OnCity": {p: 910000}, "Compumundo": {p: null} } },
            { name: "Philco 5kg Superior", cat: "Lavarropas", prices: { "ML": {p: 550000}, "Frávega": {p: 490000}, "Musimundo": {p: 520000}, "OnCity": {p: 535000}, "Compumundo": {p: 540000} } },
            { name: "Drean Next 8.12 Eco", cat: "Lavarropas", prices: { "ML": {p: 780000}, "Frávega": {p: 740000}, "Musimundo": {p: 760000}, "OnCity": {p: 750000, alt: "Next 8.14"}, "Compumundo": {p: 765000} } },
            { name: "LG Inverter 8.5kg", cat: "Lavarropas", prices: { "ML": {p: 1100000}, "Frávega": {p: 1050000}, "Musimundo": {p: 1080000}, "OnCity": {p: null}, "Compumundo": {p: 1099000} } },
            { name: "Whirlpool 9kg WLF90", cat: "Lavarropas", prices: { "ML": {p: 980000}, "Frávega": {p: 920000}, "Musimundo": {p: 950000}, "OnCity": {p: 940000}, "Compumundo": {p: null} } },

            // 6 HELADERAS
            { name: "Samsung No Frost 328L", cat: "Heladera", prices: { "ML": {p: 1300000}, "Frávega": {p: 1150000}, "Musimundo": {p: 1200000}, "OnCity": {p: 1220000}, "Compumundo": {p: 1250000, alt: "Inox"} } },
            { name: "Philco Ciclica 290L", cat: "Heladera", prices: { "ML": {p: 650000}, "Frávega": {p: 610000}, "Musimundo": {p: 630000}, "OnCity": {p: 620000}, "Compumundo": {p: 599000} } },
            { name: "Whirlpool WRM45AK", cat: "Heladera", prices: { "ML": {p: 1500000}, "Frávega": {p: 1420000}, "Musimundo": {p: 1450000}, "OnCity": {p: 1480000}, "Compumundo": {p: 1460000} } },
            { name: "Gafa White 358L", cat: "Heladera", prices: { "ML": {p: 680000}, "Frávega": {p: 630000}, "Musimundo": {p: 660000}, "OnCity": {p: 650000}, "Compumundo": {p: null} } },
            { name: "LG Instaview Black", cat: "Heladera", prices: { "ML": {p: 5500000}, "Frávega": {p: null}, "Musimundo": {p: 5800000}, "OnCity": {p: 5700000, alt: "Side By Side"}, "Compumundo": {p: 5900000} } },
            { name: "Siam Side by Side 505L", cat: "Heladera", prices: { "ML": {p: 2200000}, "Frávega": {p: 1950000}, "Musimundo": {p: 2100000}, "OnCity": {p: 2050000}, "Compumundo": {p: 2150000} } },

            // 4 AIRES
            { name: "Siam Inverter 3000fg", cat: "Aire", prices: { "ML": {p: 1100000}, "Frávega": {p: 769999}, "Musimundo": {p: 980000}, "OnCity": {p: 950000}, "Compumundo": {p: 1050000} } },
            { name: "Samsung WindFree 3000", cat: "Aire", prices: { "ML": {p: 1400000}, "Frávega": {p: 1320000}, "Musimundo": {p: 1350000}, "OnCity": {p: 1350000}, "Compumundo": {p: 1380000} } },
            { name: "Philco Split 2200fg", cat: "Aire", prices: { "ML": {p: 650000}, "Frávega": {p: 590000}, "Musimundo": {p: 610000}, "OnCity": {p: 620000}, "Compumundo": {p: null} } },
            { name: "BGH Silent Air 4500", cat: "Aire", prices: { "ML": {p: 1600000}, "Frávega": {p: 1520000}, "Musimundo": {p: 1550000}, "OnCity": {p: 1540000, alt: "Split Std"}, "Compumundo": {p: 1580000} } },

            // 3 VENTILADORES
            { name: "Liliana Pie 20\"", cat: "Ventilador", prices: { "ML": {p: 75000}, "Frávega": {p: 68000}, "Musimundo": {p: 72000}, "OnCity": {p: 70000}, "Compumundo": {p: 73000} } },
            { name: "Atma Mesa 12\"", cat: "Ventilador", prices: { "ML": {p: 45000}, "Frávega": {p: 41000}, "Musimundo": {p: null}, "OnCity": {p: 42000}, "Compumundo": {p: 39000} } },
            { name: "Turbo Philco 16\"", cat: "Ventilador", prices: { "ML": {p: 62000}, "Frávega": {p: 55000}, "Musimundo": {p: 59000}, "OnCity": {p: 57000}, "Compumundo": {p: null} } },

            // 2 MICROONDAS
            { name: "Samsung 23L Grill", cat: "Microondas", prices: { "ML": {p: 220000}, "Frávega": {p: 199000}, "Musimundo": {p: 210000}, "OnCity": {p: 205000}, "Compumundo": {p: 215000} } },
            { name: "Atma 20L Digital", cat: "Microondas", prices: { "ML": {p: 165000}, "Frávega": {p: 152000}, "Musimundo": {p: 155000}, "OnCity": {p: 160000}, "Compumundo": {p: 150000} } },

            // 2 AURICULARES
            { name: "Sony WH-1000XM5", cat: "Auricular", prices: { "ML": {p: 650000}, "Frávega": {p: 710000}, "Musimundo": {p: 690000}, "OnCity": {p: 705000, alt: "XM4 Model"}, "Compumundo": {p: 720000} } },
            { name: "Galaxy Buds 3 Pro", cat: "Auricular", prices: { "ML": {p: 240000}, "Frávega": {p: 195000}, "Musimundo": {p: 205000}, "OnCity": {p: 210000}, "Compumundo": {p: null} } }
        ];

        const brandBadges = { "ML": "badge-ml", "Frávega": "badge-fravega", "Musimundo": "badge-musimundo", "OnCity": "badge-oncity", "Compumundo": "badge-compumundo" };

        function render(filter = "") {
            const grid = document.getElementById('radarGrid');
            grid.innerHTML = "";
            const filtered = products.filter(p => p.name.toLowerCase().includes(filter.toLowerCase()));
            document.getElementById('counter').innerText = `${filtered.length} Productos Analizados`;

            filtered.forEach(p => {
                const stores = Object.keys(p.prices);
                const available = stores.filter(s => p.prices[s].p !== null);
                const winner = available.reduce((a, b) => p.prices[a].p < p.prices[b].p ? a : b);
                const bClass = brandBadges[winner];

                grid.innerHTML += `
                    <div class="product-card">
                        <div class="img-box"><i class="fa-solid ${icons[p.cat]}"></i></div>
                        <div class="p-5 flex flex-col flex-1">
                            <span class="text-[7px] font-black text-gray-400 uppercase tracking-widest">${p.cat}</span>
                            <h3 class="font-bold text-[10px] mb-4 h-8 overflow-hidden uppercase tracking-tighter leading-tight">${p.name}</h3>
                            
                            <div class="mb-5 space-y-2">
                                ${stores.map(s => {
                                    const isWinner = s === winner;
                                    const data = p.prices[s];
                                    return `
                                        <div class="flex justify-between items-start text-[9px] ${isWinner ? 'font-black text-blue-600' : ''}">
                                            <span class="uppercase font-bold ${isWinner ? '' : 'text-gray-400'}">${s}</span>
                                            <div class="text-right leading-none">
                                                <span>${data.p ? '$' + data.p.toLocaleString() : '<span class="no-stock italic">SIN STOCK</span>'}</span>
                                                ${data.alt ? `<span class="alt-label">Alt: ${data.alt}</span>` : ''}
                                            </div>
                                        </div>
                                    `;
                                }).join('')}
                            </div>

                            <div class="bg-gray-900 text-white p-3 rounded-2xl mt-auto">
                                <div class="flex justify-between items-center text-[7px] mb-1">
                                    <span class="text-blue-400 uppercase font-black">Ganador</span>
                                    <span class="${bClass} px-2 py-0.5 rounded uppercase font-black">${winner}</span>
                                </div>
                                <div class="text-xl font-black">$${p.prices[winner].p.toLocaleString()}</div>
                            </div>
                            <button class="${bClass} w-full mt-3 py-2.5 rounded-xl text-[9px] font-black uppercase tracking-widest hover:opacity-90 transition">Ver Oferta</button>
                        </div>
                    </div>
                `;
            });
        }

        document.getElementById('searchInput').addEventListener('input', e => render(e.target.value));
        render();
    </script>
</body>
</html>
