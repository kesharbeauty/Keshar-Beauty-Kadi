<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Glamour Beauty Salon - Premium Beauty Services</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        body {
            box-sizing: border-box;
        }
        
        /* Custom gradient backgrounds with 3D effects */
        .hero-gradient {
            background: linear-gradient(135deg, #ff6b9d 0%, #c44569 25%, #f8b500 50%, #667eea 75%, #764ba2 100%);
            background-size: 400% 400%;
            animation: gradientShift 8s ease infinite;
            position: relative;
        }
        
        .hero-gradient::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: 
                radial-gradient(circle at 20% 80%, rgba(255, 255, 255, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 80% 20%, rgba(255, 255, 255, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 40% 40%, rgba(255, 255, 255, 0.05) 0%, transparent 50%);
            pointer-events: none;
        }
        
        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        
        .service-gradient {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }
        
        /* Advanced 3D Effects */
        .card-3d {
            transform-style: preserve-3d;
            perspective: 1000px;
            transition: all 0.6s cubic-bezier(0.23, 1, 0.320, 1);
        }
        
        .card-3d:hover {
            transform: rotateY(5deg) rotateX(5deg) translateZ(20px);
            box-shadow: 
                0 40px 80px rgba(0, 0, 0, 0.25),
                0 20px 40px rgba(0, 0, 0, 0.15),
                inset 0 1px 0 rgba(255, 255, 255, 0.3);
        }
        
        .package-card-3d {
            transform-style: preserve-3d;
            perspective: 1200px;
            transition: all 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            position: relative;
            overflow: hidden;
        }
        
        .package-card-3d::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.4), transparent);
            transition: left 0.8s;
        }
        
        .package-card-3d:hover::before {
            left: 100%;
        }
        
        .package-card-3d:hover {
            transform: translateY(-15px) rotateX(8deg) rotateY(-3deg) scale(1.02);
            box-shadow: 
                0 50px 100px rgba(0, 0, 0, 0.3),
                0 25px 50px rgba(0, 0, 0, 0.2),
                0 10px 20px rgba(0, 0, 0, 0.1),
                inset 0 2px 0 rgba(255, 255, 255, 0.4);
        }
        
        /* Floating animation with 3D */
        @keyframes float3d {
            0%, 100% { 
                transform: translateY(0px) rotateX(0deg) rotateY(0deg); 
            }
            25% { 
                transform: translateY(-8px) rotateX(2deg) rotateY(1deg); 
            }
            50% { 
                transform: translateY(-15px) rotateX(0deg) rotateY(-1deg); 
            }
            75% { 
                transform: translateY(-8px) rotateX(-2deg) rotateY(1deg); 
            }
        }
        
        .float-3d {
            animation: float3d 4s ease-in-out infinite;
        }
        
        /* Pulse glow effect */
        @keyframes pulseGlow {
            0%, 100% { 
                box-shadow: 0 0 20px rgba(255, 105, 180, 0.3);
            }
            50% { 
                box-shadow: 0 0 40px rgba(255, 105, 180, 0.6), 0 0 60px rgba(255, 105, 180, 0.4);
            }
        }
        
        .pulse-glow {
            animation: pulseGlow 2s ease-in-out infinite;
        }
        
        /* 3D Button Effects */
        .btn-3d {
            position: relative;
            transform-style: preserve-3d;
            transition: all 0.3s cubic-bezier(0.68, -0.55, 0.265, 1.55);
        }
        
        .btn-3d:hover {
            transform: translateY(-3px) rotateX(15deg);
            box-shadow: 
                0 15px 30px rgba(0, 0, 0, 0.3),
                0 5px 15px rgba(0, 0, 0, 0.2);
        }
        
        .btn-3d:active {
            transform: translateY(0px) rotateX(0deg);
            box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
        }
        
        /* Glass morphism enhanced */
        .glass-3d {
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(20px);
            border: 2px solid rgba(255, 255, 255, 0.3);
            box-shadow: 
                0 25px 45px rgba(0, 0, 0, 0.1),
                inset 0 1px 0 rgba(255, 255, 255, 0.4);
        }
        
        /* Gradient borders with 3D effect */
        .gradient-border-3d {
            position: relative;
            background: linear-gradient(145deg, #ffffff, #f0f0f0);
            border-radius: 20px;
        }
        
        .gradient-border-3d::before {
            content: '';
            position: absolute;
            inset: -3px;
            padding: 3px;
            background: linear-gradient(45deg, #ff6b9d, #c44569, #f8b500, #667eea);
            border-radius: inherit;
            mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
            mask-composite: exclude;
        }
        
        /* Price animation */
        @keyframes priceSlash {
            0% { transform: scaleX(0); }
            100% { transform: scaleX(1); }
        }
        
        .price-slash {
            position: relative;
        }
        
        .price-slash::after {
            content: '';
            position: absolute;
            top: 50%;
            left: 0;
            right: 0;
            height: 2px;
            background: #ef4444;
            transform: scaleX(0);
            animation: priceSlash 0.8s ease-out forwards;
            animation-delay: 0.5s;
        }
        
        /* Sparkle effect */
        @keyframes sparkle {
            0%, 100% { opacity: 0; transform: scale(0) rotate(0deg); }
            50% { opacity: 1; transform: scale(1) rotate(180deg); }
        }
        
        .sparkle::before {
            content: '✨';
            position: absolute;
            top: -10px;
            right: -10px;
            animation: sparkle 2s ease-in-out infinite;
        }
        
        /* Custom shadows enhanced */
        .shadow-luxury-3d {
            box-shadow: 
                0 35px 70px rgba(0, 0, 0, 0.2),
                0 15px 35px rgba(0, 0, 0, 0.15),
                0 5px 15px rgba(0, 0, 0, 0.1),
                inset 0 2px 0 rgba(255, 255, 255, 0.3);
        }
        
        /* Beauty-themed colors enhanced */
        .bg-rose-gold-3d {
            background: linear-gradient(145deg, #f7971e 0%, #ffd200 50%, #f7971e 100%);
            box-shadow: 
                0 20px 40px rgba(247, 151, 30, 0.3),
                inset 0 2px 0 rgba(255, 255, 255, 0.4);
        }
        
        .bg-pink-luxury-3d {
            background: linear-gradient(145deg, #ff9a9e 0%, #fecfef 50%, #ff9a9e 100%);
            box-shadow: 
                0 20px 40px rgba(255, 154, 158, 0.3),
                inset 0 2px 0 rgba(255, 255, 255, 0.4);
        }
        
        /* Discount badge 3D */
        .discount-badge-3d {
            position: absolute;
            top: -15px;
            right: -15px;
            background: linear-gradient(145deg, #ef4444, #dc2626);
            color: white;
            padding: 8px 16px;
            border-radius: 25px;
            font-weight: bold;
            font-size: 14px;
            transform: rotate(15deg);
            box-shadow: 
                0 10px 20px rgba(239, 68, 68, 0.4),
                0 5px 10px rgba(239, 68, 68, 0.3);
            animation: pulseGlow 2s ease-in-out infinite;
            z-index: 10;
        }
        
        /* Icon 3D effects */
        .icon-3d {
            transform-style: preserve-3d;
            transition: all 0.4s cubic-bezier(0.68, -0.55, 0.265, 1.55);
        }
        
        .icon-3d:hover {
            transform: rotateY(360deg) scale(1.1);
        }
        
        /* Additional 3D effects for special offer */
        .special-offer-3d {
            position: relative;
            transform-style: preserve-3d;
        }
        
        .special-offer-3d::after {
            content: '';
            position: absolute;
            inset: -5px;
            background: linear-gradient(45deg, #ff6b9d, #c44569, #f8b500, #667eea, #764ba2);
            border-radius: inherit;
            z-index: -1;
            opacity: 0.7;
            filter: blur(10px);
            animation: rotateGlow 3s linear infinite;
        }
        
        @keyframes rotateGlow {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        .pulse-glow-intense {
            animation: pulseGlowIntense 1.5s ease-in-out infinite;
        }
        
        @keyframes pulseGlowIntense {
            0%, 100% { 
                box-shadow: 0 0 30px rgba(255, 105, 180, 0.5), 0 0 60px rgba(255, 105, 180, 0.3);
                transform: scale(1);
            }
            50% { 
                box-shadow: 0 0 50px rgba(255, 105, 180, 0.8), 0 0 100px rgba(255, 105, 180, 0.5);
                transform: scale(1.05);
            }
        }
        
        .sparkle-bg {
            background-image: 
                radial-gradient(2px 2px at 20px 30px, #fff, transparent),
                radial-gradient(2px 2px at 40px 70px, rgba(255,255,255,0.8), transparent),
                radial-gradient(1px 1px at 90px 40px, #fff, transparent),
                radial-gradient(1px 1px at 130px 80px, rgba(255,255,255,0.6), transparent);
            background-repeat: repeat;
            background-size: 150px 100px;
            animation: sparkleMove 4s linear infinite;
        }
        
        @keyframes sparkleMove {
            0% { background-position: 0 0, 0 0, 0 0, 0 0; }
            100% { background-position: 150px 100px, -150px -100px, 75px 50px, -75px -50px; }
        }
        
        .border-gradient-rainbow {
            border-image: linear-gradient(45deg, #ff6b9d, #c44569, #f8b500, #667eea, #764ba2) 1;
        }
        
        .sanskrit-blessing {
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
            font-family: 'Devanagari', serif;
        }
    </style>
</head>
<body class="bg-gray-50">
    <!-- Navigation -->
    <nav class="fixed w-full top-0 z-50 bg-white shadow-lg">
        <div class="max-w-7xl mx-auto px-6 py-4">
            <div class="flex justify-between items-center">
                <div class="flex items-center space-x-3">
                    <!-- Keshar Beauty Logo -->
                    <div class="w-12 h-12 rounded-full overflow-hidden shadow-lg bg-gradient-to-br from-orange-400 via-yellow-500 to-pink-500 flex items-center justify-center relative">
                        <!-- Beautiful Custom SVG Logo for Keshar Beauty Kadi -->
                        <svg class="w-10 h-10" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
                            <!-- Background circle with gradient -->
                            <defs>
                                <radialGradient id="logoGrad" cx="50%" cy="30%" r="70%">
                                    <stop offset="0%" style="stop-color:#FFD700;stop-opacity:1" />
                                    <stop offset="50%" style="stop-color:#FF6B9D;stop-opacity:1" />
                                    <stop offset="100%" style="stop-color:#8B5CF6;stop-opacity:1" />
                                </radialGradient>
                                <filter id="glow">
                                    <feGaussianBlur stdDeviation="2" result="coloredBlur"/>
                                    <feMerge> 
                                        <feMergeNode in="coloredBlur"/>
                                        <feMergeNode in="SourceGraphic"/>
                                    </feMerge>
                                </filter>
                            </defs>
                            
                            <!-- Main logo circle -->
                            <circle cx="50" cy="50" r="45" fill="url(#logoGrad)" filter="url(#glow)"/>
                            
                            <!-- Stylized "K" for Keshar -->
                            <path d="M25 25 L25 75 M25 45 L45 25 M25 50 L45 75" stroke="white" stroke-width="4" stroke-linecap="round" fill="none" opacity="0.9"/>
                            
                            <!-- Beauty symbol - stylized flower/lotus -->
                            <circle cx="65" cy="35" r="8" fill="white" opacity="0.8"/>
                            <path d="M65 27 Q70 30 65 35 Q60 30 65 27" fill="white" opacity="0.9"/>
                            <path d="M65 35 Q70 40 65 43 Q60 40 65 35" fill="white" opacity="0.9"/>
                            <path d="M57 35 Q60 30 65 35 Q60 40 57 35" fill="white" opacity="0.9"/>
                            <path d="M73 35 Q70 30 65 35 Q70 40 73 35" fill="white" opacity="0.9"/>
                            
                            <!-- Decorative dots -->
                            <circle cx="35" cy="65" r="2" fill="white" opacity="0.7"/>
                            <circle cx="75" cy="65" r="3" fill="white" opacity="0.6"/>
                            <circle cx="70" cy="20" r="2" fill="white" opacity="0.8"/>
                            
                            <!-- Sparkle effects -->
                            <path d="M20 20 L22 18 L20 16 L18 18 Z" fill="white" opacity="0.9"/>
                            <path d="M80 75 L82 73 L80 71 L78 73 Z" fill="white" opacity="0.8"/>
                            <path d="M85 25 L86 24 L85 23 L84 24 Z" fill="white" opacity="0.7"/>
                        </svg>
                        
                        <!-- Animated decorative elements -->
                        <div class="absolute -top-1 -right-1 w-3 h-3 bg-yellow-300 rounded-full opacity-80 animate-pulse"></div>
                        <div class="absolute -bottom-1 -left-1 w-2 h-2 bg-pink-300 rounded-full opacity-60 animate-bounce"></div>
                        <div class="absolute top-0 left-0 w-2 h-2 bg-white rounded-full opacity-50 animate-ping"></div>
                    </div>
                    <div>
                        <span class="text-2xl font-bold text-gray-800">Keshar Beauty</span>
                        <div class="text-sm text-pink-500 font-medium -mt-1">Kadi</div>
                    </div>
                </div>
                
                <div class="hidden md:flex space-x-8">
                    <a href="#home" class="text-gray-700 hover:text-pink-500 transition-colors font-medium">Home</a>
                    <a href="#services" class="text-gray-700 hover:text-pink-500 transition-colors font-medium">Services</a>
                    <a href="#gallery" class="text-gray-700 hover:text-pink-500 transition-colors font-medium">Gallery</a>
                    <a href="#about" class="text-gray-700 hover:text-pink-500 transition-colors font-medium">About</a>
                    <a href="#contact" class="text-gray-700 hover:text-pink-500 transition-colors font-medium">Contact</a>
                </div>
                
                <button class="bg-pink-500 text-white px-6 py-2 rounded-full hover:bg-pink-600 transition-colors font-medium">
                    Book Now
                </button>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero-gradient min-h-screen flex items-center pt-20">
        <div class="max-w-7xl mx-auto px-6 grid md:grid-cols-2 gap-12 items-center">
            <div class="text-white">
                <p class="text-yellow-300 text-xl font-semibold sanskrit-blessing mb-6 text-center">॥ श्री टहुका नी चेहर कृपा ॥</p>
                <h1 class="text-5xl md:text-7xl font-bold mb-6 leading-tight">
                    Welcome to
                    <span class="block text-yellow-300">"Keshar Beauty Kadi"</span>
                </h1>
                <p class="text-xl mb-8 text-gray-100">
                    Where beauty meets care. We offer a wide range of professional beauty, hair and skin services tailored to bring out the best version of you. Whether you are getting ready for a special occasion or just want to treat yourself, our expert team is here to make you feel pampered, refreshed, and confident experience at our salon.
                </p>
                <div class="flex flex-col sm:flex-row gap-6">
                    <button onclick="openBookingModal()" class="group bg-gradient-to-r from-white to-gray-100 text-pink-600 px-10 py-5 rounded-full font-bold hover:from-pink-50 hover:to-white transition-all shadow-luxury-3d btn-3d transform hover:scale-105 relative overflow-hidden">
                        <span class="relative z-10 flex items-center justify-center space-x-2">
                            <span class="text-2xl group-hover:animate-bounce">📅</span>
                            <span class="text-lg">Book Appointment</span>
                        </span>
                        <div class="absolute inset-0 bg-gradient-to-r from-pink-400 to-purple-500 opacity-0 group-hover:opacity-20 transition-opacity"></div>
                    </button>
                    <button onclick="document.getElementById('services').scrollIntoView({behavior: 'smooth'})" class="group border-3 border-white text-white px-10 py-5 rounded-full font-bold hover:bg-white hover:text-pink-600 transition-all shadow-luxury-3d btn-3d transform hover:scale-105 relative overflow-hidden">
                        <span class="relative z-10 flex items-center justify-center space-x-2">
                            <span class="text-2xl group-hover:animate-spin">✨</span>
                            <span class="text-lg">View Services</span>
                        </span>
                        <div class="absolute inset-0 bg-gradient-to-r from-white to-gray-100 opacity-0 group-hover:opacity-100 transition-opacity"></div>
                    </button>
                </div>
            </div>
            
            <div class="relative">
                <div class="glass-3d rounded-3xl p-8 float-3d special-offer-3d">
                    <div class="bg-gradient-to-br from-white via-pink-50 to-purple-50 rounded-2xl p-6 shadow-luxury-3d border-2 border-gradient-rainbow relative overflow-hidden">
                        <!-- Animated background sparkles -->
                        <div class="absolute inset-0 sparkle-bg"></div>
                        
                        <!-- Pulsing 30% OFF badge -->
                        <div class="absolute -top-4 -right-4 bg-gradient-to-r from-red-500 to-orange-500 text-white px-6 py-3 rounded-full font-bold text-lg transform rotate-12 pulse-glow-intense animate-bounce">
                            30% OFF!
                        </div>
                        
                        <div class="relative z-10">
                            <h3 class="text-3xl font-bold bg-gradient-to-r from-pink-600 to-purple-600 bg-clip-text text-transparent mb-4 animate-pulse">
                                ✨ MEGA SPECIAL OFFER ✨
                            </h3>
                            <p class="text-xl font-semibold text-gray-700 mb-6 animate-bounce">
                                🎉 Get 30% OFF on your first visit! 🎉
                            </p>
                            <div class="flex items-center space-x-4 bg-gradient-to-r from-pink-100 to-purple-100 rounded-xl p-4">
                                <div class="w-16 h-16 bg-gradient-to-br from-pink-500 to-purple-600 rounded-full flex items-center justify-center icon-3d pulse-glow">
                                    <span class="text-3xl">💄</span>
                                </div>
                                <div>
                                    <p class="font-bold text-gray-800 text-lg">Premium Makeover</p>
                                    <p class="text-sm text-gray-600">Complete luxury beauty package</p>
                                    <p class="text-xs text-green-600 font-semibold mt-1">💰 Save Thousands!</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section id="services" class="py-20 bg-white">
        <div class="max-w-7xl mx-auto px-6">
            <div class="text-center mb-16">
                <h2 class="text-4xl md:text-5xl font-bold text-gray-800 mb-6">Our Services</h2>
                <p class="text-xl text-gray-600 max-w-3xl mx-auto mb-4">
                    Keshar Beauty Kadi Services - Keep your skin looking beautiful
                </p>
                <div class="bg-gradient-to-r from-pink-100 to-purple-100 rounded-2xl p-6 max-w-4xl mx-auto">
                    <p class="text-lg font-semibold text-gray-800 mb-2">✨ Bridal Makeup Specialists ✨</p>
                    <p class="text-gray-700">We are highly specialized in makeup and bridal related premium services, making your special day absolutely perfect</p>
                </div>
            </div>
            
            <div class="grid md:grid-cols-3 gap-8">
                <!-- Makeup & Nails Services -->
                <div class="card-3d gradient-border-3d bg-gradient-to-br from-yellow-50 to-orange-50 rounded-3xl p-8 shadow-luxury-3d relative sparkle">
                    <div class="w-20 h-20 bg-rose-gold-3d rounded-full flex items-center justify-center mb-6 icon-3d float-3d">
                        <span class="text-4xl">💄</span>
                    </div>
                    <h3 class="text-2xl font-bold text-gray-800 mb-4">Makeup & Nails</h3>
                    <p class="text-gray-600 mb-6">Professional makeup and nail services including manicure & pedicure</p>
                    <ul class="space-y-3 text-gray-600 mb-6">
                        <li class="flex items-center"><span class="text-orange-500 mr-3 text-lg">💫</span> <strong>HD & Airbrush Makeup</strong></li>
                        <li class="flex items-center"><span class="text-orange-500 mr-3 text-lg">💅</span> Luxury Manicure & Pedicure</li>
                        <li class="flex items-center"><span class="text-orange-500 mr-3 text-lg">🎨</span> Professional Nail Art</li>
                        <li class="flex items-center"><span class="text-orange-500 mr-3 text-lg">👰</span> Bridal Makeup Specialist</li>
                        <li class="flex items-center"><span class="text-orange-500 mr-3 text-lg">🎉</span> Party & Event Makeup</li>
                        <li class="flex items-center"><span class="text-orange-500 mr-3 text-lg">✨</span> Professional Styling</li>
                    </ul>
                    <button class="w-full bg-orange-500 text-white py-4 rounded-full hover:bg-orange-600 transition-colors font-medium btn-3d">
                        Book Makeup Service
                    </button>
                </div>

                <!-- Hair Cut & Styling Services -->
                <div class="card-3d gradient-border-3d bg-gradient-to-br from-pink-50 to-purple-50 rounded-3xl p-8 shadow-luxury-3d relative sparkle">
                    <div class="w-20 h-20 bg-pink-luxury-3d rounded-full flex items-center justify-center mb-6 icon-3d float-3d">
                        <span class="text-4xl">💇‍♀</span>
                    </div>
                    <h3 class="text-2xl font-bold text-gray-800 mb-4">Hair Cut & Styling</h3>
                    <p class="text-gray-600 mb-6">Professional hair cuts and styling services for all hair types</p>
                    <ul class="space-y-3 text-gray-600 mb-6">
                        <li class="flex items-center"><span class="text-pink-500 mr-3 text-lg">✂</span> Expert Hair Cutting</li>
                        <li class="flex items-center"><span class="text-pink-500 mr-3 text-lg">🌟</span> Advanced Hair Styling</li>
                        <li class="flex items-center"><span class="text-pink-500 mr-3 text-lg">💆‍♀</span> Hair Spa & Treatments</li>
                        <li class="flex items-center"><span class="text-pink-500 mr-3 text-lg">👑</span> Bridal Hair Design</li>
                        <li class="flex items-center"><span class="text-pink-500 mr-3 text-lg">🌸</span> Hair Extensions</li>
                        <li class="flex items-center"><span class="text-pink-500 mr-3 text-lg">🎀</span> Hair Accessories</li>
                    </ul>
                    <button class="w-full bg-pink-500 text-white py-4 rounded-full hover:bg-pink-600 transition-colors font-medium btn-3d">
                        Book Hair Service
                    </button>
                </div>

                <!-- Facial & Waxing Services -->
                <div class="card-3d gradient-border-3d bg-gradient-to-br from-blue-50 to-indigo-50 rounded-3xl p-8 shadow-luxury-3d relative sparkle">
                    <div class="w-20 h-20 service-gradient rounded-full flex items-center justify-center mb-6 icon-3d float-3d shadow-luxury-3d">
                        <span class="text-4xl">✨</span>
                    </div>
                    <h3 class="text-2xl font-bold text-gray-800 mb-4">Facial & Waxing</h3>
                    <p class="text-gray-600 mb-6">Professional facial treatments and waxing services for smooth, glowing skin</p>
                    <ul class="space-y-3 text-gray-600 mb-6">
                        <li class="flex items-center"><span class="text-indigo-500 mr-3 text-lg">🧴</span> O3+ Premium Facials</li>
                        <li class="flex items-center"><span class="text-indigo-500 mr-3 text-lg">💎</span> Diamond Facial Treatment</li>
                        <li class="flex items-center"><span class="text-indigo-500 mr-3 text-lg">🌿</span> Full Body Waxing</li>
                        <li class="flex items-center"><span class="text-indigo-500 mr-3 text-lg">🧖‍♀</span> Eyebrow & Threading</li>
                        <li class="flex items-center"><span class="text-indigo-500 mr-3 text-lg">🌟</span> Body Bleach & Polish</li>
                        <li class="flex items-center"><span class="text-indigo-500 mr-3 text-lg">💆‍♀</span> Deep Cleansing</li>
                    </ul>
                    <button class="w-full bg-indigo-500 text-white py-4 rounded-full hover:bg-indigo-600 transition-colors font-medium btn-3d">
                        Book Facial Service
                    </button>
                </div>
            </div>
        </div>
    </section>

    <!-- Bridal Packages Section -->
    <section class="py-20 bg-gradient-to-br from-pink-50 via-purple-50 to-indigo-50">
        <div class="max-w-7xl mx-auto px-6">
            <div class="text-center mb-16">
                <h2 class="text-4xl md:text-5xl font-bold text-gray-800 mb-6">Keshar Beauty Premium & Diamond Packages</h2>
                <p class="text-xl text-gray-600 max-w-3xl mx-auto mb-4">
                    Amazing Experience Services - Make your special day unforgettable
                </p>
                <div class="bg-gradient-to-r from-red-500 to-orange-500 text-white rounded-2xl p-4 max-w-md mx-auto">
                    <p class="text-2xl font-bold">🎉 30% OFF on All Packages! 🎉</p>
                </div>
            </div>
            
            <!-- Main Bridal Packages -->
            <div class="grid lg:grid-cols-3 md:grid-cols-2 gap-6 mb-12">
                <!-- ₹7,000 Package (30% OFF from ₹10,000) -->
                <div class="package-card-3d gradient-border-3d bg-white rounded-3xl p-6 shadow-luxury-3d relative">
                    <div class="discount-badge-3d">30% OFF</div>
                    <div class="text-center mb-4">
                        <div class="w-20 h-20 bg-gradient-to-br from-pink-400 to-purple-500 rounded-full flex items-center justify-center mx-auto mb-3 icon-3d pulse-glow">
                            <span class="text-3xl">👰</span>
                        </div>
                        <h3 class="text-xl font-bold text-gray-800 mb-2">Essential Bridal</h3>
                        <div class="flex items-center justify-center space-x-2 mb-2">
                            <span class="text-lg text-gray-400 line-through price-slash">₹10,000</span>
                            <span class="text-2xl font-bold text-pink-600">₹7,000/-</span>
                        </div>
                        <p class="text-sm text-green-600 font-semibold">💰 Save ₹3,000!</p>
                    </div>
                    <ul class="space-y-2 text-sm text-gray-600 mb-6">
                        <li class="flex items-center"><span class="text-pink-500 mr-2 text-lg">💄</span> HD Makeup</li>
                        <li class="flex items-center"><span class="text-pink-500 mr-2 text-lg">💇‍♀</span> Hair Style (Broach)</li>
                        <li class="flex items-center"><span class="text-pink-500 mr-2 text-lg">💎</span> Bridal Jewelry</li>
                        <li class="flex items-center"><span class="text-pink-500 mr-2 text-lg">👁</span> Lenses & Eyelashes</li>
                        <li class="flex items-center"><span class="text-pink-500 mr-2 text-lg">👗</span> Saree Draping</li>
                        <li class="flex items-center"><span class="text-pink-500 mr-2 text-lg">🧖‍♀</span> Eye Brow & Threading</li>
                    </ul>
                    <button class="w-full bg-pink-500 text-white py-3 rounded-full hover:bg-pink-600 transition-colors font-medium text-sm btn-3d">
                        Book ₹7,000 Package
                    </button>
                </div>

                <!-- ₹10,500 Package (30% OFF from ₹15,000) -->
                <div class="package-card-3d gradient-border-3d bg-white rounded-3xl p-6 shadow-luxury-3d relative">
                    <div class="discount-badge-3d">30% OFF</div>
                    <div class="text-center mb-4">
                        <div class="w-20 h-20 bg-gradient-to-br from-purple-500 to-pink-600 rounded-full flex items-center justify-center mx-auto mb-3 icon-3d pulse-glow">
                            <span class="text-3xl">💎</span>
                        </div>
                        <h3 class="text-xl font-bold text-gray-800 mb-2">Premium Bridal</h3>
                        <div class="flex items-center justify-center space-x-2 mb-2">
                            <span class="text-lg text-gray-400 line-through price-slash">₹15,000</span>
                            <span class="text-2xl font-bold text-purple-600">₹10,500/-</span>
                        </div>
                        <p class="text-sm text-green-600 font-semibold">💰 Save ₹4,500!</p>
                    </div>
                    <ul class="space-y-2 text-sm text-gray-600 mb-6">
                        <li class="flex items-center"><span class="text-purple-500 mr-2 text-lg">💄</span> HD Makeup</li>
                        <li class="flex items-center"><span class="text-purple-500 mr-2 text-lg">💇‍♀</span> Hair Style (Broach)</li>
                        <li class="flex items-center"><span class="text-purple-500 mr-2 text-lg">💎</span> Bridal Jewelry</li>
                        <li class="flex items-center"><span class="text-purple-500 mr-2 text-lg">👁</span> Lenses & Eyelashes</li>
                        <li class="flex items-center"><span class="text-purple-500 mr-2 text-lg">👗</span> Saree Draping</li>
                        <li class="flex items-center"><span class="text-purple-500 mr-2 text-lg">✨</span> Clean Up</li>
                        <li class="flex items-center"><span class="text-purple-500 mr-2 text-lg">🌿</span> Waxing (Hand)</li>
                        <li class="flex items-center"><span class="text-purple-500 mr-2 text-lg">🧖‍♀</span> Eye Brow & Threading</li>
                    </ul>
                    <button class="w-full bg-purple-500 text-white py-3 rounded-full hover:bg-purple-600 transition-colors font-medium text-sm btn-3d">
                        Book ₹10,500 Package
                    </button>
                </div>

                <!-- ₹14,000 Package (30% OFF from ₹20,000) -->
                <div class="package-card-3d gradient-border-3d bg-white rounded-3xl p-6 shadow-luxury-3d relative">
                    <div class="discount-badge-3d">30% OFF</div>
                    <div class="text-center mb-4">
                        <div class="w-20 h-20 bg-gradient-to-br from-blue-500 to-indigo-600 rounded-full flex items-center justify-center mx-auto mb-3 icon-3d pulse-glow">
                            <span class="text-3xl">👑</span>
                        </div>
                        <h3 class="text-xl font-bold text-gray-800 mb-2">Luxury Bridal</h3>
                        <div class="flex items-center justify-center space-x-2 mb-2">
                            <span class="text-lg text-gray-400 line-through price-slash">₹20,000</span>
                            <span class="text-2xl font-bold text-blue-600">₹14,000/-</span>
                        </div>
                        <p class="text-sm text-green-600 font-semibold">💰 Save ₹6,000!</p>
                    </div>
                    <ul class="space-y-2 text-sm text-gray-600 mb-6">
                        <li class="flex items-center"><span class="text-blue-500 mr-2 text-lg">💄</span> HD Makeup</li>
                        <li class="flex items-center"><span class="text-blue-500 mr-2 text-lg">💇‍♀</span> Advance Hair Style (Broach)</li>
                        <li class="flex items-center"><span class="text-blue-500 mr-2 text-lg">💎</span> Bridal Jewelry</li>
                        <li class="flex items-center"><span class="text-blue-500 mr-2 text-lg">👁</span> Lenses & Eyelashes</li>
                        <li class="flex items-center"><span class="text-blue-500 mr-2 text-lg">👗</span> Saree Draping</li>
                        <li class="flex items-center"><span class="text-blue-500 mr-2 text-lg">🧴</span> Bridal Facial (One Time)</li>
                        <li class="flex items-center"><span class="text-blue-500 mr-2 text-lg">🧖‍♀</span> Eye Brow & Threading</li>
                        <li class="flex items-center"><span class="text-blue-500 mr-2 text-lg">🌿</span> Waxing</li>
                    </ul>
                    <button class="w-full bg-blue-500 text-white py-3 rounded-full hover:bg-blue-600 transition-colors font-medium text-sm btn-3d">
                        Book ₹14,000 Package
                    </button>
                </div>

                <!-- ₹17,500 Package (30% OFF from ₹25,000) -->
                <div class="package-card-3d gradient-border-3d bg-white rounded-3xl p-6 shadow-luxury-3d relative">
                    <div class="discount-badge-3d">30% OFF</div>
                    <div class="text-center mb-4">
                        <div class="w-20 h-20 bg-gradient-to-br from-green-500 to-teal-600 rounded-full flex items-center justify-center mx-auto mb-3 icon-3d pulse-glow">
                            <span class="text-3xl">✨</span>
                        </div>
                        <h3 class="text-xl font-bold text-gray-800 mb-2">Royal Bridal</h3>
                        <div class="flex items-center justify-center space-x-2 mb-2">
                            <span class="text-lg text-gray-400 line-through price-slash">₹25,000</span>
                            <span class="text-2xl font-bold text-green-600">₹17,500/-</span>
                        </div>
                        <p class="text-sm text-green-600 font-semibold">💰 Save ₹7,500!</p>
                    </div>
                    <ul class="space-y-2 text-sm text-gray-600 mb-6">
                        <li class="flex items-center"><span class="text-green-500 mr-2 text-lg">💄</span> HD Makeup</li>
                        <li class="flex items-center"><span class="text-green-500 mr-2 text-lg">💇‍♀</span> Advance Hair Style (Broach)</li>
                        <li class="flex items-center"><span class="text-green-500 mr-2 text-lg">💎</span> Bridal Jewelry</li>
                        <li class="flex items-center"><span class="text-green-500 mr-2 text-lg">👁</span> Lenses & Eyelashes</li>
                        <li class="flex items-center"><span class="text-green-500 mr-2 text-lg">👗</span> Saree Draping</li>
                        <li class="flex items-center"><span class="text-green-500 mr-2 text-lg">🧴</span> Bridal Facial (Two Times)</li>
                        <li class="flex items-center"><span class="text-green-500 mr-2 text-lg">🌟</span> Body Bleach & Polishing</li>
                        <li class="flex items-center"><span class="text-green-500 mr-2 text-lg">🌿</span> Waxing</li>
                        <li class="flex items-center"><span class="text-green-500 mr-2 text-lg">🧖‍♀</span> Eye Brow & Threading</li>
                    </ul>
                    <button class="w-full bg-green-500 text-white py-3 rounded-full hover:bg-green-600 transition-colors font-medium text-sm btn-3d">
                        Book ₹17,500 Package
                    </button>
                </div>

                <!-- ₹19,600 Package (30% OFF from ₹28,000) -->
                <div class="package-card-3d gradient-border-3d bg-white rounded-3xl p-6 shadow-luxury-3d relative">
                    <div class="absolute -top-3 left-1/2 transform -translate-x-1/2">
                        <span class="bg-gradient-to-r from-orange-500 to-red-500 text-white px-4 py-2 rounded-full text-sm font-bold pulse-glow">Most Popular</span>
                    </div>
                    <div class="discount-badge-3d">30% OFF</div>
                    <div class="text-center mb-4 mt-4">
                        <div class="w-20 h-20 bg-gradient-to-br from-orange-500 to-red-600 rounded-full flex items-center justify-center mx-auto mb-3 icon-3d pulse-glow">
                            <span class="text-3xl">🌟</span>
                        </div>
                        <h3 class="text-xl font-bold text-gray-800 mb-2">Diamond Bridal</h3>
                        <div class="flex items-center justify-center space-x-2 mb-2">
                            <span class="text-lg text-gray-400 line-through price-slash">₹28,000</span>
                            <span class="text-2xl font-bold text-orange-600">₹19,600/-</span>
                        </div>
                        <p class="text-sm text-green-600 font-semibold">💰 Save ₹8,400!</p>
                    </div>
                    <ul class="space-y-1 text-xs text-gray-600 mb-6">
                        <li class="flex items-center"><span class="text-orange-500 mr-2 text-sm">💫</span> Advance Makeup</li>
                        <li class="flex items-center"><span class="text-orange-500 mr-2 text-sm">💇‍♀</span> Advance Hair Style</li>
                        <li class="flex items-center"><span class="text-orange-500 mr-2 text-sm">🌸</span> Hair Accessories & Real Flower</li>
                        <li class="flex items-center"><span class="text-orange-500 mr-2 text-sm">💎</span> Bridal Jewelry</li>
                        <li class="flex items-center"><span class="text-orange-500 mr-2 text-sm">👁</span> Lenses & Eyelashes</li>
                        <li class="flex items-center"><span class="text-orange-500 mr-2 text-sm">👗</span> Saree Draping</li>
                        <li class="flex items-center"><span class="text-orange-500 mr-2 text-sm">🧴</span> Bridal Facial (3 Times with O3 Plus)</li>
                        <li class="flex items-center"><span class="text-orange-500 mr-2 text-sm">🌟</span> Body Bleach & Polishing</li>
                        <li class="flex items-center"><span class="text-orange-500 mr-2 text-sm">🌿</span> Full Body Waxing</li>
                        <li class="flex items-center"><span class="text-orange-500 mr-2 text-sm">💅</span> Manicure & Pedicure</li>
                        <li class="flex items-center"><span class="text-orange-500 mr-2 text-sm">🧖‍♀</span> Eye Brow & Threading</li>
                        <li class="flex items-center"><span class="text-orange-500 mr-2 text-sm">👰</span> Mandva Bridal Look</li>
                        <li class="flex items-center"><span class="text-orange-500 mr-2 text-sm">💃</span> Sangeet Bridal Look</li>
                        <li class="flex items-center"><span class="text-orange-500 mr-2 text-sm">🎨</span> Nail Art</li>
                    </ul>
                    <button class="w-full bg-orange-500 text-white py-3 rounded-full hover:bg-orange-600 transition-colors font-medium text-sm btn-3d">
                        Book ₹19,600 Package
                    </button>
                </div>

                <!-- Gold Bridal Package ₹23,100 (30% OFF from ₹33,000) -->
                <div class="package-card-3d gradient-border-3d bg-gradient-to-br from-yellow-50 to-orange-50 rounded-3xl p-6 shadow-luxury-3d relative">
                    <div class="discount-badge-3d">30% OFF</div>
                    <div class="text-center mb-4">
                        <div class="w-20 h-20 bg-gradient-to-br from-yellow-400 to-orange-500 rounded-full flex items-center justify-center mx-auto mb-3 icon-3d pulse-glow">
                            <span class="text-3xl">🏆</span>
                        </div>
                        <h3 class="text-xl font-bold text-gray-800 mb-2">Gold Bridal Package</h3>
                        <div class="flex items-center justify-center space-x-2 mb-2">
                            <span class="text-lg text-gray-400 line-through price-slash">₹33,000</span>
                            <span class="text-2xl font-bold text-yellow-600">₹23,100/-</span>
                        </div>
                        <p class="text-sm text-green-600 font-semibold">💰 Save ₹9,900!</p>
                    </div>
                    <ul class="space-y-1 text-xs text-gray-600 mb-6">
                        <li class="flex items-center"><span class="text-yellow-500 mr-2 text-sm">✨</span> Air Brush & Advance Makeup</li>
                        <li class="flex items-center"><span class="text-yellow-500 mr-2 text-sm">💇‍♀</span> Advance Hair Style</li>
                        <li class="flex items-center"><span class="text-yellow-500 mr-2 text-sm">🌸</span> Hair Accessories & Real Flower</li>
                        <li class="flex items-center"><span class="text-yellow-500 mr-2 text-sm">💎</span> Bridal Jewelry</li>
                        <li class="flex items-center"><span class="text-yellow-500 mr-2 text-sm">👁</span> Lenses & Eyelashes</li>
                        <li class="flex items-center"><span class="text-yellow-500 mr-2 text-sm">👗</span> Saree Draping</li>
                        <li class="flex items-center"><span class="text-yellow-500 mr-2 text-sm">🧴</span> Bridal Facial (3 Times with O3 Plus)</li>
                        <li class="flex items-center"><span class="text-yellow-500 mr-2 text-sm">🌟</span> Body Bleach & Polishing</li>
                        <li class="flex items-center"><span class="text-yellow-500 mr-2 text-sm">🌿</span> Full Body Waxing</li>
                        <li class="flex items-center"><span class="text-yellow-500 mr-2 text-sm">💆‍♀</span> Bikini Wax</li>
                        <li class="flex items-center"><span class="text-yellow-500 mr-2 text-sm">🎨</span> Bride Mehndi</li>
                        <li class="flex items-center"><span class="text-yellow-500 mr-2 text-sm">💅</span> Manicure & Pedicure</li>
                        <li class="flex items-center"><span class="text-yellow-500 mr-2 text-sm">🧖‍♀</span> Eye Brow & Threading</li>
                        <li class="flex items-center"><span class="text-yellow-500 mr-2 text-sm">👰</span> Mandva Bridal Look</li>
                        <li class="flex items-center"><span class="text-yellow-500 mr-2 text-sm">💃</span> Sangeet Bridal Look</li>
                        <li class="flex items-center"><span class="text-yellow-500 mr-2 text-sm">🌼</span> Haldi Bridal Look</li>
                        <li class="flex items-center"><span class="text-yellow-500 mr-2 text-sm">💎</span> Bridal Jewelry for All Time</li>
                        <li class="flex items-center"><span class="text-yellow-500 mr-2 text-sm">🎨</span> Nail Art</li>
                    </ul>
                    <button class="w-full bg-yellow-500 text-white py-3 rounded-full hover:bg-yellow-600 transition-colors font-medium text-sm btn-3d">
                        Book Gold Package ₹23,100
                    </button>
                </div>
            </div>

            <!-- Reception & Side Packages -->
            <div class="package-card-3d gradient-border-3d bg-white rounded-3xl p-8 shadow-luxury-3d mb-8">
                <h3 class="text-3xl font-bold text-gray-800 mb-8 text-center">🎉 Reception & Side Packages - 30% OFF! 🎉</h3>
                <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
                    <!-- Reception Package ₹6,300 (30% OFF from ₹9,000) -->
                    <div class="package-card-3d gradient-border-3d bg-gradient-to-br from-purple-50 to-pink-50 rounded-2xl p-6 shadow-luxury-3d relative">
                        <div class="discount-badge-3d">30% OFF</div>
                        <div class="text-center mb-4">
                            <div class="w-16 h-16 bg-gradient-to-br from-purple-500 to-pink-600 rounded-full flex items-center justify-center mx-auto mb-3 icon-3d">
                                <span class="text-2xl">🎭</span>
                            </div>
                            <h4 class="text-lg font-bold text-gray-800 mb-2">Reception Package</h4>
                            <div class="flex items-center justify-center space-x-2 mb-2">
                                <span class="text-sm text-gray-400 line-through price-slash">₹9,000</span>
                                <span class="text-xl font-bold text-purple-600">₹6,300/-</span>
                            </div>
                            <p class="text-xs text-green-600 font-semibold">💰 Save ₹2,700!</p>
                        </div>
                        <ul class="space-y-2 text-sm text-gray-600">
                            <li class="flex items-center"><span class="text-purple-500 mr-2 text-lg">💫</span> Advance Makeup</li>
                            <li class="flex items-center"><span class="text-purple-500 mr-2 text-lg">💇‍♀</span> Advance Hair Style (Hair Extension)</li>
                            <li class="flex items-center"><span class="text-purple-500 mr-2 text-lg">👗</span> Saree Draping</li>
                            <li class="flex items-center"><span class="text-purple-500 mr-2 text-lg">🎀</span> Broach</li>
                            <li class="flex items-center"><span class="text-purple-500 mr-2 text-lg">🌸</span> Real Flower</li>
                        </ul>
                        <button class="w-full bg-purple-500 text-white py-3 rounded-full hover:bg-purple-600 transition-colors font-medium text-sm btn-3d mt-4">
                            Book ₹6,300 Package
                        </button>
                    </div>

                    <!-- Reception Package ₹5,600 (30% OFF from ₹8,000) -->
                    <div class="package-card-3d gradient-border-3d bg-gradient-to-br from-blue-50 to-indigo-50 rounded-2xl p-6 shadow-luxury-3d relative">
                        <div class="discount-badge-3d">30% OFF</div>
                        <div class="text-center mb-4">
                            <div class="w-16 h-16 bg-gradient-to-br from-blue-500 to-indigo-600 rounded-full flex items-center justify-center mx-auto mb-3 icon-3d">
                                <span class="text-2xl">✨</span>
                            </div>
                            <h4 class="text-lg font-bold text-gray-800 mb-2">Premium Reception</h4>
                            <div class="flex items-center justify-center space-x-2 mb-2">
                                <span class="text-sm text-gray-400 line-through price-slash">₹8,000</span>
                                <span class="text-xl font-bold text-blue-600">₹5,600/-</span>
                            </div>
                            <p class="text-xs text-green-600 font-semibold">💰 Save ₹2,400!</p>
                        </div>
                        <ul class="space-y-2 text-sm text-gray-600">
                            <li class="flex items-center"><span class="text-blue-500 mr-2 text-lg">🎨</span> Air Brush Makeup</li>
                            <li class="flex items-center"><span class="text-blue-500 mr-2 text-lg">💇‍♀</span> Advance Hair Style (Hair Extension)</li>
                            <li class="flex items-center"><span class="text-blue-500 mr-2 text-lg">👗</span> Saree Draping</li>
                            <li class="flex items-center"><span class="text-blue-500 mr-2 text-lg">🎀</span> Broach</li>
                            <li class="flex items-center"><span class="text-blue-500 mr-2 text-lg">🌸</span> Real Flower</li>
                            <li class="flex items-center"><span class="text-blue-500 mr-2 text-lg">👁</span> Eyelashes & Lenses</li>
                            <li class="flex items-center"><span class="text-blue-500 mr-2 text-lg">💎</span> Jewelry</li>
                        </ul>
                        <button class="w-full bg-blue-500 text-white py-3 rounded-full hover:bg-blue-600 transition-colors font-medium text-sm btn-3d mt-4">
                            Book ₹5,600 Package
                        </button>
                    </div>

                    <!-- Side Packages -->
                    <div class="package-card-3d gradient-border-3d bg-gradient-to-br from-green-50 to-teal-50 rounded-2xl p-6 shadow-luxury-3d relative sparkle">
                        <div class="text-center mb-4">
                            <div class="w-16 h-16 bg-gradient-to-br from-green-500 to-teal-600 rounded-full flex items-center justify-center mx-auto mb-3 icon-3d">
                                <span class="text-2xl">💫</span>
                            </div>
                            <h4 class="text-lg font-bold text-gray-800 mb-4">Side Packages - 30% OFF!</h4>
                        </div>
                        
                        <div class="space-y-4">
                            <div class="bg-white rounded-xl p-4 border-2 border-green-200 shadow-lg">
                                <div class="flex items-center justify-between mb-2">
                                    <span class="text-sm text-gray-400 line-through">₹2,500</span>
                                    <span class="text-lg font-bold text-green-600">₹1,750/-</span>
                                </div>
                                <ul class="text-xs text-gray-600">
                                    <li class="flex items-center"><span class="text-green-500 mr-1">💄</span> HD Makeup</li>
                                    <li class="flex items-center"><span class="text-green-500 mr-1">💇‍♀</span> Basic Hair Style</li>
                                    <li class="flex items-center"><span class="text-green-500 mr-1">👗</span> Saree Draping</li>
                                    <li class="flex items-center"><span class="text-green-500 mr-1">🎀</span> Broach</li>
                                </ul>
                            </div>
                            
                            <div class="bg-white rounded-xl p-4 border-2 border-green-200 shadow-lg">
                                <div class="flex items-center justify-between mb-2">
                                    <span class="text-sm text-gray-400 line-through">₹3,000</span>
                                    <span class="text-lg font-bold text-green-600">₹2,100/-</span>
                                </div>
                                <ul class="text-xs text-gray-600">
                                    <li class="flex items-center"><span class="text-green-500 mr-1">💄</span> HD Makeup</li>
                                    <li class="flex items-center"><span class="text-green-500 mr-1">💇‍♀</span> Advance Hair Style</li>
                                    <li class="flex items-center"><span class="text-green-500 mr-1">👗</span> Saree Draping</li>
                                    <li class="flex items-center"><span class="text-green-500 mr-1">🎀</span> Broach</li>
                                </ul>
                            </div>
                            
                            <div class="bg-white rounded-xl p-4 border-2 border-green-200 shadow-lg">
                                <div class="flex items-center justify-between mb-2">
                                    <span class="text-sm text-gray-400 line-through">₹4,000</span>
                                    <span class="text-lg font-bold text-green-600">₹2,800/-</span>
                                </div>
                                <ul class="text-xs text-gray-600">
                                    <li class="flex items-center"><span class="text-green-500 mr-1">💫</span> Advance Makeup</li>
                                    <li class="flex items-center"><span class="text-green-500 mr-1">💇‍♀</span> Advance Hair (Extension)</li>
                                    <li class="flex items-center"><span class="text-green-500 mr-1">👗</span> Saree Draping</li>
                                    <li class="flex items-center"><span class="text-green-500 mr-1">🌸</span> Broach & Real Flower</li>
                                </ul>
                            </div>
                            
                            <div class="bg-white rounded-xl p-4 border-2 border-green-200 shadow-lg">
                                <div class="flex items-center justify-between mb-2">
                                    <span class="text-sm text-gray-400 line-through">₹5,000</span>
                                    <span class="text-lg font-bold text-green-600">₹3,500/-</span>
                                </div>
                                <ul class="text-xs text-gray-600">
                                    <li class="flex items-center"><span class="text-green-500 mr-1">🎨</span> Air Brush Makeup</li>
                                    <li class="flex items-center"><span class="text-green-500 mr-1">💇‍♀</span> Advance Hair (Extension)</li>
                                    <li class="flex items-center"><span class="text-green-500 mr-1">👗</span> Saree Draping</li>
                                    <li class="flex items-center"><span class="text-green-500 mr-1">🌸</span> Broach & Real Flower</li>
                                    <li class="flex items-center"><span class="text-green-500 mr-1">👁</span> Eyelashes & Lenses</li>
                                </ul>
                            </div>
                        </div>
                        <button class="w-full bg-green-500 text-white py-3 rounded-full hover:bg-green-600 transition-colors font-medium text-sm btn-3d mt-4">
                            Choose Side Package
                        </button>
                    </div>
                </div>
            </div>
            
            <div class="text-center">
                <p class="text-gray-600 mb-6">Need a custom package? We create personalized bridal experiences!</p>
                <button class="bg-gradient-to-r from-pink-500 to-purple-600 text-white px-8 py-4 rounded-full hover:from-pink-600 hover:to-purple-700 transition-all font-semibold shadow-lg">
                    Discuss Custom Package
                </button>
            </div>
        </div>
    </section>

    <!-- Gallery Section -->
    <section id="gallery" class="py-20 hero-gradient relative overflow-hidden">
        <div class="max-w-7xl mx-auto px-6 relative z-10">
            <div class="text-center mb-16">
                <h2 class="text-4xl md:text-5xl font-bold text-white mb-6 text-shadow-lg">Our Work Gallery</h2>
                <p class="text-xl text-gray-100">See the amazing transformations we create</p>
            </div>
            
            <div class="grid md:grid-cols-4 gap-6">
                <div class="card-3d gradient-border-3d bg-gradient-to-br from-pink-200 to-purple-200 rounded-3xl h-64 flex items-center justify-center shadow-luxury-3d relative overflow-hidden sparkle">
                    <div class="absolute inset-0 sparkle-bg opacity-30"></div>
                    <div class="text-center relative z-10">
                        <span class="text-5xl mb-4 block icon-3d float-3d">💇‍♀</span>
                        <p class="text-gray-800 font-bold text-lg">Hair Styling</p>
                        <p class="text-gray-600 text-sm mt-1">Professional cuts & styles</p>
                    </div>
                </div>
                <div class="card-3d gradient-border-3d bg-gradient-to-br from-blue-200 to-indigo-200 rounded-3xl h-64 flex items-center justify-center shadow-luxury-3d relative overflow-hidden sparkle">
                    <div class="absolute inset-0 sparkle-bg opacity-30"></div>
                    <div class="text-center relative z-10">
                        <span class="text-5xl mb-4 block icon-3d float-3d">✨</span>
                        <p class="text-gray-800 font-bold text-lg">Facial Treatment</p>
                        <p class="text-gray-600 text-sm mt-1">Glowing skin solutions</p>
                    </div>
                </div>
                <div class="card-3d gradient-border-3d bg-gradient-to-br from-yellow-200 to-orange-200 rounded-3xl h-64 flex items-center justify-center shadow-luxury-3d relative overflow-hidden sparkle">
                    <div class="absolute inset-0 sparkle-bg opacity-30"></div>
                    <div class="text-center relative z-10">
                        <span class="text-5xl mb-4 block icon-3d float-3d">💄</span>
                        <p class="text-gray-800 font-bold text-lg">Makeup</p>
                        <p class="text-gray-600 text-sm mt-1">HD & Airbrush artistry</p>
                    </div>
                </div>
                <div class="card-3d gradient-border-3d bg-gradient-to-br from-green-200 to-teal-200 rounded-3xl h-64 flex items-center justify-center shadow-luxury-3d relative overflow-hidden sparkle">
                    <div class="absolute inset-0 sparkle-bg opacity-30"></div>
                    <div class="text-center relative z-10">
                        <span class="text-5xl mb-4 block icon-3d float-3d">💅</span>
                        <p class="text-gray-800 font-bold text-lg">Nail Art</p>
                        <p class="text-gray-600 text-sm mt-1">Creative nail designs</p>
                    </div>
                </div>
            </div>
            
            <!-- Additional Gallery Items -->
            <div class="grid md:grid-cols-3 gap-8 mt-12">
                <div class="card-3d gradient-border-3d bg-gradient-to-br from-rose-200 to-pink-300 rounded-3xl h-80 flex items-center justify-center shadow-luxury-3d relative overflow-hidden sparkle">
                    <div class="absolute inset-0 sparkle-bg opacity-30"></div>
                    <div class="text-center relative z-10">
                        <span class="text-6xl mb-4 block icon-3d float-3d">👰</span>
                        <p class="text-gray-800 font-bold text-xl">Bridal Makeovers</p>
                        <p class="text-gray-600 text-sm mt-2">Complete bridal transformation</p>
                        <div class="mt-4 flex justify-center space-x-2">
                            <span class="w-2 h-2 bg-pink-500 rounded-full pulse-glow"></span>
                            <span class="w-2 h-2 bg-purple-500 rounded-full pulse-glow"></span>
                            <span class="w-2 h-2 bg-orange-500 rounded-full pulse-glow"></span>
                        </div>
                    </div>
                </div>
                
                <div class="card-3d gradient-border-3d bg-gradient-to-br from-purple-200 to-indigo-300 rounded-3xl h-80 flex items-center justify-center shadow-luxury-3d relative overflow-hidden sparkle">
                    <div class="absolute inset-0 sparkle-bg opacity-30"></div>
                    <div class="text-center relative z-10">
                        <span class="text-6xl mb-4 block icon-3d float-3d">🌟</span>
                        <p class="text-gray-800 font-bold text-xl">Premium Treatments</p>
                        <p class="text-gray-600 text-sm mt-2">Luxury spa experiences</p>
                        <div class="mt-4 flex justify-center space-x-2">
                            <span class="w-2 h-2 bg-blue-500 rounded-full pulse-glow"></span>
                            <span class="w-2 h-2 bg-indigo-500 rounded-full pulse-glow"></span>
                            <span class="w-2 h-2 bg-purple-500 rounded-full pulse-glow"></span>
                        </div>
                    </div>
                </div>
                
                <div class="card-3d gradient-border-3d bg-gradient-to-br from-orange-200 to-red-300 rounded-3xl h-80 flex items-center justify-center shadow-luxury-3d relative overflow-hidden sparkle">
                    <div class="absolute inset-0 sparkle-bg opacity-30"></div>
                    <div class="text-center relative z-10">
                        <span class="text-6xl mb-4 block icon-3d float-3d">💎</span>
                        <p class="text-gray-800 font-bold text-xl">Diamond Packages</p>
                        <p class="text-gray-600 text-sm mt-2">Ultimate beauty experiences</p>
                        <div class="mt-4 flex justify-center space-x-2">
                            <span class="w-2 h-2 bg-orange-500 rounded-full pulse-glow"></span>
                            <span class="w-2 h-2 bg-red-500 rounded-full pulse-glow"></span>
                            <span class="w-2 h-2 bg-yellow-500 rounded-full pulse-glow"></span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="py-20 bg-white">
        <div class="max-w-7xl mx-auto px-6">
            <div class="grid md:grid-cols-2 gap-12 items-center">
                <div>
                    <h2 class="text-4xl md:text-5xl font-bold text-gray-800 mb-6">Why Choose Keshar Beauty Kadi?</h2>
                    <p class="text-xl text-gray-600 mb-8">
                        With over 10 years of experience, we're committed to bringing out your natural beauty with premium services and expert care.
                    </p>
                    
                    <div class="space-y-6">
                        <div class="flex items-start space-x-4">
                            <div class="w-12 h-12 bg-pink-100 rounded-full flex items-center justify-center flex-shrink-0">
                                <span class="text-pink-500 text-xl">👩‍🎨</span>
                            </div>
                            <div>
                                <h3 class="text-xl font-semibold text-gray-800 mb-2">Expert Stylists</h3>
                                <p class="text-gray-600">Certified professionals with years of experience</p>
                            </div>
                        </div>
                        
                        <div class="flex items-start space-x-4">
                            <div class="w-12 h-12 bg-blue-100 rounded-full flex items-center justify-center flex-shrink-0">
                                <span class="text-blue-500 text-xl">🏆</span>
                            </div>
                            <div>
