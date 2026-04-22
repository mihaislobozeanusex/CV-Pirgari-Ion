<!DOCTYPE html>
<html lang="ro">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ion Pirgari - The Human Compiler</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;500;600&family=Inter:wght@300;400;500;600;700;800;900&display=swap');
        
        :root {
            --primary: #00d1b2;
            --primary-dark: #00b89c;
            --bg-slate: #f8fafc;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-color: var(--bg-slate);
            color: #1e293b;
        }

        .mono { font-family: 'Fira Code', monospace; }

        .card {
            background: white;
            border-radius: 1.5rem;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.03);
            border: 1px solid #f1f5f9;
            transition: all 0.3s ease;
        }

        .card:hover {
            transform: translateY(-4px);
            box-shadow: 0 12px 30px rgba(0, 0, 0, 0.06);
        }

        .progress-bar {
            height: 10px;
            background: #f1f5f9;
            border-radius: 999px;
            overflow: hidden;
        }

        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, var(--primary), #3b82f6);
            border-radius: 999px;
        }

        .status-dot {
            height: 12px;
            width: 12px;
            background-color: #22c55e;
            border-radius: 50%;
            display: inline-block;
            box-shadow: 0 0 12px #22c55e;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0% { transform: scale(1); opacity: 1; }
            50% { transform: scale(1.2); opacity: 0.7; }
            100% { transform: scale(1); opacity: 1; }
        }

        .sector-title {
            font-family: 'Fira Code', monospace;
            text-transform: uppercase;
            letter-spacing: 0.1em;
            color: #94a3b8;
            font-size: 0.75rem;
            font-weight: 700;
        }

        .skill-badge {
            background: #f1f5f9;
            padding: 4px 12px;
            border-radius: 8px;
            font-size: 0.8rem;
            font-weight: 600;
            color: #475569;
            border: 1px solid #e2e8f0;
        }

        .terminal-block {
            background: #0f172a;
            color: #38bdf8;
            padding: 1.5rem;
            border-radius: 1rem;
            font-family: 'Fira Code', monospace;
            font-size: 0.85rem;
            line-height: 1.6;
        }
    </style>
</head>
<body class="p-4 md:p-12">

    <div class="max-w-7xl mx-auto space-y-8">
        
        <!-- HEADER: SYSTEM CORE -->
        <header class="card p-8 md:p-14 flex flex-col md:flex-row items-center gap-10 relative overflow-hidden">
            <div class="absolute top-0 right-0 p-8">
                <div class="flex items-center gap-3 bg-slate-50 px-4 py-2 rounded-full border border-slate-100">
                    <span class="status-dot"></span>
                    <span class="text-xs font-bold mono text-slate-500 uppercase tracking-tighter">Sistem Optimizat</span>
                </div>
            </div>
            
            <div class="relative">
                <div class="w-36 h-36 md:w-48 md:h-48 bg-slate-900 rounded-[2.5rem] flex items-center justify-center text-white text-6xl font-black shadow-2xl relative z-10">
                    IP
                </div>
                <div class="absolute -inset-4 bg-teal-400 opacity-10 blur-2xl rounded-full"></div>
            </div>

            <div class="text-center md:text-left space-y-4">
                <div class="space-y-1">
                    <p class="mono text-teal-500 font-bold text-sm tracking-widest uppercase">[NODE: HIGH-PERFORMER]</p>
                    <h1 class="text-5xl md:text-7xl font-black text-slate-900 tracking-tight">
                        ION <span class="text-transparent bg-clip-text bg-gradient-to-r from-teal-500 to-blue-600">PIRGARI</span>
                    </h1>
                    <p class="text-xl md:text-2xl mono text-slate-400 font-medium">THE HUMAN COMPILER</p>
                </div>
                
                <div class="flex flex-wrap justify-center md:justify-start gap-4 pt-2">
                    <div class="flex items-center gap-2 px-4 py-2 bg-slate-50 rounded-xl border border-slate-100 text-sm font-bold text-slate-600">
                        <i class="fa-solid fa-graduation-cap text-teal-500"></i> L.T. „Mihai Marinciuc”
                    </div>
                    <div class="flex items-center gap-2 px-4 py-2 bg-slate-50 rounded-xl border border-slate-100 text-sm font-bold text-slate-600">
                        <i class="fa-solid fa-calendar text-teal-500"></i> Promoția 2026
                    </div>
                    <div class="flex items-center gap-2 px-4 py-2 bg-slate-50 rounded-xl border border-slate-100 text-sm font-bold text-slate-600">
                        <i class="fa-solid fa-clock text-teal-500"></i> 19 Rotații Solare
                    </div>
                </div>
            </div>
        </header>

        <div class="grid grid-cols-1 lg:grid-cols-12 gap-8">
            
            <!-- LEFT COLUMN: ARCHITECTURE & SPECS -->
            <div class="lg:col-span-4 space-y-8">
                
                <!-- CONTACT ENDPOINTS -->
                <section class="card p-8">
                    <h2 class="sector-title mb-6">[SECTOR: NETWORKING]</h2>
                    <div class="space-y-4">
                        <a href="mailto:pirgari.slobozeanu@highperformance.md" class="flex items-center gap-4 group p-3 hover:bg-slate-50 rounded-2xl transition-all">
                            <div class="w-11 h-11 bg-teal-50 text-teal-600 flex items-center justify-center rounded-xl group-hover:bg-teal-500 group-hover:text-white transition-all">
                                <i class="fa-solid fa-envelope"></i>
                            </div>
                            <div class="overflow-hidden">
                                <p class="text-[10px] mono text-slate-400 uppercase font-bold">Email Direct</p>
                                <p class="text-sm font-bold text-slate-700 truncate">pirgari.slobozeanu@highperformance.md</p>
                            </div>
                        </a>
                        <a href="#" class="flex items-center gap-4 group p-3 hover:bg-slate-50 rounded-2xl transition-all">
                            <div class="w-11 h-11 bg-blue-50 text-blue-600 flex items-center justify-center rounded-xl group-hover:bg-blue-500 group-hover:text-white transition-all">
                                <i class="fa-brands fa-github"></i>
                            </div>
                            <div>
                                <p class="text-[10px] mono text-slate-400 uppercase font-bold">GitHub Repo</p>
                                <p class="text-sm font-bold text-slate-700">github.com/pirgarislobozeanu</p>
                            </div>
                        </a>
                        <div class="flex items-center gap-4 p-3">
                            <div class="w-11 h-11 bg-slate-50 text-slate-400 flex items-center justify-center rounded-xl">
                                <i class="fa-solid fa-location-dot"></i>
                            </div>
                            <div>
                                <p class="text-[10px] mono text-slate-400 uppercase font-bold">Geolocație</p>
                                <p class="text-sm font-bold text-slate-700">Chișinău, Moldova</p>
                            </div>
                        </div>
                    </div>
                </section>

                <!-- ARSENAL TEHNIC EXTINS -->
                <section class="card p-8">
                    <h2 class="sector-title mb-8">[SECTOR: ARSENAL TEHNIC]</h2>
                    <div class="space-y-6">
                        <div>
                            <div class="flex justify-between text-xs font-black mb-3 text-slate-700">
                                <span>C++ STANDARD</span>
                                <span class="mono text-teal-500">95%</span>
                            </div>
                            <div class="progress-bar"><div class="progress-fill" style="width: 95%"></div></div>
                        </div>
                        <div>
                            <div class="flex justify-between text-xs font-black mb-3 text-slate-700">
                                <span>PYTHON SCRIPTING</span>
                                <span class="mono text-teal-500">85%</span>
                            </div>
                            <div class="progress-bar"><div class="progress-fill" style="width: 85%"></div></div>
                        </div>
                        <div>
                            <div class="flex justify-between text-xs font-black mb-3 text-slate-700">
                                <span>SQL ARCHITECTURE</span>
                                <span class="mono text-teal-500">75%</span>
                            </div>
                            <div class="progress-bar"><div class="progress-fill" style="width: 75%"></div></div>
                        </div>
                        <div>
                            <div class="flex justify-between text-xs font-black mb-3 text-slate-700">
                                <span>DEBUGGING & QA</span>
                                <span class="mono text-teal-500">100%</span>
                            </div>
                            <div class="progress-bar"><div class="progress-fill" style="width: 100%"></div></div>
                        </div>
                    </div>

                    <div class="mt-10 space-y-6">
                        <div class="p-4 bg-slate-50 rounded-2xl border border-slate-100">
                            <h4 class="text-xs font-bold mono text-slate-400 uppercase mb-3">Algoritmică Avansată</h4>
                            <div class="flex flex-wrap gap-2">
                                <span class="skill-badge">Grafuri</span>
                                <span class="skill-badge">Arbori</span>
                                <span class="skill-badge">O(n log n)</span>
                                <span class="skill-badge">Dynamic Programming</span>
                            </div>
                        </div>
                        <div class="p-4 bg-slate-50 rounded-2xl border border-slate-100">
                            <h4 class="text-xs font-bold mono text-slate-400 uppercase mb-3">Inginerie Sistem</h4>
                            <div class="flex flex-wrap gap-2">
                                <span class="skill-badge">Git/Branching</span>
                                <span class="skill-badge">CLI Linux</span>
                                <span class="skill-badge">Hardware Diagnostic</span>
                                <span class="skill-badge">Criptare</span>
                            </div>
                        </div>
                    </div>
                </section>

                <!-- METABOLISM & TIMING -->
                <section class="card p-8 bg-slate-900 text-white border-none shadow-2xl">
                    <h2 class="sector-title text-slate-500 mb-6">[SECTOR: METABOLISM]</h2>
                    <div class="space-y-4">
                        <div class="flex items-start gap-4">
                            <div class="w-8 h-8 bg-slate-800 rounded flex items-center justify-center text-teal-400 mono">
                                🔸
                            </div>
                            <div>
                                <h5 class="text-sm font-bold">Sistem de Energie</h5>
                                <p class="text-xs text-slate-400 mt-1">Conversia cafeinei în linii de cod funcționale.</p>
                            </div>
                        </div>
                        <div class="flex items-start gap-4">
                            <div class="w-8 h-8 bg-slate-800 rounded flex items-center justify-center text-blue-400 mono">
                                🔸
                            </div>
                            <div>
                                <h5 class="text-sm font-bold">Deep Work Engine</h5>
                                <p class="text-xs text-slate-400 mt-1">Utilizarea tehnicii Pomodoro pentru performanță.</p>
                            </div>
                        </div>
                        <div class="flex items-start gap-4">
                            <div class="w-8 h-8 bg-slate-800 rounded flex items-center justify-center text-purple-400 mono">
                                🔸
                            </div>
                            <div>
                                <h5 class="text-sm font-bold">Hobby-uri Analitice</h5>
                                <p class="text-xs text-slate-400 mt-1">Gaming de strategie (Chess/RTS) pentru tactică.</p>
                            </div>
                        </div>
                    </div>
                </section>
            </div>

            <!-- RIGHT COLUMN: LOGIC, ART & IMPACT -->
            <div class="lg:col-span-8 space-y-8">
                
                <!-- GENEZA & FILOZOFIE -->
                <section class="card p-10 relative overflow-hidden">
                    <div class="absolute top-0 right-0 p-10 opacity-5 pointer-events-none">
                        <i class="fa-solid fa-microchip text-9xl"></i>
                    </div>
                    <h2 class="sector-title mb-8">[SECTOR: GENEZA & FILOZOFIA EXISTENȚIALĂ]</h2>
                    <div class="space-y-6">
                        <p class="text-3xl font-black text-slate-800 leading-tight">
                            "Deconstruiesc realitatea în instrucțiuni atomice pentru a o reconstrui mai eficient."
                        </p>
                        <p class="text-lg text-slate-600 leading-relaxed max-w-2xl">
                            Format în ecosistemul Moldovei, unde pragmatismul se întâlnește cu o reziliență istorică. Misiunea mea: reducerea entropiei informaționale prin cod curat și soluții creative de impact. Caracterul meu este compilat cu valori de onestitate, transparență și meritocrație.
                        </p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <div class="p-4 bg-slate-50 rounded-2xl border-l-4 border-teal-500">
                                <h4 class="font-bold text-slate-800">Identitate Ontologică</h4>
                                <p class="text-sm text-slate-500 mt-1">Hibrid între rigoarea matematică și fluiditatea artistică.</p>
                            </div>
                            <div class="p-4 bg-slate-50 rounded-2xl border-l-4 border-blue-500">
                                <h4 class="font-bold text-slate-800">Adaptabilitate</h4>
                                <p class="text-sm text-slate-500 mt-1">De la C++ la poezie în mai puțin de o secundă.</p>
                            </div>
                        </div>
                    </div>
                </section>

                <!-- IMPACT STRATEGIC & LEADERSHIP -->
                <section class="card p-10">
                    <h2 class="sector-title mb-10">[SECTOR: LEADERSHIP CIVIC & IMPACT STRATEGIC]</h2>
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-10">
                        <div class="space-y-4">
                            <div class="flex items-center gap-4">
                                <div class="text-5xl font-black text-teal-500 mono">42%</div>
                                <div class="h-12 w-[2px] bg-slate-100"></div>
                                <h4 class="text-sm font-bold text-slate-700 leading-snug">Eficiență în <br>Laborator</h4>
                            </div>
                            <p class="text-sm text-slate-500 leading-relaxed">Identificarea ineficiențelor și implementarea propriului sistem de gestiune a resurselor.</p>
                        </div>
                        <div class="space-y-4">
                            <div class="flex items-center gap-4">
                                <div class="text-5xl font-black text-blue-500 mono">25%</div>
                                <div class="h-12 w-[2px] bg-slate-100"></div>
                                <h4 class="text-sm font-bold text-slate-700 leading-snug">Success în <br>Mentorat</h4>
                            </div>
                            <p class="text-sm text-slate-500 leading-relaxed">Coordonarea grupului de studiu și reducerea anxietății pentru examenele de informatică.</p>
                        </div>
                    </div>
                    <div class="mt-10 p-6 bg-teal-50 rounded-3xl border border-teal-100 flex items-center gap-6">
                        <div class="w-14 h-14 bg-white rounded-2xl flex items-center justify-center text-teal-600 text-xl shadow-sm">
                            <i class="fa-solid fa-server"></i>
                        </div>
                        <div>
                            <h4 class="font-bold text-slate-800">Voluntariat Tehnic de Elită</h4>
                            <p class="text-sm text-slate-600">Asigurarea uptime-ului infrastructurii IT a liceului „Mihai Marinciuc”.</p>
                        </div>
                    </div>
                </section>

                <!-- RANDARE ANALOGICĂ & ESTETICĂ -->
                <section class="card p-10">
                    <h2 class="sector-title mb-8">[SECTOR: RANDARE ANALOGICĂ & ESTETICĂ]</h2>
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                        <div class="space-y-6">
                            <div class="p-6 bg-slate-50 rounded-[2rem] hover:bg-slate-100 transition-colors">
                                <h4 class="font-black text-slate-800 flex items-center gap-3 mb-4">
                                    <i class="fa-solid fa-paintbrush text-teal-500"></i> Mecanică Grafică
                                </h4>
                                <ul class="text-sm text-slate-600 space-y-3 font-medium">
                                    <li class="flex gap-2"><span>•</span> Grafit: Umbre ce sfidează bidimensionalitatea.</li>
                                    <li class="flex gap-2"><span>•</span> Acrilic: Control precis al culorilor (Hex-like).</li>
                                    <li class="flex gap-2"><span>•</span> Raportul Φ: Ghidarea privirii către punctul de interes.</li>
                                </ul>
                            </div>
                        </div>
                        <div class="space-y-6">
                            <div class="p-6 bg-slate-50 rounded-[2rem] hover:bg-slate-100 transition-colors">
                                <h4 class="font-black text-slate-800 flex items-center gap-3 mb-4">
                                    <i class="fa-solid fa-keyboard text-blue-500"></i> Inginerie Lingvistică
                                </h4>
                                <ul class="text-sm text-slate-600 space-y-3 font-medium">
                                    <li class="flex gap-2"><span>•</span> Poezie: Compilarea sentimentelor în versuri.</li>
                                    <li class="flex gap-2"><span>•</span> Metafore: Algoritmi de compresie filozofică.</li>
                                    <li class="flex gap-2"><span>•</span> Narațiune: Explorarea condiției umane digitale.</li>
                                </ul>
                            </div>
                        </div>
                    </div>
                </section>

                <!-- VALIDARE EXTERNA & LOOP EVOLUTIV -->
                <section class="card p-10 border-dashed border-2 border-slate-200">
                    <div class="flex flex-col md:flex-row justify-between items-start md:items-center gap-6 mb-10">
                        <h2 class="sector-title">[SECTOR: VALIDARE & LOOP EVOLUTIV]</h2>
                        <div class="mono text-xs font-bold text-teal-600 bg-teal-50 px-3 py-1 rounded-full">
                            VERIFICARE STATUS: VALIDAT
                        </div>
                    </div>
                    <div class="grid grid-cols-2 md:grid-cols-3 gap-4">
                        <div class="p-4 bg-white border border-slate-100 rounded-2xl text-center shadow-sm">
                            <i class="fa-solid fa-trophy text-amber-400 mb-2 block text-xl"></i>
                            <p class="text-xs font-bold text-slate-800">Olimpiade Județene</p>
                        </div>
                        <div class="p-4 bg-white border border-slate-100 rounded-2xl text-center shadow-sm">
                            <i class="fa-solid fa-certificate text-teal-400 mb-2 block text-xl"></i>
                            <p class="text-xs font-bold text-slate-800">Atestat Profesional</p>
                        </div>
                        <div class="p-4 bg-white border border-slate-100 rounded-2xl text-center shadow-sm">
                            <i class="fa-solid fa-medal text-blue-400 mb-2 block text-xl"></i>
                            <p class="text-xs font-bold text-slate-800">Premii de Excelență</p>
                        </div>
                    </div>
                    
                    <div class="mt-10 terminal-block">
                        <p class="text-slate-500 mb-2 font-bold uppercase tracking-widest text-[10px]"># system_log --current_vision</p>
                        <p>Pregătire intensă pentru admiterea la o facultate de elită în domeniul IT.</p>
                        <p class="mt-4 text-teal-400">Ion Pirgari@System:~$ <span class="text-white">"Perfect" este punctul de plecare.</span></p>
                    </div>
                </section>

            </div>
        </div>

        <!-- FOOTER: SYSTEM TERMINATION -->
        <footer class="text-center py-16 space-y-6">
            <div class="flex justify-center gap-8 mb-8">
                <a href="#" class="text-slate-300 hover:text-teal-500 transition-all text-2xl"><i class="fa-brands fa-github"></i></a>
                <a href="#" class="text-slate-300 hover:text-blue-600 transition-all text-2xl"><i class="fa-brands fa-linkedin"></i></a>
                <a href="#" class="text-slate-300 hover:text-red-500 transition-all text-2xl"><i class="fa-solid fa-envelope"></i></a>
            </div>
            <p class="mono text-[10px] text-slate-400 tracking-[0.4em] uppercase">
                © 2026 Ion Pirgari — Realitate Optimizată la Persoana I.
            </p>
            <p class="italic text-slate-400 font-medium text-sm">"Nu suntem ceea ce știm, ci ceea ce facem cu ceea ce știm."</p>
        </footer>
    </div>

</body>
</html>
