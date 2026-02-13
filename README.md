# service
<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hayat Enterprise AB | Premium Swedish Transport</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/ScrollTrigger.min.js"></script>
    <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --chocolate-dark: #1a1209;
            --chocolate-med: #2d1f12;
            --chocolate-light: #4a3425;
            --bronze: #8b6914;
            --gold: #d4af37;
            --cream: #f5f1e8;
            --swedish-blue: #006AA7;
        }
        
        body {
            font-family: 'Inter', sans-serif;
            background: linear-gradient(135deg, #0f0a05 0%, #1a1209 50%, #0d0804 100%);
            overflow-x: hidden;
            color: var(--cream);
        }
        
        h1, h2, h3, h4, .display-font {
            font-family: 'Space Grotesk', sans-serif;
        }
        
        /* Aurora Background with Brown Tones */
        .aurora-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: linear-gradient(135deg, #0a0603 0%, #1a1209 50%, #0f0a05 100%);
            overflow: hidden;
        }
        
        .aurora-wave {
            position: absolute;
            width: 200%;
            height: 200%;
            top: -50%;
            left: -50%;
            background: radial-gradient(ellipse at center, rgba(212, 175, 55, 0.08) 0%, transparent 50%),
                        radial-gradient(ellipse at 30% 70%, rgba(139, 105, 20, 0.1) 0%, transparent 40%),
                        radial-gradient(ellipse at 70% 30%, rgba(0, 106, 167, 0.15) 0%, transparent 40%);
            animation: aurora 20s ease-in-out infinite;
            filter: blur(80px);
        }
        
        .aurora-wave:nth-child(2) {
            animation-delay: -5s;
            animation-duration: 25s;
            opacity: 0.6;
            background: radial-gradient(ellipse at center, rgba(74, 52, 37, 0.2) 0%, transparent 50%);
        }
        
        .aurora-wave:nth-child(3) {
            animation-delay: -10s;
            animation-duration: 30s;
            opacity: 0.4;
            background: radial-gradient(ellipse at 40% 60%, rgba(45, 31, 18, 0.3) 0%, transparent 40%);
        }
        
        @keyframes aurora {
            0%, 100% { transform: translate(0, 0) rotate(0deg); }
            33% { transform: translate(5%, 5%) rotate(5deg); }
            66% { transform: translate(-5%, 10%) rotate(-5deg); }
        }
        
        /* Glass Morphism - Dark Brown Tint */
        .glass {
            background: rgba(45, 31, 18, 0.4);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border: 1px solid rgba(212, 175, 55, 0.1);
        }
        
        .glass-strong {
            background: rgba(45, 31, 18, 0.6);
            backdrop-filter: blur(30px);
            -webkit-backdrop-filter: blur(30px);
            border: 1px solid rgba(212, 175, 55, 0.2);
        }
        
        /* Gold Accent */
        .gold-accent {
            position: relative;
        }
        .gold-accent::after {
            content: '';
            position: absolute;
            bottom: -4px;
            left: 0;
            width: 100%;
            height: 2px;
            background: linear-gradient(90deg, var(--gold), var(--bronze));
            transform: scaleX(0);
            transition: transform 0.3s ease;
        }
        .gold-accent:hover::after {
            transform: scaleX(1);
        }
        
        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: var(--chocolate-dark);
        }
        ::-webkit-scrollbar-thumb {
            background: var(--chocolate-light);
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: var(--bronze);
        }
        
        /* Text Gradient */
        .text-gradient {
            background: linear-gradient(135deg, var(--cream) 0%, var(--gold) 50%, var(--bronze) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        
        /* Magnetic Button */
        .magnetic-btn {
            transition: transform 0.3s cubic-bezier(0.23, 1, 0.32, 1);
        }
        
        /* Vehicle Cards */
        .vehicle-card {
            transition: all 0.5s cubic-bezier(0.23, 1, 0.32, 1);
        }
        .vehicle-card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 20px 40px rgba(212, 175, 55, 0.1);
        }
        
        /* City Cards */
        .city-card {
            transition: all 0.5s cubic-bezier(0.23, 1, 0.32, 1);
        }
        .city-card:hover {
            transform: translateY(-10px) scale(1.02);
        }
        
        /* Floating Elements */
        .float {
            animation: float 6s ease-in-out infinite;
        }
        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }
        
        /* Noise Texture */
        .noise {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1000;
            opacity: 0.04;
            background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noiseFilter'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.65' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noiseFilter)'/%3E%3C/svg%3E");
        }
        
        /* Reveal Animation */
        .reveal {
            opacity: 0;
            transform: translateY(30px);
        }
        
        /* H Logo Styling */
        .h-logo {
            font-family: 'Space Grotesk', sans-serif;
            font-weight: 700;
            background: linear-gradient(135deg, var(--gold), var(--cream));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        
        /* Form Styling */
        .form-input {
            background: rgba(45, 31, 18, 0.5);
            border: 1px solid rgba(212, 175, 55, 0.2);
            color: var(--cream);
            transition: all 0.3s ease;
        }
        .form-input:focus {
            outline: none;
            border-color: var(--gold);
            box-shadow: 0 0 0 3px rgba(212, 175, 55, 0.1);
        }
        .form-input::placeholder {
            color: rgba(245, 241, 232, 0.4);
        }
    </style>
</head>
<body class="antialiased">

    <!-- Noise Overlay -->
    <div class="noise"></div>

    <!-- Aurora Background -->
    <div class="aurora-bg">
        <div class="aurora-wave"></div>
        <div class="aurora-wave"></div>
        <div class="aurora-wave"></div>
    </div>

    <!-- Navigation -->
    <nav class="fixed top-0 w-full z-50 px-6 py-4 transition-all duration-300" id="navbar">
        <div class="max-w-7xl mx-auto glass rounded-2xl px-6 py-4 flex justify-between items-center">
            <div class="flex items-center gap-4">
                <div class="w-12 h-12 rounded-xl bg-gradient-to-br from-[#2d1f12] to-[#4a3425] border border-[#d4af37]/30 flex items-center justify-center">
                    <span class="text-2xl h-logo">H</span>
                </div>
                <div class="flex flex-col">
                    <span class="text-xl font-bold display-font tracking-tight text-[#f5f1e8]">Hayat Enterprise</span>
                    <span class="text-xs text-[#d4af37] tracking-widest uppercase">Premium Transport</span>
                </div>
            </div>
            
            <div class="hidden md:flex items-center gap-8">
                <a href="#fleet" class="text-sm font-medium text-[#f5f1e8]/70 hover:text-[#f5f1e8] transition-colors gold-accent">Fleet</a>
                <a href="#cities" class="text-sm font-medium text-[#f5f1e8]/70 hover:text-[#f5f1e8] transition-colors gold-accent">Cities</a>
                <a href="#booking" class="text-sm font-medium text-[#f5f1e8]/70 hover:text-[#f5f1e8] transition-colors gold-accent">Book Now</a>
                <a href="#contact" class="text-sm font-medium text-[#f5f1e8]/70 hover:text-[#f5f1e8] transition-colors gold-accent">Contact</a>
            </div>
            
            <a href="#booking" class="magnetic-btn glass-strong px-6 py-3 rounded-full text-sm font-semibold hover:bg-[#d4af37]/20 transition-all flex items-center gap-2 group border border-[#d4af37]/30">
                <span class="text-[#d4af37]">Request Ride</span>
                <svg class="w-4 h-4 text-[#d4af37] transform group-hover:translate-x-1 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3"/>
                </svg>
            </a>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="relative min-h-screen flex items-center justify-center px-6 pt-20 overflow-hidden">
        <div class="max-w-7xl mx-auto grid lg:grid-cols-2 gap-12 items-center">
            <div class="space-y-8 z-10">
                <div class="inline-flex items-center gap-2 glass px-4 py-2 rounded-full text-xs font-medium text-[#d4af37] reveal">
                    <span class="w-2 h-2 bg-[#d4af37] rounded-full animate-pulse"></span>
                    Serving All of Sweden
                </div>
                
                <h1 class="text-6xl md:text-8xl font-bold display-font leading-none reveal">
                    Ride the <br>
                    <span class="text-gradient">Northern</span><br>
                    Light
                </h1>
                
                <p class="text-xl text-[#f5f1e8]/70 max-w-lg leading-relaxed reveal">
                    Premium transport across Sweden's most iconic cities. From the Arctic Circle to the Øresund Bridge, experience Scandinavian luxury in motion.
                </p>
                
                <div class="flex flex-wrap gap-4 reveal">
                    <a href="#booking" class="magnetic-btn bg-[#d4af37] text-[#1a1209] px-8 py-4 rounded-full font-bold text-lg hover:shadow-[0_0_30px_rgba(212,175,55,0.4)] transition-all flex items-center gap-2">
                        Book Transport
                        <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7l5 5m0 0l-5 5m5-5H6"/>
                        </svg>
                    </a>
                    <a href="#fleet" class="magnetic-btn glass px-8 py-4 rounded-full font-semibold text-lg hover:bg-[#d4af37]/10 transition-all text-[#f5f1e8]">
                        View Fleet
                    </a>
                </div>
                
                <div class="flex items-center gap-6 pt-8 reveal">
                    <div class="text-center">
                        <div class="text-3xl font-bold text-[#d4af37]">24/7</div>
                        <div class="text-xs text-[#f5f1e8]/50 uppercase tracking-wider">Service</div>
                    </div>
                    <div class="w-px h-12 bg-[#d4af37]/20"></div>
                    <div class="text-center">
                        <div class="text-3xl font-bold text-[#f5f1e8]">4.9</div>
                        <div class="text-xs text-[#f5f1e8]/50 uppercase tracking-wider">Rating</div>
                    </div>
                    <div class="w-px h-12 bg-[#d4af37]/20"></div>
                    <div class="text-center">
                        <div class="text-3xl font-bold text-[#d4af37]">Hybrid</div>
                        <div class="text-xs text-[#f5f1e8]/50 uppercase tracking-wider">Fleet</div>
                    </div>
                </div>
            </div>
            
            <div class="relative lg:h-[600px] flex items-center justify-center">
                <!-- Hero Vehicle Visualization -->
                <div class="relative w-full max-w-lg float">
                    <div class="absolute inset-0 bg-gradient-to-r from-[#4a3425] to-[#d4af37] rounded-3xl blur-3xl opacity-20 transform rotate-6"></div>
                    <div class="relative glass-strong rounded-3xl p-2 border border-[#d4af37]/20">
                        <div class="aspect-[16/10] bg-gradient-to-br from-[#0f0a05] to-[#1a1209] rounded-2xl overflow-hidden relative">
                            <img src="https://cdn-ds.com/blogs-media/sites/177/2024/08/12065954/2024-Mercedes-Benz-E-Class-Sedan-Black-B_o.jpg" alt="Mercedes E-Class" class="w-full h-full object-cover opacity-90 hover:scale-105 transition-transform duration-700">
                            <div class="absolute inset-0 bg-gradient-to-t from-[#0f0a05] via-transparent to-transparent"></div>
                            <div class="absolute top-4 right-4 glass px-3 py-1 rounded-full text-xs text-[#d4af37] border border-[#d4af37]/30">Mercedes E-Class</div>
                        </div>
                        <div class="p-6 flex justify-between items-center">
                            <div>
                                <div class="text-sm text-[#f5f1e8]/50 mb-1">Premium Sedan</div>
                                <div class="text-xl font-bold text-[#f5f1e8]">Business Elite</div>
                            </div>
                            <div class="w-12 h-12 rounded-full bg-[#d4af37]/20 flex items-center justify-center border border-[#d4af37]/30">
                                <svg class="w-6 h-6 text-[#d4af37]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"/>
                                </svg>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Fleet Section -->
    <section id="fleet" class="py-32 px-6 relative">
        <div class="max-w-7xl mx-auto">
            <div class="text-center mb-20">
                <h2 class="text-5xl md:text-7xl font-bold display-font mb-6 reveal">Our Fleet</h2>
                <p class="text-xl text-[#f5f1e8]/60 max-w-2xl mx-auto reveal">Premium vehicles maintained to the highest standards. From efficient hybrids to luxury sedans.</p>
            </div>

            <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- Mercedes E-Class -->
                <div class="vehicle-card group relative rounded-3xl overflow-hidden cursor-pointer reveal">
                    <div class="absolute inset-0 bg-gradient-to-t from-[#0f0a05] via-[#0f0a05]/80 to-transparent z-10"></div>
                    <div class="h-[400px] bg-[#1a1209] relative overflow-hidden">
                        <img src="https://cdn-ds.com/blogs-media/sites/177/2024/08/12065954/2024-Mercedes-Benz-E-Class-Sedan-Black-B_o.jpg" alt="Mercedes E-Class" class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-110">
                    </div>
                    <div class="absolute bottom-0 left-0 right-0 p-8 z-20">
                        <div class="flex items-center gap-2 mb-3">
                            <span class="px-3 py-1 rounded-full bg-[#d4af37]/20 text-[#d4af37] text-xs font-bold border border-[#d4af37]/30">FLAGSHIP</span>
                        </div>
                        <h3 class="text-3xl font-bold display-font mb-2 text-[#f5f1e8]">Mercedes E-Class</h3>
                        <p class="text-[#f5f1e8]/60 text-sm mb-4">Executive comfort with premium leather interior and ambient lighting.</p>
                        <div class="flex items-center justify-between text-xs text-[#f5f1e8]/40">
                            <span>4 Passengers</span>
                            <span>Hybrid Available</span>
                        </div>
                    </div>
                </div>

                <!-- Mercedes C-Class -->
                <div class="vehicle-card group relative rounded-3xl overflow-hidden cursor-pointer reveal">
                    <div class="absolute inset-0 bg-gradient-to-t from-[#0f0a05] via-[#0f0a05]/80 to-transparent z-10"></div>
                    <div class="h-[400px] bg-[#1a1209] relative overflow-hidden">
                        <img src="https://di-shared-assets.dealerinspire.com/legacy/rackspace/ldm-images/2024-mercedes-benz-c-300-hero.png" alt="Mercedes C-Class" class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-110">
                    </div>
                    <div class="absolute bottom-0 left-0 right-0 p-8 z-20">
                        <div class="flex items-center gap-2 mb-3">
                            <span class="px-3 py-1 rounded-full bg-[#8b6914]/20 text-[#d4af37] text-xs font-bold border border-[#8b6914]/30">BUSINESS</span>
                        </div>
                        <h3 class="text-3xl font-bold display-font mb-2 text-[#f5f1e8]">Mercedes C-Class</h3>
                        <p class="text-[#f5f1e8]/60 text-sm mb-4">Compact luxury perfect for city travel and airport transfers.</p>
                        <div class="flex items-center justify-between text-xs text-[#f5f1e8]/40">
                            <span>4 Passengers</span>
                            <span>Hybrid Available</span>
                        </div>
                    </div>
                </div>

                <!-- Volvo XC60 -->
                <div class="vehicle-card group relative rounded-3xl overflow-hidden cursor-pointer reveal">
                    <div class="absolute inset-0 bg-gradient-to-t from-[#0f0a05] via-[#0f0a05]/80 to-transparent z-10"></div>
                    <div class="h-[400px] bg-[#1a1209] relative overflow-hidden">
                        <img src="https://www.avus-automobile.com/wp-content/uploads/2023/02/xc60_black_edition.jpg" alt="Volvo XC60" class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-110">
                    </div>
                    <div class="absolute bottom-0 left-0 right-0 p-8 z-20">
                        <div class="flex items-center gap-2 mb-3">
                            <span class="px-3 py-1 rounded-full bg-[#006AA7]/20 text-[#006AA7] text-xs font-bold border border-[#006AA7]/30">SUV</span>
                        </div>
                        <h3 class="text-3xl font-bold display-font mb-2 text-[#f5f1e8]">Volvo XC60</h3>
                        <p class="text-[#f5f1e8]/60 text-sm mb-4">Swedish engineering excellence. Spacious and safe for families.</p>
                        <div class="flex items-center justify-between text-xs text-[#f5f1e8]/40">
                            <span>5 Passengers</span>
                            <span>Plug-in Hybrid</span>
                        </div>
                    </div>
                </div>

                <!-- Toyota Corolla -->
                <div class="vehicle-card group relative rounded-3xl overflow-hidden cursor-pointer reveal">
                    <div class="absolute inset-0 bg-gradient-to-t from-[#0f0a05] via-[#0f0a05]/80 to-transparent z-10"></div>
                    <div class="h-[400px] bg-[#1a1209] relative overflow-hidden">
                        <img src="https://mystrongad.com/toyota/2025/corolla-hybrid/2025-toyota-corolla-hybrid-black.webp" alt="Toyota Corolla Hybrid" class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-110">
                    </div>
                    <div class="absolute bottom-0 left-0 right-0 p-8 z-20">
                        <div class="flex items-center gap-2 mb-3">
                            <span class="px-3 py-1 rounded-full bg-[#4a3425]/40 text-[#f5f1e8] text-xs font-bold border border-[#4a3425]/50">EFFICIENT</span>
                        </div>
                        <h3 class="text-3xl font-bold display-font mb-2 text-[#f5f1e8]">Toyota Corolla</h3>
                        <p class="text-[#f5f1e8]/60 text-sm mb-4">Reliable hybrid efficiency for everyday transport needs.</p>
                        <div class="flex items-center justify-between text-xs text-[#f5f1e8]/40">
                            <span>4 Passengers</span>
                            <span>Hybrid</span>
                        </div>
                    </div>
                </div>

                <!-- Toyota RAV4 -->
                <div class="vehicle-card group relative rounded-3xl overflow-hidden cursor-pointer reveal">
                    <div class="absolute inset-0 bg-gradient-to-t from-[#0f0a05] via-[#0f0a05]/80 to-transparent z-10"></div>
                    <div class="h-[400px] bg-[#1a1209] relative overflow-hidden">
                        <img src="https://hips.hearstapps.com/hmg-prod/images/2023-toyota-rav4-hybrid-woodland-edition-4162-1675116414.jpg?crop=0.598xw:0.449xh;0.213xw,0.361xh&resize=1200:*" alt="Toyota RAV4 Hybrid" class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-110">
                    </div>
                    <div class="absolute bottom-0 left-0 right-0 p-8 z-20">
                        <div class="flex items-center gap-2 mb-3">
                            <span class="px-3 py-1 rounded-full bg-[#4a3425]/40 text-[#f5f1e8] text-xs font-bold border border-[#4a3425]/50">ADVENTURE</span>
                        </div>
                        <h3 class="text-3xl font-bold display-font mb-2 text-[#f5f1e8]">Toyota RAV4</h3>
                        <p class="text-[#f5f1e8]/60 text-sm mb-4">Versatile SUV with AWD capability for all Swedish conditions.</p>
                        <div class="flex items-center justify-between text-xs text-[#f5f1e8]/40">
                            <span>5 Passengers</span>
                            <span>Hybrid AWD</span>
                        </div>
                    </div>
                </div>

                <!-- Fleet Info Card -->
                <div class="glass rounded-3xl p-8 flex flex-col justify-center items-center text-center reveal border border-[#d4af37]/20">
                    <div class="w-20 h-20 rounded-full bg-[#d4af37]/10 flex items-center justify-center mb-6 border border-[#d4af37]/30">
                        <svg class="w-10 h-10 text-[#d4af37]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z"/>
                        </svg>
                    </div>
                    <h3 class="text-2xl font-bold display-font mb-4 text-[#f5f1e8]">All Vehicles Feature</h3>
                    <ul class="space-y-3 text-[#f5f1e8]/70 text-sm text-left w-full">
                        <li class="flex items-center gap-3">
                            <svg class="w-5 h-5 text-[#d4af37]" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"/></svg>
                            Climate Control
                        </li>
                        <li class="flex items-center gap-3">
                            <svg class="w-5 h-5 text-[#d4af37]" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"/></svg>
                            Free WiFi
                        </li>
                        <li class="flex items-center gap-3">
                            <svg class="w-5 h-5 text-[#d4af37]" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"/></svg>
                            Bottled Water
                        </li>
                        <li class="flex items-center gap-3">
                            <svg class="w-5 h-5 text-[#d4af37]" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"/></svg>
                            Phone Charging
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- Cities Section -->
    <section id="cities" class="py-32 px-6 relative">
        <div class="max-w-7xl mx-auto">
            <div class="text-center mb-20">
                <h2 class="text-5xl md:text-7xl font-bold display-font mb-6 reveal">Our Cities</h2>
                <p class="text-xl text-[#f5f1e8]/60 max-w-2xl mx-auto reveal">Connecting Sweden's most dynamic destinations with premium comfort and reliability.</p>
            </div>

            <div class="grid md:grid-cols-3 gap-8">
                <!-- Kiruna -->
                <div class="city-card group relative h-[500px] rounded-3xl overflow-hidden cursor-pointer reveal border border-[#d4af37]/10">
                    <div class="absolute inset-0 bg-gradient-to-t from-[#0f0a05] via-[#0f0a05]/60 to-transparent z-10"></div>
                    <div class="absolute inset-0 bg-[url('https://ucarecdn.com/94ac0bd3-d4af-4b47-bf9f-5d992e484f49/-/format/auto/-/preview/3000x3000/-/quality/lighter/timo-horstschaefer-3QTe0CdhcL4-unsplash.jpg')] bg-cover bg-center transition-transform duration-700 group-hover:scale-110"></div>
                    <div class="absolute inset-0 bg-gradient-to-br from-[#d4af37]/10 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-500"></div>
                    
                    <div class="absolute bottom-0 left-0 right-0 p-8 z-20">
                        <div class="flex items-center gap-2 mb-2">
                            <span class="px-3 py-1 rounded-full bg-[#d4af37]/20 text-[#d4af37] text-xs font-bold border border-[#d4af37]/30">ARCTIC</span>
                        </div>
                        <h3 class="text-4xl font-bold display-font mb-2 text-[#f5f1e8]">Kiruna</h3>
                        <p class="text-[#f5f1e8]/70 text-sm mb-4">Gateway to the Northern Lights. Airport transfers to ICEHOTEL and Aurora camps.</p>
                        <div class="flex items-center gap-4 text-xs text-[#f5f1e8]/50">
                            <span class="flex items-center gap-1">
                                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z"/></svg>
                                24h Service
                            </span>
                            <span class="flex items-center gap-1">
                                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z"/></svg>
                                AWD Fleet
                            </span>
                        </div>
                    </div>
                </div>

                <!-- Malmö -->
                <div class="city-card group relative h-[500px] rounded-3xl overflow-hidden cursor-pointer reveal border border-[#d4af37]/10">
                    <div class="absolute inset-0 bg-gradient-to-t from-[#0f0a05] via-[#0f0a05]/60 to-transparent z-10"></div>
                    <div class="absolute inset-0 bg-[url('https://www.shutterstock.com/image-photo/shot-night-city-turning-torso-260nw-2152322427.jpg')] bg-cover bg-center transition-transform duration-700 group-hover:scale-110"></div>
                    <div class="absolute inset-0 bg-gradient-to-br from-[#8b6914]/10 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-500"></div>
                    
                    <div class="absolute bottom-0 left-0 right-0 p-8 z-20">
                        <div class="flex items-center gap-2 mb-2">
                            <span class="px-3 py-1 rounded-full bg-[#8b6914]/20 text-[#d4af37] text-xs font-bold border border-[#8b6914]/30">SOUTHERN</span>
                        </div>
                        <h3 class="text-4xl font-bold display-font mb-2 text-[#f5f1e8]">Malmö</h3>
                        <p class="text-[#f5f1e8]/70 text-sm mb-4">Øresund connections. Turning Torso views. Copenhagen airport transfers.</p>
                        <div class="flex items-center gap-4 text-xs text-[#f5f1e8]/50">
                            <span class="flex items-center gap-1">
                                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z"/></svg>
                                24h Service
                            </span>
                            <span class="flex items-center gap-1">
                                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3.055 11H5a2 2 0 012 2v1a2 2 0 002 2 2 2 0 012 2v2.945M8 3.935V5.5A2.5 2.5 0 0010.5 8h.5a2 2 0 012 2 2 2 0 104 0 2 2 0 012-2h1.064M15 20.488V18a2 2 0 012-2h3.064"/></svg>
                                International
                            </span>
                        </div>
                    </div>
                </div>

                <!-- Stockholm -->
                <div class="city-card group relative h-[500px] rounded-3xl overflow-hidden cursor-pointer reveal border border-[#d4af37]/10">
                    <div class="absolute inset-0 bg-gradient-to-t from-[#0f0a05] via-[#0f0a05]/60 to-transparent z-10"></div>
                    <div class="absolute inset-0 bg-[url('https://www.shutterstock.com/image-photo/stockholm-riddarholmen-old-town-night-260nw-2461909967.jpg')] bg-cover bg-center transition-transform duration-700 group-hover:scale-110"></div>
                    <div class="absolute inset-0 bg-gradient-to-br from-[#006AA7]/10 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-500"></div>
                    
                    <div class="absolute bottom-0 left-0 right-0 p-8 z-20">
                        <div class="flex items-center gap-2 mb-2">
                            <span class="px-3 py-1 rounded-full bg-[#006AA7]/20 text-[#006AA7] text-xs font-bold border border-[#006AA7]/30">CAPITAL</span>
                        </div>
                        <h3 class="text-4xl font-bold display-font mb-2 text-[#f5f1e8]">Stockholm</h3>
                        <p class="text-[#f5f1e8]/70 text-sm mb-4">Archipelago access. Gamla Stan transfers. Arlanda express alternative.</p>
                        <div class="flex items-center gap-4 text-xs text-[#f5f1e8]/50">
                            <span class="flex items-center gap-1">
                                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z"/></svg>
                                24h Service
                            </span>
                            <span class="flex items-center gap-1">
                                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z"/></svg>
                                Premium
                            </span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Booking Section -->
    <section id="booking" class="py-32 px-6 relative">
        <div class="max-w-4xl mx-auto">
            <div class="glass-strong rounded-[3rem] p-8 md:p-16 border border-[#d4af37]/20 relative overflow-hidden reveal">
                <div class="absolute inset-0 bg-gradient-to-br from-[#d4af37]/5 to-transparent"></div>
                
                <div class="relative z-10 text-center mb-12">
                    <h2 class="text-4xl md:text-6xl font-bold display-font mb-6">Request a Ride</h2>
                    <p class="text-lg text-[#f5f1e8]/70">Send us your travel details and we'll confirm your booking within 15 minutes.</p>
                </div>

                <form class="relative z-10 space-y-6" onsubmit="event.preventDefault(); alert('Thank you for your booking request. We will contact you shortly!');">
                    <div class="grid md:grid-cols-2 gap-6">
                        <div>
                            <label class="block text-sm font-medium text-[#f5f1e8]/70 mb-2">Full Name</label>
                            <input type="text" class="form-input w-full px-6 py-4 rounded-xl" placeholder="Your name" required>
                        </div>
                        <div>
                            <label class="block text-sm font-medium text-[#f5f1e8]/70 mb-2">Phone Number</label>
                            <input type="tel" class="form-input w-full px-6 py-4 rounded-xl" placeholder="+46 70 123 4567" required>
                        </div>
                    </div>

                    <div class="grid md:grid-cols-2 gap-6">
                        <div>
                            <label class="block text-sm font-medium text-[#f5f1e8]/70 mb-2">Pickup Location</label>
                            <input type="text" class="form-input w-full px-6 py-4 rounded-xl" placeholder="Address or airport" required>
                        </div>
                        <div>
                            <label class="block text-sm font-medium text-[#f5f1e8]/70 mb-2">Destination</label>
                            <input type="text" class="form-input w-full px-6 py-4 rounded-xl" placeholder="Where to?" required>
                        </div>
                    </div>

                    <div class="grid md:grid-cols-2 gap-6">
                        <div>
                            <label class="block text-sm font-medium text-[#f5f1e8]/70 mb-2">Date & Time</label>
                            <input type="datetime-local" class="form-input w-full px-6 py-4 rounded-xl" required>
                        </div>
                        <div>
                            <label class="block text-sm font-medium text-[#f5f1e8]/70 mb-2">Vehicle Preference</label>
                            <select class="form-input w-full px-6 py-4 rounded-xl">
                                <option value="">Select vehicle...</option>
                                <option value="corolla">Toyota Corolla (Hybrid)</option>
                                <option value="rav4">Toyota RAV4 (Hybrid AWD)</option>
                                <option value="c-class">Mercedes C-Class</option>
                                <option value="e-class">Mercedes E-Class</option>
                                <option value="xc60">Volvo XC60</option>
                            </select>
                        </div>
                    </div>

                    <div>
                        <label class="block text-sm font-medium text-[#f5f1e8]/70 mb-2">Additional Requests</label>
                        <textarea class="form-input w-full px-6 py-4 rounded-xl h-32" placeholder="Special requirements, flight number, etc."></textarea>
                    </div>

                    <div class="flex flex-col md:flex-row gap-4 items-center justify-between pt-6">
                        <div class="text-sm text-[#f5f1e8]/50">
                            Or email us directly at <a href="mailto:booking@hayatenterprise.se" class="text-[#d4af37] hover:underline">booking@hayatenterprise.se</a>
                        </div>
                        <button type="submit" class="magnetic-btn bg-[#d4af37] text-[#1a1209] px-10 py-4 rounded-full font-bold text-lg hover:shadow-[0_0_30px_rgba(212,175,55,0.4)] transition-all flex items-center gap-2 w-full md:w-auto justify-center">
                            Send Request
                            <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3"/>
                            </svg>
                        </button>
                    </div>
                </form>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="py-32 px-6">
        <div class="max-w-7xl mx-auto">
            <div class="grid md:grid-cols-3 gap-8 text-center">
                <div class="glass p-8 rounded-3xl reveal">
                    <div class="w-16 h-16 rounded-full bg-[#d4af37]/10 flex items-center justify-center mx-auto mb-6 border border-[#d4af37]/30">
                        <svg class="w-8 h-8 text-[#d4af37]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"/>
                        </svg>
                    </div>
                    <h3 class="text-xl font-bold mb-2 text-[#f5f1e8]">Email</h3>
                    <p class="text-[#f5f1e8]/60">booking@hayatenterprise.se</p>
                    <p class="text-[#f5f1e8]/60">info@hayatenterprise.se</p>
                </div>

                <div class="glass p-8 rounded-3xl reveal">
                    <div class="w-16 h-16 rounded-full bg-[#d4af37]/10 flex items-center justify-center mx-auto mb-6 border border-[#d4af37]/30">
                        <svg class="w-8 h-8 text-[#d4af37]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"/>
                        </svg>
                    </div>
                    <h3 class="text-xl font-bold mb-2 text-[#f5f1e8]">Phone</h3>
                    <p class="text-[#f5f1e8]/60">+46 70 123 4567</p>
                    <p class="text-[#f5f1e8]/60">24/7 Available</p>
                </div>

                <div class="glass p-8 rounded-3xl reveal">
                    <div class="w-16 h-16 rounded-full bg-[#d4af37]/10 flex items-center justify-center mx-auto mb-6 border border-[#d4af37]/30">
                        <svg class="w-8 h-8 text-[#d4af37]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"/>
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"/>
                        </svg>
                    </div>
                    <h3 class="text-xl font-bold mb-2 text-[#f5f1e8]">Service Area</h3>
                    <p class="text-[#f5f1e8]/60">Stockholm, Malmö, Kiruna</p>
                    <p class="text-[#f5f1e8]/60">All of Sweden</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="py-12 px-6 border-t border-[#d4af37]/10">
        <div class="max-w-7xl mx-auto flex flex-col md:flex-row justify-between items-center gap-6">
            <div class="flex items-center gap-4">
                <div class="w-10 h-10 rounded-lg bg-gradient-to-br from-[#2d1f12] to-[#4a3425] border border-[#d4af37]/30 flex items-center justify-center">
                    <span class="text-xl h-logo">H</span>
                </div>
                <div class="flex flex-col">
                    <span class="text-lg font-bold display-font text-[#f5f1e8]">Hayat Enterprise AB</span>
                    <span class="text-xs text-[#d4af37]/70">Premium Swedish Transport</span>
                </div>
            </div>
            
            <div class="flex gap-8 text-sm text-[#f5f1e8]/50">
                <a href="#" class="hover:text-[#d4af37] transition-colors">Privacy</a>
                <a href="#" class="hover:text-[#d4af37] transition-colors">Terms</a>
                <a href="#" class="hover:text-[#d4af37] transition-colors">Contact</a>
            </div>
            
            <div class="text-sm text-[#f5f1e8]/30">
                © 2026 Hayat Enterprise AB. All rights reserved.
            </div>
        </div>
    </footer>

    <script>
        // GSAP Animations
        gsap.registerPlugin(ScrollTrigger);
        
        // Reveal animations
        gsap.utils.toArray('.reveal').forEach((elem) => {
            gsap.fromTo(elem, 
                { opacity: 0, y: 30 },
                {
                    opacity: 1,
                    y: 0,
                    duration: 1,
                    ease: "power3.out",
                    scrollTrigger: {
                        trigger: elem,
                        start: "top 85%",
                        toggleActions: "play none none reverse"
                    }
                }
            );
        });
        
        // Navbar scroll effect
        const navbar = document.getElementById('navbar');
        window.addEventListener('scroll', () => {
            if (window.scrollY > 50) {
                navbar.classList.add('py-2');
                navbar.classList.remove('py-4');
            } else {
                navbar.classList.add('py-4');
                navbar.classList.remove('py-2');
            }
        });
        
        // Magnetic button effect
        document.querySelectorAll('.magnetic-btn').forEach(btn => {
            btn.addEventListener('mousemove', (e) => {
                const rect = btn.getBoundingClientRect();
                const x = e.clientX - rect.left - rect.width / 2;
                const y = e.clientY - rect.top - rect.height / 2;
                
                btn.style.transform = `translate(${x * 0.2}px, ${y * 0.2}px)`;
            });
            
            btn.addEventListener('mouseleave', () => {
                btn.style.transform = 'translate(0, 0)';
            });
        });
        
        // Parallax effect for aurora
        document.addEventListener('mousemove', (e) => {
            const mouseX = e.clientX / window.innerWidth - 0.5;
            const mouseY = e.clientY / window.innerHeight - 0.5;
            
            gsap.to('.aurora-wave', {
                x: mouseX * 50,
                y: mouseY * 50,
                duration: 1,
                ease: "power2.out"
            });
        });
    </script>
</body>
</html>
