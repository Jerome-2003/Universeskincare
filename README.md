Only admin see
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>UNIVERSE Skincare - Mobile Web</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap" rel="stylesheet">
    
    <script type="module" src="https://unpkg.com/lucide@latest"></script>
    <style>
        /* * RESPONSIVE MOBILE WEBSITE STRUCTURE CHANGES 
         * 1. The body now takes the full viewport (no fixed app container frame).
         * 2. The main body background is now the deep color.
         */
        body {
            font-family: 'Inter', sans-serif;
            background-color: #0d0c1d; /* The very dark background from the old .app-container */
            color: white; /* Ensure base text color is visible */
            min-height: 100vh;
            margin: 0;
            padding-bottom: 4rem; /* Add space for the fixed footer */
            /* Remove: display: flex; justify-content: center; align-items: center; min-height: 100vh; */
        }

        /* * OLD .app-container STYLES REMOVED/MODIFIED 
         * The fixed sizing and device simulation are gone.
         * The #app container now simply wraps the main content and handles max-width for larger screens.
         */
        #app {
            width: 100%;
            max-width: 600px; /* Set a max width for large screens for better readability */
            margin: 0 auto; /* Center the content on larger screens */
            display: flex;
            flex-direction: column;
            min-height: 100vh; /* Ensure it takes full height to push footer down if not fixed */
            background: transparent; /* No inner background */
            /* Remove: height: 800px; box-shadow; border-radius; */
        }

        /* Header gradient to match the template */
        .app-header {
            background: linear-gradient(135deg, #1c193f, #312e81, #4f46e5);
            /* Make the header sticky at the top */
            position: sticky; 
            top: 0;
            z-index: 30; /* Ensure it's above content */
        }

        /* Content area that scrolls - now occupies the space below the header */
        .app-content {
            flex-grow: 1;
            overflow-y: auto;
            padding: 1rem;
            /* Remove app scrollbar hacks */
            -ms-overflow-style: auto; 
            scrollbar-width: auto; 
        }
        .app-content::-webkit-scrollbar {
            display: block; 
            width: 8px;
            background-color: #0d0c1d;
        }
        .app-content::-webkit-scrollbar-thumb {
            background-color: #312e81;
            border-radius: 4px;
        }

        /* Footer is fixed at the bottom of the viewport for a mobile web feel */
        #mobile-nav-footer {
            position: fixed;
            bottom: 0;
            left: 0;
            right: 0;
            width: 100%;
            height: 4rem; /* Adjusted from 16 to a fixed height for consistency */
            background-color: #1c193f; 
            border-top: 1px solid #4f46e550;
            z-index: 50; 
            box-shadow: 0 -5px 20px rgba(0,0,0,0.3);
        }

        /* All other custom styles remain the same for component consistency */
        .product-card {
            border: 2px solid transparent;
            border-radius: 12px;
            background-clip: padding-box, border-box;
            background-origin: padding-box, border-box;
            background-image: linear-gradient(#0d0c1d, #0d0c1d), linear-gradient(to right, #4f46e5, #312e81);
            transition: transform 0.2s, box-shadow 0.2s;
        }
        .product-card:hover {
             transform: translateY(-2px);
             box-shadow: 0 10px 15px -3px rgba(79, 70, 229, 0.2), 0 4px 6px -2px rgba(79, 70, 229, 0.05);
        }
        .active-nav {
            transform: scale(1.1);
            color: #818cf8;
        }
        .social-icon {
            transition: all 0.2s;
            cursor: pointer;
        }
        .social-icon:hover {
            color: #a78bfa;
            transform: translateY(-2px);
        }
        .mobile-shop-nav {
            background: #1c193f;
            box-shadow: 0 -5px 20px rgba(0, 0, 0, 0.5);
            border-top: 1px solid #4f46e550;
        }
        .product-badge {
            @apply absolute top-0 left-0 text-xs font-semibold px-2 py-0.5 rounded-br-lg;
        }
        .official-store-badge {
            @apply bg-indigo-600 text-white;
        }
        .pay-on-delivery-badge {
            @apply bg-green-500 text-white;
        }
        .discount-badge {
            @apply bg-pink-500 text-white;
        }
        .qty-btn {
            @apply bg-indigo-700 text-white w-6 h-6 rounded-full text-lg leading-none flex items-center justify-center transition hover:bg-indigo-600 active:scale-95;
        }
        /* REMOVED: #reader video CSS */
        .admin-input {
            @apply w-full p-3 bg-gray-700/50 text-white rounded-lg border border-indigo-500/50 focus:ring-2 focus:ring-indigo-400 focus:outline-none transition;
        }

        /* * RESPONSIVE DESIGN ENHANCEMENT: 
         * Hide the fixed shop nav on screens wider than a mobile device for better UX. 
         */
        @media (min-width: 601px) {
            #mobile-shop-nav {
                display: none !important;
            }
        }
        
        /* NEW: Rule to hide admin button by default for non-admin users */
        .admin-button {
            display: none !important;
        }
        
    </style>
</head>
<body class="selection:bg-indigo-300 selection:text-indigo-900">

<div id="app" class="relative"> 

    
<header id="app-header" class="app-header p-4 text-white shadow-lg h-36 flex flex-col justify-between">
        <div class="flex justify-between items-center text-xs font-semibold">
            <span class="text-gray-400">UNIVERSE Skincare</span> <span class="text-gray-400">9:41 AM</span>
        </div>
        <div class="flex items-center mt-2 flex-grow">
            
<div class="w-20 h-20 flex-shrink-0">
                <a href="https://ibb.co/Z6djmTW9" class="block w-full h-full"><img src="https://i.ibb.co/zhsMJfGd/IMG-0365.jpg" alt="UNIVERSE Logo" class="w-full h-full object-contain border-0"></a>
            </div>
            <div class="ml-4 flex-grow">
                <h1 class="text-lg font-bold">UNIVERSE</h1>
                <p class="text-sm text-gray-300">cosmetics and beauty skincare</p>
            </div>
        </div>
    </header>

    
<main id="main-content" class="app-content mb-16">

        
<div id="home-view" class="page-view" data-page="home">
    <div class="w-full h-8 bg-indigo-600 rounded-lg flex items-center justify-center mb-6">
        <h2 class="text-white text-base font-semibold tracking-wider">HOME</h2>
    </div>
    
    <section class="mb-8 rounded-xl overflow-hidden shadow-2xl product-card border-none p-0">
        <div class="relative w-full h-[300px] overflow-hidden">
            <img src="https://i.ibb.co/nMNNJ4TH/IMG-0481.jpg"
                 alt="UNIVERSE Radiance Skincare Banner" 
                 class="w-full h-full object-cover brightness-75"
                 onerror="this.onerror=null;this.src='https://placehold.co/400x600/1c193f/d1d5db?text=Image+Load+Error';"
            >
            
            <div class="absolute inset-0 flex items-center justify-center p-4">
                <h3 class="text-3xl font-extrabold text-white text-center tracking-wider leading-snug drop-shadow-lg">
                    Unveiling your radiance
                </h3>
            </div>
        </div>
    </section>
    <section class="mb-8">
        <h3 class="text-xl font-extrabold text-white mb-4 border-b border-indigo-400/50 pb-2">ABOUT</h3>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-4 items-center">
            <p class="text-gray-300 leading-relaxed text-sm">
                This company strives in providing you products that helps unveil your radiance, shine with us today. We believe true beauty starts with healthy, nourished skin, and we're committed to sourcing only the best ingredients.
            </p>
            <div class="rounded-xl overflow-hidden shadow-2xl product-card">
                <a href="https://ibb.co/KjsVX3VM" class="block w-full h-auto">
                    <img src="https://i.ibb.co/fYNr2Prh/IMG-0390.jpg" alt="Skincare products" class="w-full h-auto object-cover transition-transform duration-300 hover:scale-[1.03] border-0">
                </a>
            </div>
        </div>
    </section>

    <section class="mt-8 mb-8 pt-4 border-t border-indigo-400/50">
        <h3 class="text-xl font-extrabold text-white mb-4">NEW ARRIVALS</h3>
        <div class="grid grid-cols-2 gap-4 mb-6">
            <div class="rounded-lg overflow-hidden shadow-xl product-card p-1">
                <a href="https://ibb.co/HTN8Tq2C" class="block">
                    <img src="https://i.ibb.co/N21B2K3r/IMG-0391.jpg" alt="New Product 1" class="w-full h-auto object-cover rounded-lg">
                </a>
            </div>
            <div class="rounded-lg overflow-hidden shadow-xl product-card p-1">
                <a href="https://ibb.co/fGkV77Ph/IMG-0389.jpg" class="block">
                    <img src="https://i.ibb.co/fGkV77Ph/IMG-0389.jpg" alt="New Product 2" class="w-full h-auto object-cover rounded-lg">
                </a>
            </div>
        </div>

        <button onclick="navigateTo('shop')" class="w-full py-3 bg-indigo-600 text-white font-bold text-lg rounded-xl shadow-lg hover:bg-indigo-700 transition duration-200 transform hover:scale-[1.01] flex items-center justify-center">
            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-shopping-bag mr-3"><path d="M6 2L3 7v14a2 2 0 0 0 2 2h14a2 2 0 0 0 2-2V7l-3-5Z"/><path d="M3 7h18"/><path d="M16 10a4 4 0 0 1-8 0"/></svg>
            SHOP NEW ARRIVALS
        </button>
    </section>
    <section class="mt-8 pt-4 border-t border-indigo-400/50">
        <h3 class="text-xl font-extrabold text-white mb-4">TESTIMONIALS</h3>
        <div class="space-y-4">
            <div class="p-4 rounded-xl bg-indigo-900/40 text-sm">
                <p class="text-gray-200 italic">"My skin has never felt better. The products are truly transformative!"</p>
                <p class="text-right text-indigo-400 mt-2">— Sarah L.</p>
            </div>
            <div class="p-4 rounded-xl bg-indigo-900/40 text-sm">
                <p class="text-gray-200 italic">"Fast shipping and amazing customer support. Highly recommend UNIVERSE!"</p>
                <p class="text-right text-indigo-400 mt-2">— David B.</p>
            </div>
        </div>
    </section>
</div>

        
<div id="shop-view" class="page-view hidden" data-page="shop">
    <div class="w-full h-8 bg-indigo-600 rounded-lg flex items-center justify-center mb-6">
        <h2 class="text-white text-base font-semibold tracking-wider">SHOP NOW</h2>
    </div>
    
    <section class="pb-16">
        <div id="product-grid" class="grid grid-cols-2 gap-4">
            <p id="shop-loading-message" class="col-span-2 text-center text-gray-400 py-12">Loading products...</p>
        </div>
    </section>
    <section class="mt-8 pt-4 border-t border-indigo-400/50">
        <h3 class="text-xl font-extrabold text-white mb-4">CUSTOMER REVIEWS</h3>
        <div class="space-y-4">
            <div class="flex items-start p-4 rounded-xl bg-indigo-900/40 border border-indigo-700/50">
                <img src="https://placehold.co/64x64/4c051e/ffffff?text=User" onerror="this.onerror=null;this.src='https://placehold.co/64x64/4c051e/ffffff?text=User';" alt="Portrait of a happy Black woman using UNIVERSE products" class="w-12 h-12 rounded-full object-cover mr-4 flex-shrink-0">
                <div class="flex-grow">
                    <p class="text-gray-200 italic text-sm">"The Radiant Glow Serum is a game-changer! It's lightweight and gives my skin a flawless, non-oily finish. Absolutely essential for my routine."</p>
                    <p class="text-right text-indigo-400 font-semibold mt-2">— Jessica A.</p>
                </div>
            </div>
            <div class="flex items-start p-4 rounded-xl bg-indigo-900/40 border border-indigo-700/50">
                <img src="https://placehold.co/64x64/2d1740/ffffff?text=User" onerror="this.onerror=null;this.src='https://placehold.co/64x64/2d1740/ffffff?text=User';" alt="Portrait of a satisfied Black woman customer" class="w-12 h-12 rounded-full object-cover mr-4 flex-shrink-0">
                <div class="flex-grow">
                    <p class="text-gray-200 italic text-sm">"I was skeptical, but the Moisturizing Cream completely cleared up my dry patches. It feels rich without being heavy—perfection!"</p>
                    <p class="text-right text-indigo-400 font-semibold mt-2">— Nala O.</p>
                </div>
            </div>
        </div>
    </section>
    </div>

        
<div id="cart-view" class="page-view hidden" data-page="cart">
    <div class="w-full h-8 bg-indigo-600 rounded-lg flex items-center justify-center mb-6">
        <h2 class="text-white text-base font-semibold tracking-wider">SHOPPING CART</h2>
    </div>

    <div id="cart-items-container" class="space-y-4 mb-8">
        <p class="text-gray-400 text-center py-12" id="cart-empty-message">
            Your cart is empty. Time to find your radiance!
        </p>
    </div>
    
    <form id="checkout-form" onsubmit="handleCheckout(event)" class="space-y-4 p-4 mb-8 bg-indigo-900/40 rounded-xl border border-indigo-700/50">
        <h3 class="text-lg font-bold text-white border-b border-indigo-500/50 pb-2">Delivery Information</h3>
        
        <input type="text" id="customer-name" class="admin-input" placeholder="Full Name" required>
        <input type="tel" id="customer-phone" class="admin-input" placeholder="Phone Number (e.g., 070...)" required>
        <textarea id="customer-address" class="admin-input h-20 resize-none" placeholder="Shipping Address" required></textarea>

        <button type="submit" id="checkout-button" class="w-full py-3 bg-pink-600 text-white font-bold text-lg rounded-xl shadow-lg hover:bg-pink-700 transition duration-200 transform hover:scale-[1.01] flex items-center justify-center">
            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-credit-card mr-3"><rect width="20" height="14" x="2" y="5" rx="2"/><line x1="2" x2="22" y1="10" y2="10"/></svg>
            PROCEED TO CHECKOUT
        </button>
        <p class="text-xs text-center text-gray-500 mt-2">
            Payment will be confirmed after order submission.
        </p>
    </form>
    <div id="cart-summary" class="sticky bottom-0 bg-gray-900/50 p-4 rounded-xl border border-indigo-700/50">
        <div class="flex justify-between items-center text-lg mb-3">
            <span class="text-gray-300 font-semibold">Subtotal:</span>
            <span id="cart-subtotal" class="text-white font-bold">$0.00</span>
        </div>
        <div class="flex justify-between items-center text-lg mb-4 border-b border-indigo-700/50 pb-3">
            <span class="text-gray-300 font-semibold">Shipping:</span>
            <span class="text-white font-bold">FREE</span>
        </div>
        <div class="flex justify-between items-center text-xl">
            <span class="text-indigo-400 font-extrabold">Total:</span>
            <span id="cart-total" class="text-pink-400 font-extrabold">$0.00</span>
        </div>
        
        <p id="auth-status-display" class="text-xs text-center text-gray-500 mt-2">
            Loading user status...
        </p>
    </div>
</div>

        
<div id="auth-view" class="page-view hidden" data-page="auth">
    <div class="w-full h-8 bg-pink-600 rounded-lg flex items-center justify-center mb-6">
        <h2 class="text-white text-base font-semibold tracking-wider" id="auth-header-title">ADMIN PANEL</h2>
    </div>

    <div id="admin-panel">
        <h3 class="text-2xl font-bold text-white mb-4 text-center">Product Management</h3>
        <p class="text-xs text-gray-400 text-center mb-4">You are currently signed in as the Administrator.</p>
        
        <div class="p-4 bg-indigo-900/40 rounded-xl mb-6 border border-indigo-700/50">
            <h4 class="text-lg font-semibold text-indigo-300 mb-4" id="form-title">Add New Product</h4>
            <form id="product-form" onsubmit="handleProductFormSubmit(event)">
                <input type="hidden" id="product-doc-id" value="">
                <div class="space-y-3">
                    <input type="text" id="product-name" class="admin-input" placeholder="Product Name" required>
                    <input type="number" id="product-price" class="admin-input" placeholder="Price (e.g., 45.00)" step="0.01" required>
                    <input type="number" id="product-line-through-price" class="admin-input" placeholder="Old Price (Optional, e.g., 55.00)" step="0.01">
                    <input type="text" id="product-img" class="admin-input" placeholder="Image URL (e.g., https://i.ibb.co/...)" required>
                    <input type="text" id="product-badge" class="admin-input" placeholder="Badge Text (e.g., Best Seller)">
                    <button type="submit" id="product-form-button" class="w-full py-3 bg-indigo-600 text-white font-bold rounded-lg hover:bg-indigo-700 transition">Add Product</button>
                    <button type="button" onclick="resetForm()" class="w-full py-3 bg-gray-600 text-white font-bold rounded-lg hover:bg-gray-700 transition">Cancel / New</button>
                </div>
            </form>
        </div>

        <div class="p-4 bg-gray-900/50 rounded-xl border border-gray-700/50 mb-8">
            <h4 class="text-lg font-semibold text-indigo-300 mb-4">Existing Products</h4>
            <ul id="admin-product-list" class="space-y-3">
                <li class="text-gray-400">Loading products...</li>
            </ul>
        </div>
        
        <div id="orders-panel" class="p-4 bg-red-900/40 rounded-xl border border-red-700/50">
            <h4 class="text-xl font-extrabold text-red-300 mb-4 flex items-center">
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-box-select mr-2"><path d="M21.5 5.5a2.5 2.5 0 0 0-2.5-2.5H6l2 4 4-4 4 4 2-4h2a2.5 2.5 0 0 1 2.5 2.5v2L19 12l2 4v2.5a2.5 2.5 0 0 1-2.5 2.5H6l-2-4-2-4v-2L5 9l-2-4v-2.5a2.5 2.5 0 0 1 2.5-2.5H18l-4 4-4-4-4 4-2-4H5a2.5 2.5 0 0 0-2.5 2.5v2.5L5 9l2 4v2.5a2.5 2.5 0 0 0 2.5 2.5h10.5a2.5 2.5 0 0 0 2.5-2.5v-2L19 12l-2-4v-2.5a2.5 2.5 0 0 1 2.5-2.5z"/></svg>
                PENDING ORDERS
            </h4>
            <ul id="admin-orders-list" class="space-y-4">
                <li class="text-gray-400">Loading orders...</li>
            </ul>
        </div>
        </div>

    </div>
</main>

    <div id="mobile-shop-nav" class="fixed bottom-[4rem] left-0 right-0 h-14 mobile-shop-nav flex justify-around items-center z-40 hidden">
        <button onclick="alertMessage('Sort Feature')" class="flex items-center text-white/90 hover:text-indigo-400 transition-colors duration-200">
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-arrow-down-up mr-2"><path d="m3 16 4 4 4-4"/><path d="M7 20V4"/><path d="m21 8-4-4-4 4"/><path d="M17 4v16"/></svg>
            <span class="font-bold text-sm">Sort by</span>
        </button>
        <div class="w-px h-8 bg-indigo-700"></div>
        <button onclick="alertMessage('Filter Feature')" class="flex items-center text-white/90 hover:text-indigo-400 transition-colors duration-200">
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-sliders-horizontal mr-2"><path d="M21 17H3"/><path d="M21 12H3"/><path d="M21 7H3"/><path d="M18 10v4"/><path d="M6 5v4"/><path d="M14 15v4"/></svg>
            <span class="font-bold text-sm">Filter</span>
        </button>
    </div>


    
<footer id="mobile-nav-footer" class="flex justify-around items-center text-gray-400">
        <button onclick="navigateTo('home')" id="nav-home" class="nav-button flex flex-col items-center p-2 rounded-lg transition-all duration-300 active-nav">
            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-home"><path d="m3 9 9-7 9 7v11a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2z"/><polyline points="9 22 9 12 15 12 15 22"/></svg>
            <span class="text-xs mt-1">Home</span>
        </button>
        <button onclick="navigateTo('shop')" id="nav-shop" class="nav-button flex flex-col items-center p-2 rounded-lg transition-all duration-300">
            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-shopping-bag"><path d="M6 2L3 7v14a2 2 0 0 0 2 2h14a2 2 0 0 0 2-2V7l-3-5Z"/><path d="M3 7h18"/><path d="M16 10a4 4 0 0 1-8 0"/></svg>
            <span class="text-xs mt-1">Shop</span>
        </button>
        <button onclick="navigateTo('cart')" id="nav-cart" class="nav-button flex flex-col items-center p-2 rounded-lg transition-all duration-300">
            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-shopping-cart"><circle cx="8" cy="20" r="1"/><circle cx="19" cy="20" r="1"/><path d="M2.5 2.5h2l2.64 10.37a2 2 0 0 0 1.95 1.63h8.84a2 2 0 0 0 1.95-1.63L21.5 7.5h-13"/></svg>
            <span class="text-xs mt-1">Cart</span>
        </button>
        <button onclick="navigateTo('auth')" id="nav-auth" class="nav-button flex flex-col items-center p-2 rounded-lg transition-all duration-300 admin-button">
            <svg xmlns="http://www.w3.org/2300/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-scan"><path d="M3 7V5a2 2 0 0 1 2-2h2"/><path d="M17 3h2a2 2 0 0 1 2 2v2"/><path d="M21 17v2a2 2 0 0 1-2 2h-2"/><path d="M7 21H5a2 2 0 0 1-2-2v-2"/></svg>
            <span class="text-xs mt-1">Admin</span> </button>
    </footer>

    <div id="message-box" class="fixed inset-0 bg-black/60 z-50 hidden items-center justify-center">
        <div class="bg-gray-800 p-6 rounded-xl shadow-2xl max-w-xs w-full text-center border-t-4 border-indigo-500">
            <p id="message-text" class="text-white text-lg mb-4"></p>
            <button onclick="hideMessage()" class="w-full bg-indigo-600 text-white py-2 rounded-lg font-semibold hover:bg-indigo-700 transition">OK</button>
        </div>
    </div>
<div id="confirmation-box" class="fixed inset-0 bg-black/60 z-50 hidden items-center justify-center">
        <div class="bg-gray-800 p-6 rounded-xl shadow-2xl max-w-xs w-full text-center border-t-4 border-red-500">
            <p id="confirmation-text" class="text-white text-lg mb-4"></p>
            <div class="flex justify-between space-x-4">
                <button id="confirm-yes-btn" class="flex-1 bg-red-600 text-white py-2 rounded-lg font-semibold hover:bg-red-700 transition">Delete</button>
                <button id="confirm-no-btn" class="flex-1 bg-gray-600 text-white py-2 rounded-lg font-semibold hover:bg-gray-700 transition">Cancel</button>
            </div>
        </div>
    </div>
    </div>

<script type="module">
    // --- Firebase Imports ---
    import { initializeApp } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-app.js";
    import { getAnalytics } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-analytics.js"; 
    import { getAuth, signInAnonymously, signInWithCustomToken, onAuthStateChanged } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-auth.js";
    import { getFirestore, doc, collection, query, addDoc, updateDoc, deleteDoc, onSnapshot } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-firestore.js";
    import { setLogLevel } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-firestore.js";
    // setLogLevel('debug'); // Optional: Uncomment to see detailed Firestore logs

    // **********************************************
    // * YOUR FIREBASE CONFIGURATION AND INITIALIZATION
    // **********************************************
    // Your web app's Firebase configuration
    // For Firebase JS SDK v7.20.0 and later, measurementId is optional
    const firebaseConfig = {
      apiKey: "AIzaSyBi4U4tt1fh-jCiufDnyO3wqqVhcZgWL1s",
      authDomain: "universe2004-6e50e.firebaseapp.com",
      projectId: "universe2004-6e50e",
      storageBucket: "universe2004-6e50e.firebasestorage.app",
      messagingSenderId: "233249859383",
      appId: "1:233249859383:web:7dd0ef5700af1188291cb2",
      measurementId: "G-78HDJQE55J"
    };

    // Initialize Firebase outside of the function, and initialize analytics
    const firebaseApp = initializeApp(firebaseConfig);
    const analytics = getAnalytics(firebaseApp); 
    // **********************************************
    // * END FIREBASE CONFIGURATION
    // **********************************************


    // --- App Configuration and Globals ---
    const appId = firebaseConfig.projectId; 
    const initialAuthToken = typeof __initial_auth_token !== 'undefined' ? __initial_auth_token : null;

    let db;
    let auth;
    let userId = null;
    let isCurrentUserAdmin = false;
    let productsLoaded = false;
    let cartListenerUnsubscribe = null;
    let productsListenerUnsubscribe = null;
    let ordersListenerUnsubscribe = null; 

    // Stores products as an object for quick lookup: { docId: { docId, name, price, ... } }
    let currentProductsMap = {};
    // Stores cart items: { docId: { cartDocId, quantity: N, data: ProductData } }
    let currentCartItems = {}; 
    // NEW: Stores pending orders
    let currentOrders = {}; 

    // --- DOM Elements (Alert/Confirmation) ---
    const messageBox = document.getElementById('message-box');
    const messageText = document.getElementById('message-text');

    const confirmationBox = document.getElementById('confirmation-box');
    const confirmationText = document.getElementById('confirmation-text');
    const confirmYesBtn = document.getElementById('confirm-yes-btn');
    const confirmNoBtn = document.getElementById('confirm-no-btn');
    let resolveConfirmation = null;

    // --- DOM Elements (Main App) ---
    const navButtons = document.querySelectorAll('.nav-button');
    const mobileShopNav = document.getElementById('mobile-shop-nav');
    const mainContent = document.getElementById('main-content');
    const cartItemsContainer = document.getElementById('cart-items-container');
    const cartEmptyMessage = document.getElementById('cart-empty-message');
    const cartSubtotal = document.getElementById('cart-subtotal');
    const cartTotal = document.getElementById('cart-total');
    const authStatusDisplay = document.getElementById('auth-status-display');
    const authHeaderTitle = document.getElementById('auth-header-title');
    
    // NEW: Admin Button Element (For hiding/showing)
    const adminButton = document.getElementById('nav-auth');
    
    // NEW: Checkout Form Elements
    const checkoutForm = document.getElementById('checkout-form');
    const customerNameInput = document.getElementById('customer-name');
    const customerPhoneInput = document.getElementById('customer-phone');
    const customerAddressInput = document.getElementById('customer-address');

    // Admin/Auth View Elements
    const adminPanel = document.getElementById('admin-panel');
    const adminProductList = document.getElementById('admin-product-list');
    const productForm = document.getElementById('product-form');
    const productDocIdInput = document.getElementById('product-doc-id');
    const productNameInput = document.getElementById('product-name');
    const productPriceInput = document.getElementById('product-price');
    const productLineThroughPriceInput = document.getElementById('product-line-through-price');
    const productImgInput = document.getElementById('product-img');
    const productBadgeInput = document.getElementById('product-badge');
    const formTitle = document.getElementById('form-title');
    const formButton = document.getElementById('product-form-button');
    const productGrid = document.getElementById('product-grid');
    const shopLoadingMessage = document.getElementById('shop-loading-message');
    
    // NEW: Orders List Element
    const adminOrdersList = document.getElementById('admin-orders-list');


    let currentPage = 'home';

    // --- Firebase Collection/Document References ---

    /** Gets the Firestore collection reference for all public products. */
    function getProductsCollectionRef() {
        if (!db) return null;
        return collection(db, `artifacts/${appId}/public/data/products`);
    }

    /** Gets the Firestore document reference for the admin configuration. */
    function getAdminConfigDocRef() {
        if (!db) return null;
        return doc(db, `artifacts/${appId}/public/data/settings/adminConfig`);
    }

    /** Gets the Firestore collection reference for the user's private cart. */
    function getCartCollectionRef() {
        if (!db || !userId) return null;
        return collection(db, `artifacts/${appId}/users/${userId}/cart`);
    }
    
    /** NEW: Gets the Firestore collection reference for all customer orders. */
    function getOrdersCollectionRef() {
        if (!db) return null;
        // Public data: /artifacts/{appId}/public/data/orders
        return collection(db, `artifacts/${appId}/public/data/orders`);
    }


    // --- Firebase Initialization and Auth ---

    /** Initializes Firebase and sets up the authentication listener. */
    async function initializeFirebase() {
        db = getFirestore(firebaseApp);
        auth = getAuth(firebaseApp);

        try {
            if (initialAuthToken) {
                await signInWithCustomToken(auth, initialAuthToken);
            } else {
                await signInAnonymously(auth);
            }
        } catch (error) {
            console.error("Firebase authentication failed:", error);
            authStatusDisplay.textContent = `Auth failed: ${error.code}`;
            return;
        }

        onAuthStateChanged(auth, (user) => {
            if (user) {
                userId = user.uid;
                authStatusDisplay.textContent = `User ID: ${userId.substring(0, 8)}...`;
                console.log("User signed in with ID:", userId);
                loadProductsListener(); 
                loadAdminStatusListener(); 
                startCartListener(); 
            } else {
                userId = null;
                authStatusDisplay.textContent = "Signed out.";
                console.log("User signed out.");
                if (cartListenerUnsubscribe) cartListenerUnsubscribe();
                if (productsListenerUnsubscribe) productsListenerUnsubscribe();
                if (ordersListenerUnsubscribe) ordersListenerUnsubscribe(); // NEW: Clean up
                currentProductsMap = {};
                currentOrders = {}; // NEW: Clear orders
                renderShop();
                adminButton.classList.add('admin-button'); // Ensure button is hidden on sign out
            }
        });
    }

    // --- Admin Status and Conditional Rendering ---

    /** Sets up a listener for the Admin configuration document. */
    function loadAdminStatusListener() {
        const adminDocRef = getAdminConfigDocRef();
        if (!adminDocRef || !userId) return;

        onSnapshot(adminDocRef, async (docSnapshot) => {
            if (!docSnapshot.exists()) {
                try {
                    await setDoc(adminDocRef, { adminUserId: userId });
                    isCurrentUserAdmin = true;
                    console.log("Admin config initialized. Current user is Admin.");
                } catch (e) {
                    console.error("Failed to initialize admin config:", e);
                }
            } else {
                const adminData = docSnapshot.data();
                isCurrentUserAdmin = (adminData && adminData.adminUserId === userId);
                console.log("Admin status check:", isCurrentUserAdmin ? "Admin" : "Standard User");
            }
            
            updateAdminAuthView();
            
            // START MODIFICATION: Show/Hide Admin Button
            if (isCurrentUserAdmin) {
                adminButton.classList.remove('admin-button'); // Remove the CSS hiding class
            } else {
                adminButton.classList.add('admin-button'); // Ensure the CSS hiding class is present
            }
            // END MODIFICATION
            
            if(isCurrentUserAdmin) {
                loadOrdersListener(); // NEW: Start listening to orders only for Admin
            } else {
                if (ordersListenerUnsubscribe) ordersListenerUnsubscribe(); // NEW: Stop if no longer admin
            }
        }, (error) => {
            console.error("Error listening to admin status:", error);
        });
    }

    /** Toggles the visibility of the Admin Panel vs. Access Denied message. */
    function updateAdminAuthView() {
        if (currentPage !== 'auth') return;

        if (isCurrentUserAdmin) {
            adminPanel.classList.remove('hidden');
            adminPanel.innerHTML = `
                <h3 class="text-2xl font-bold text-white mb-4 text-center">Product Management</h3>
                <p class="text-xs text-gray-400 text-center mb-4">You are currently signed in as the Administrator.</p>
                
                <div class="p-4 bg-indigo-900/40 rounded-xl mb-6 border border-indigo-700/50">
                    <h4 class="text-lg font-semibold text-indigo-300 mb-4" id="form-title">Add New Product</h4>
                    <form id="product-form" onsubmit="handleProductFormSubmit(event)">
                        <input type="hidden" id="product-doc-id" value="">
                        <div class="space-y-3">
                            <input type="text" id="product-name" class="admin-input" placeholder="Product Name" required>
                            <input type="number" id="product-price" class="admin-input" placeholder="Price (e.g., 45.00)" step="0.01" required>
                            <input type="number" id="product-line-through-price" class="admin-input" placeholder="Old Price (Optional, e.g., 55.00)" step="0.01">
                            <input type="text" id="product-img" class="admin-input" placeholder="Image URL (e.g., https://i.ibb.co/...)" required>
                            <input type="text" id="product-badge" class="admin-input" placeholder="Badge Text (e.g., Best Seller)">
                            <button type="submit" id="product-form-button" class="w-full py-3 bg-indigo-600 text-white font-bold rounded-lg hover:bg-indigo-700 transition">Add Product</button>
                            <button type="button" onclick="resetForm()" class="w-full py-3 bg-gray-600 text-white font-bold rounded-lg hover:bg-gray-700 transition">Cancel / New</button>
                        </div>
                    </form>
                </div>

                <div class="p-4 bg-gray-900/50 rounded-xl border border-gray-700/50 mb-8">
                    <h4 class="text-lg font-semibold text-indigo-300 mb-4">Existing Products</h4>
                    <ul id="admin-product-list" class="space-y-3">
                        <li class="text-gray-400">Loading products...</li>
                    </ul>
                </div>
                
                <div id="orders-panel" class="p-4 bg-red-900/40 rounded-xl border border-red-700/50">
                    <h4 class="text-xl font-extrabold text-red-300 mb-4 flex items-center">
                        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-box-select mr-2"><path d="M21.5 5.5a2.5 2.5 0 0 0-2.5-2.5H6l2 4 4-4 4 4 2-4h2a2.5 2.5 0 0 1 2.5 2.5v2L19 12l2 4v2.5a2.5 2.5 0 0 1-2.5 2.5H6l-2-4-2-4v-2L5 9l-2-4v-2.5a2.5 2.5 0 0 1 2.5-2.5H18l-4 4-4-4-4 4-2-4H5a2.5 2.5 0 0 0-2.5 2.5v2.5L5 9l2 4v2.5a2.5 2.5 0 0 0 2.5 2.5h10.5a2.5 2.5 0 0 0 2.5-2.5v-2L19 12l-2-4v-2.5a2.5 2.5 0 0 1 2.5-2.5z"/></svg>
                        PENDING ORDERS
                    </h4>
                    <ul id="admin-orders-list-dynamic" class="space-y-4">
                        <li class="text-gray-400">Loading orders...</li>
                    </ul>
                </div>
            `;
            // Re-assign the dynamic elements
            window.adminOrdersListDynamic = document.getElementById('admin-orders-list-dynamic');
            window.adminProductList = document.getElementById('admin-product-list');
            window.productDocIdInput = document.getElementById('product-doc-id');
            window.productNameInput = document.getElementById('product-name');
            window.productPriceInput = document.getElementById('product-price');
            window.productLineThroughPriceInput = document.getElementById('product-line-through-price');
            window.productImgInput = document.getElementById('product-img');
            window.productBadgeInput = document.getElementById('product-badge');
            window.formTitle = document.getElementById('form-title');
            window.formButton = document.getElementById('product-form-button');
            
            authHeaderTitle.textContent = 'ADMIN PRODUCT MANAGER';
            renderAdminProductList(); // Re-render product list
            renderOrdersList(); // NEW: Re-render orders list
        } else {
            // Show a message if not admin
            adminPanel.classList.remove('hidden');
            adminPanel.innerHTML = '<div class="p-6 bg-red-900/40 rounded-xl text-center"><h3 class="text-xl font-bold text-white mb-2">Access Denied</h3><p class="text-gray-300">This panel is for administrators only.</p></div>';
            authHeaderTitle.textContent = 'ACCESS DENIED';
        }
    }


    // --- Product Management (Admin/Shop) Functions (Unchanged logic, minor change to list element in admin view) ---

    /** Renders the shop view using data from Firestore. (No change) */
    function renderShop() {
        productGrid.innerHTML = '';
        const items = Object.values(currentProductsMap);
        
        if (!productsLoaded || items.length === 0) {
            shopLoadingMessage.classList.remove('hidden');
            productGrid.innerHTML = '';
            productGrid.appendChild(shopLoadingMessage);
            if (productsLoaded && items.length === 0) {
                 shopLoadingMessage.textContent = 'No products available right now!';
            } else if (!productsLoaded) {
                 shopLoadingMessage.textContent = 'Loading products...';
            }
            return;
        }

        shopLoadingMessage.classList.add('hidden');
        
        items.forEach(product => {
            const lineThrough = product.lineThroughPrice ? `<p class="text-xs text-gray-400 line-through mb-2">$${Number(product.lineThroughPrice).toFixed(2)}</p>` : `<p class="text-xs text-gray-400 mb-2 invisible"></p>`;
            const productHtml = `
                <div class="product-card bg-gray-900/50 p-2 shadow-2xl flex flex-col">
                    <div class="relative mb-2 rounded-lg overflow-hidden h-36">
                        <img src="${product.img}" onerror="this.onerror=null;this.src='https://placehold.co/400x400/312e81/ffffff?text=Image+Error';" alt="${product.name}" class="w-full h-full object-cover">
                        <span class="product-badge official-store-badge">${product.badge || 'New'}</span>
                        <button class="absolute top-2 right-2 text-white/70 hover:text-pink-400 transition">
                            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-heart"><path d="M19 14c1.49-1.46 3-3.23 3-5.5A5.5 5.5 0 0 0 16.5 3c-1.76 0-3 .5-4.5 2-1.5-1.5-2.74-2-4.5-2A5.5 5.5 0 0 0 2 8.5c0 2.27 1.51 4.04 3 5.5l7 7Z"/></svg>
                        </button>
                    </div>
                    <div class="flex flex-col flex-grow">
                        <p class="text-sm font-medium text-gray-200 leading-tight flex-grow">${product.name}</p>
                        <div class="flex items-center text-xs my-1">
                            <span class="text-pink-400">★★★★★</span>
                            <span class="text-gray-500 ml-1">(0)</span>
                        </div>
                        <p class="text-lg font-bold text-white mt-1">$${Number(product.price).toFixed(2)}</p>
                        ${lineThrough}
                        <button onclick="addToCart('${product.docId}')" class="w-full py-2 bg-indigo-600 text-white text-sm font-semibold rounded-lg hover:bg-indigo-700 transition duration-200">
                            Add to cart
                        </button>
                    </div>
                </div>
            `;
            productGrid.insertAdjacentHTML('beforeend', productHtml);
        });
    }

    /** Renders the admin product list using data from Firestore. */
    function renderAdminProductList() {
        if (!window.adminProductList) return; // Check if the element exists in the current view

        window.adminProductList.innerHTML = '';
        const items = Object.values(currentProductsMap);

        if (items.length === 0) {
            window.adminProductList.innerHTML = '<li class="text-gray-400">No products in the database.</li>';
            return;
        }

        items.forEach(product => {
            const lineThroughInfo = product.lineThroughPrice ? ` (Old: $${Number(product.lineThroughPrice).toFixed(2)})` : '';
            const listItem = `
                <li class="flex justify-between items-center p-3 bg-gray-800/70 rounded-lg border-l-4 border-indigo-400/70">
                    <div class="flex-grow min-w-0 pr-2">
                        <p class="text-white font-semibold truncate">${product.name}</p>
                        <p class="text-xs text-indigo-300">$${Number(product.price).toFixed(2)}${lineThroughInfo}</p>
                    </div>
                    <div class="flex space-x-2 flex-shrink-0">
                        <button onclick="editProduct('${product.docId}')" class="bg-blue-600 hover:bg-blue-700 text-white p-2 rounded-lg text-xs font-bold transition">Edit</button>
                        <button onclick="deleteProduct('${product.docId}')" class="bg-red-600 hover:bg-red-700 text-white p-2 rounded-lg text-xs font-bold transition">Delete</button>
                    </div>
                </li>
            `;
            window.adminProductList.insertAdjacentHTML('beforeend', listItem);
        });
    }

    /** Starts the real-time listener for public products. (Unchanged) */
    function loadProductsListener() {
        if (productsListenerUnsubscribe) productsListenerUnsubscribe(); // Stop existing listener

        const productsRef = getProductsCollectionRef();
        if (!productsRef) return;

        productsListenerUnsubscribe = onSnapshot(productsRef, (snapshot) => {
            currentProductsMap = {};
            snapshot.forEach((doc) => {
                const product = doc.data();
                currentProductsMap[doc.id] = { docId: doc.id, ...product };
            });

            productsLoaded = true;
            renderShop();
            if (isCurrentUserAdmin) {
                renderAdminProductList();
            }
            renderCart(); // Re-render the cart in case prices changed

        }, (error) => {
            console.error("Error listening to products: ", error);
            shopLoadingMessage.textContent = 'Error loading products.';
        });
    }

    // --- Admin CRUD Functions (Unchanged logic, minor variable/element updates) ---

    /** Handles product form submission (Add or Edit). */
    async function handleProductFormSubmit(event) {
        event.preventDefault();

        if (!isCurrentUserAdmin) {
            alertMessage("Authorization failed. You are not the admin.");
            return;
        }

        const docId = window.productDocIdInput.value.trim();
        const name = window.productNameInput.value.trim();
        const price = parseFloat(window.productPriceInput.value);
        const img = window.productImgInput.value.trim();
        const badge = window.productBadgeInput.value.trim();
        const lineThroughPriceValue = window.productLineThroughPriceInput.value.trim();
        const lineThroughPrice = lineThroughPriceValue ? parseFloat(lineThroughPriceValue) : null;
        
        if (!name || isNaN(price) || price <= 0 || !img) {
            alertMessage("Please fill out all required fields (Name, Price, Image URL) correctly.");
            return;
        }

        const productData = {
            name: name,
            price: price,
            img: img,
            badge: badge || 'New',
            lineThroughPrice: lineThroughPrice
        };

        const productsRef = getProductsCollectionRef();
        if (!productsRef) return;

        try {
            if (docId) {
                const docRef = doc(productsRef, docId);
                await updateDoc(docRef, productData);
                alertMessage(`Product "${name}" updated successfully!`);
            } else {
                await addDoc(productsRef, productData);
                alertMessage(`New product "${name}" added successfully!`);
            }
            resetForm();
        } catch (e) {
            console.error("Error saving product: ", e);
            alertMessage("Error: Could not save product. Check console for details.");
        }
    }

    /** Pre-fills the form to edit an existing product. */
    function editProduct(docId) {
        const product = currentProductsMap[docId];
        if (!product) {
            alertMessage("Product not found for editing.");
            return;
        }

        window.productDocIdInput.value = docId;
        window.productNameInput.value = product.name;
        window.productPriceInput.value = product.price;
        window.productImgInput.value = product.img;
        window.productBadgeInput.value = product.badge || '';
        window.productLineThroughPriceInput.value = product.lineThroughPrice || '';

        window.formTitle.textContent = `Edit Product: ${product.name}`;
        window.formButton.textContent = 'Update Product';

        mainContent.scrollTop = 0;
    }

    /** Resets the admin form to 'Add New Product' state. */
    function resetForm() {
        if (!window.productForm) return; // Guard for non-admin view
        window.productForm.reset();
        window.productDocIdInput.value = '';
        window.formTitle.textContent = 'Add New Product';
        window.formButton.textContent = 'Add Product';
    }

    /** Deletes a product from Firestore. (Unchanged logic) */
    async function deleteProduct(docId) {
        if (!isCurrentUserAdmin) {
            alertMessage("Authorization failed. You are not the admin.");
            return;
        }

        const product = currentProductsMap[docId];
        const confirmation = await confirmAction(`Are you sure you want to delete "${product ? product.name : 'this product'}"?`);
        
        if (!confirmation) return;

        const productsRef = getProductsCollectionRef();
        if (!productsRef) return;

        try {
            const docRef = doc(productsRef, docId);
            await deleteDoc(docRef);
            alertMessage(`Product deleted successfully.`);
            resetForm(); 
        } catch (e) {
            console.error("Error deleting product: ", e);
            alertMessage("Error: Could not delete product.");
        }
    }

    // --- NEW: Order Management Functions ---

    /** Starts the real-time listener for pending customer orders. */
    function loadOrdersListener() {
        if (ordersListenerUnsubscribe) ordersListenerUnsubscribe(); 

        const ordersRef = getOrdersCollectionRef();
        if (!ordersRef) return;

        ordersListenerUnsubscribe = onSnapshot(ordersRef, (snapshot) => {
            currentOrders = {};
            snapshot.forEach((doc) => {
                currentOrders[doc.id] = { docId: doc.id, ...doc.data() };
            });
            renderOrdersList();

        }, (error) => {
            console.error("Error listening to orders: ", error);
        });
    }

    /** Renders the list of pending orders in the Admin panel. */
    function renderOrdersList() {
        if (!window.adminOrdersListDynamic) return; // Check if the element exists in the current view

        const items = Object.values(currentOrders);
        window.adminOrdersListDynamic.innerHTML = '';

        if (items.length === 0) {
            window.adminOrdersListDynamic.innerHTML = '<li class="text-gray-400 p-4 text-center">No pending orders! 🎉</li>';
            return;
        }

        items.sort((a, b) => b.timestamp - a.timestamp); // Sort by newest first

        items.forEach(order => {
            const date = new Date(order.timestamp).toLocaleString();
            const total = order.total.toFixed(2);
            
            // Generate a list of cart items for display
            const cartList = order.cartItems.map(item => 
                `<li class="text-xs text-gray-400 ml-3 list-disc">${item.data.name} (x${item.quantity}) - $${(item.data.price * item.quantity).toFixed(2)}</li>`
            ).join('');

            const listItem = `
                <li class="p-4 bg-gray-800/70 rounded-xl border-l-4 border-red-400/70 shadow-lg">
                    <p class="text-xs text-gray-500 mb-1">Order ID: ${order.docId.substring(0, 8)}...</p>
                    <p class="text-lg font-bold text-white mb-2">Total: <span class="text-red-400">$${total}</span></p>
                    
                    <div class="text-sm space-y-1 mb-3">
                        <p class="text-indigo-300 font-semibold">👤 ${order.customerInfo.name}</p>
                        <p class="text-gray-300">📞 ${order.customerInfo.phone}</p>
                        <p class="text-gray-300">🏠 ${order.customerInfo.address}</p>
                        <p class="text-xs text-gray-500 mt-2">Ordered on: ${date}</p>
                    </div>

                    <h5 class="text-sm font-semibold text-indigo-400 mt-3">Items:</h5>
                    <ul class="mb-3 pl-2">${cartList}</ul>

                    <button onclick="fulfillOrder('${order.docId}')" class="w-full py-2 bg-green-600 text-white font-bold rounded-lg hover:bg-green-700 transition">
                        Mark as Fulfilled
                    </button>
                </li>
            `;
            window.adminOrdersListDynamic.insertAdjacentHTML('beforeend', listItem);
        });
    }

    /** Deletes an order from Firestore, marking it as fulfilled/processed. */
    async function fulfillOrder(docId) {
        if (!isCurrentUserAdmin) {
            alertMessage("Authorization failed. You are not the admin.");
            return;
        }
        
        const confirmation = await confirmAction(`Mark order ${docId.substring(0, 8)}... as Fulfilled? This action cannot be undone.`);
        
        if (!confirmation) return;

        const ordersRef = getOrdersCollectionRef();
        if (!ordersRef) return;

        try {
            const docRef = doc(ordersRef, docId);
            await deleteDoc(docRef);
            alertMessage(`Order fulfilled and removed.`);
        } catch (e) {
            console.error("Error fulfilling order: ", e);
            alertMessage("Error: Could not fulfill order.");
        }
    }

    // --- Cart Persistence Functions ---
    
    /** Adds an item to the cart or increments its quantity. (Unchanged) */
    async function addToCart(docId) {
        const productData = currentProductsMap[docId];
        if (!productData) {
            alertMessage("Product data not found. Please try again later.");
            return;
        }

        const cartRef = getCartCollectionRef();
        if (!cartRef) return;

        const existingItem = Object.values(currentCartItems).find(item => item.data.docId === docId);

        try {
            if (existingItem) {
                const cartDocRef = doc(cartRef, existingItem.cartDocId);
                const newQuantity = existingItem.quantity + 1;
                await updateDoc(cartDocRef, {
                    quantity: newQuantity
                });
                alertMessage(`Added another ${productData.name}! Total: ${newQuantity}`);
            } else {
                await addDoc(cartRef, {
                    productDocId: docId, 
                    quantity: 1,
                    timestamp: Date.now()
                });
                alertMessage(`${productData.name} added to cart!`);
            }
        } catch (e) {
            console.error("Error adding/updating document: ", e);
            alertMessage("Error: Could not update cart. Check console for details.");
        }
    }

    /** Updates the quantity of an item or removes it if quantity is zero. (Unchanged) */
    async function updateCartItemQuantity(cartDocId, change) {
        const cartRef = getCartCollectionRef();
        if (!cartRef) return;

        const cartItem = currentCartItems[cartDocId];
        if (!cartItem) {
            console.error("Cart item not found:", cartDocId);
            return;
        }

        const newQuantity = cartItem.quantity + change;
        const docRef = doc(cartRef, cartDocId);

        try {
            if (newQuantity <= 0) {
                await deleteDoc(docRef);
                alertMessage(`${cartItem.data.name} removed from cart.`);
            } else {
                await updateDoc(docRef, {
                    quantity: newQuantity
                });
            }
        } catch (e) {
            console.error("Error updating/deleting document: ", e);
            alertMessage("Error: Could not update cart item quantity.");
        }
    }

    /** Starts the real-time listener for the user's cart. (Unchanged) */
    function startCartListener() {
        if (cartListenerUnsubscribe) {
            cartListenerUnsubscribe(); 
        }

        const cartRef = getCartCollectionRef();
        if (!cartRef) return;

        const q = query(cartRef);

        cartListenerUnsubscribe = onSnapshot(q, (snapshot) => {
            currentCartItems = {};
            let total = 0;

            snapshot.forEach((doc) => {
                const item = doc.data();
                const productData = currentProductsMap[item.productDocId]; 

                if (productData) {
                    currentCartItems[doc.id] = {
                        cartDocId: doc.id,
                        quantity: item.quantity,
                        data: productData 
                    };
                    total += item.quantity * productData.price;
                } else {
                    console.warn(`Product reference ID ${item.productDocId} not found in product catalog.`);
                }
            });

            renderCart(total);

        }, (error) => {
            console.error("Error listening to cart changes: ", error);
            alertMessage("Error loading cart data in real-time.");
        });
    }

    /** Renders the cart items and updates the total/subtotal. (Unchanged) */
    function renderCart(total = null) {
        const items = Object.values(currentCartItems);
        cartItemsContainer.innerHTML = '';
        
        let calculatedTotal = 0;

        // NEW: Disable checkout form if cart is empty
        if (items.length === 0) {
            cartEmptyMessage.classList.remove('hidden');
            checkoutForm.classList.add('opacity-50', 'pointer-events-none');
        } else {
            cartEmptyMessage.classList.add('hidden');
            checkoutForm.classList.remove('opacity-50', 'pointer-events-none');
            items.forEach(item => {
                const subtotal = (item.quantity * item.data.price).toFixed(2);
                calculatedTotal += parseFloat(subtotal);

                const itemHtml = `
                    <div class="flex items-center bg-indigo-900/40 p-3 rounded-xl shadow-lg border border-indigo-700/50">
                        <img src="${item.data.img}" onerror="this.onerror=null;this.src='https://placehold.co/100x100/1e072b/ffffff?text=Product';" alt="${item.data.name}" class="w-16 h-16 rounded-lg object-cover mr-3 flex-shrink-0">
                        <div class="flex-grow">
                            <p class="text-white font-semibold leading-tight">${item.data.name}</p>
                            <p class="text-indigo-300 text-sm">$${Number(item.data.price).toFixed(2)} / item</p>
                        </div>
                        <div class="flex flex-col items-end flex-shrink-0">
                            <div class="flex items-center space-x-2 mb-2">
                                <button onclick="updateCartItemQuantity('${item.cartDocId}', -1)" class="qty-btn">-</button>
                                <span class="text-white font-bold text-lg">${item.quantity}</span>
                                <button onclick="updateCartItemQuantity('${item.cartDocId}', 1)" class="qty-btn">+</button>
                            </div>
                            <p class="text-pink-400 font-extrabold text-lg">$${subtotal}</p>
                        </div>
                    </div>
                `;
                cartItemsContainer.insertAdjacentHTML('beforeend', itemHtml);
            });
        }

        const finalTotal = (total !== null ? total : calculatedTotal).toFixed(2);
        cartSubtotal.textContent = `$${finalTotal}`;
        cartTotal.textContent = `$${finalTotal}`;
    }

    // --- NEW: Checkout Logic ---
    
    /**
     * Handles the checkout form submission, saves the order, and clears the cart.
     * @param {Event} event - The form submission event.
     */
    async function handleCheckout(event) {
        event.preventDefault();

        const cartItemsArray = Object.values(currentCartItems);
        if (cartItemsArray.length === 0) {
            alertMessage("Your cart is empty. Please add products before checking out!");
            return;
        }

        const name = customerNameInput.value.trim();
        const phone = customerPhoneInput.value.trim();
        const address = customerAddressInput.value.trim();
        const total = parseFloat(cartTotal.textContent.replace('$', ''));

        if (!name || !phone || !address || isNaN(total) || total <= 0) {
             alertMessage("Please fill in your Full Name, Phone Number, and Shipping Address.");
            return;
        }

        const ordersRef = getOrdersCollectionRef();
        if (!ordersRef) return;
        
        const customerInfo = { name, phone, address };
        
        // Prepare cart items for storage (strip unneeded live references)
        const orderCartItems = cartItemsArray.map(item => ({
            quantity: item.quantity,
            // Only save necessary product details to prevent large duplication
            data: {
                docId: item.data.docId,
                name: item.data.name,
                price: item.data.price,
                img: item.data.img 
            }
        }));

        const orderData = {
            userId: userId,
            customerInfo: customerInfo,
            cartItems: orderCartItems,
            total: total,
            timestamp: Date.now(),
            status: 'Pending'
        };

        // Disable button during submission
        document.getElementById('checkout-button').disabled = true;
        document.getElementById('checkout-button').innerHTML = 'Processing Order...';

        try {
            // 1. Save the new order to the 'orders' collection
            await addDoc(ordersRef, orderData);
            
            // 2. Clear the user's cart by deleting all cart items in the user's private cart subcollection
            const cartRef = getCartCollectionRef();
            const deletePromises = cartItemsArray.map(item => 
                deleteDoc(doc(cartRef, item.cartDocId))
            );
            await Promise.all(deletePromises);
            
            // 3. Success message and redirect (or stay)
            alertMessage("🎉 Order Placed Successfully! The admin has been notified. We will contact you shortly to confirm and arrange delivery.");
            checkoutForm.reset();
            navigateTo('home'); // Go to home after successful checkout

        } catch (e) {
            console.error("Error during checkout process: ", e);
            alertMessage("Error: Could not place your order. Please try again.");
        } finally {
            // Re-enable button
            document.getElementById('checkout-button').disabled = false;
            document.getElementById('checkout-button').innerHTML = `
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-credit-card mr-3"><rect width="20" height="14" x="2" y="5" rx="2"/><line x1="2" x2="22" y1="10" y2="10"/></svg>
                PROCEED TO CHECKOUT
            `;
        }
    }


    // --- Utility Functions (Alert/Confirmation) (Unchanged) ---

    /** Shows a custom message box instead of using alert() */
    function alertMessage(message) {
        messageText.textContent = message;
        messageBox.classList.add('flex');
        messageBox.classList.remove('hidden');
    }

    /** Hides the custom message box. */
    function hideMessage() {
        messageBox.classList.remove('flex');
        messageBox.classList.add('hidden');
    }

    /** Shows a custom confirmation dialog and returns a Promise that resolves to true/false. */
    function confirmAction(message) {
        return new Promise((resolve) => {
            confirmationText.textContent = message;
            confirmationBox.classList.add('flex');
            confirmationBox.classList.remove('hidden');
            
            resolveConfirmation = resolve;
        });
    }

    /** Event listeners for confirmation buttons (Unchanged) */
    confirmYesBtn.onclick = () => {
        confirmationBox.classList.remove('flex');
        confirmationBox.classList.add('hidden');
        if (resolveConfirmation) resolveConfirmation(true);
    };

    confirmNoBtn.onclick = () => {
        confirmationBox.classList.remove('flex');
        confirmationBox.classList.add('hidden');
        if (resolveConfirmation) resolveConfirmation(false);
    };

    // --- Utility Functions (Navigation - MODIFIED) ---

    /** Handles navigation between the main views. */
    function navigateTo(targetPage) {
        if (currentPage === targetPage) return;
        
        // START MODIFICATION: Admin Access Check
        if (targetPage === 'auth' && !isCurrentUserAdmin) {
            alertMessage("Access Denied: This panel is for administrators only.");
            return; 
        }
        // END MODIFICATION
        
        currentPage = targetPage;

        document.querySelectorAll('.page-view').forEach(view => {
            view.classList.add('hidden');
        });

        document.getElementById(`${targetPage}-view`).classList.remove('hidden');

        const isShop = targetPage === 'shop';
        if (isShop && window.innerWidth <= 600) { 
            mobileShopNav.classList.remove('hidden');
        } else {
            mobileShopNav.classList.add('hidden');
        }

        navButtons.forEach(button => {
            button.classList.remove('active-nav', 'text-indigo-400');
            button.classList.add('text-gray-400');
        });

        const activeNavButton = document.getElementById(`nav-${targetPage}`);
        if (activeNavButton) {
            activeNavButton.classList.add('active-nav', 'text-indigo-400');
            activeNavButton.classList.remove('text-gray-400');
        }

        if (targetPage === 'auth') {
            updateAdminAuthView();
        }

        mainContent.scrollTop = 0;
    }

    // --- Welcome Pop-up Function (Unchanged) ---
    function showWelcomeMessage() {
        const message = "welcome to **universe skincare shop**, here we only provide you with **original skincare products** that’ll help your skin glow, we also provide **nationwide delivery**";
        alertMessage(message);
    }

    // --- Global Export (UPDATED) ---
    window.alertMessage = alertMessage;
    window.hideMessage = hideMessage;
    window.navigateTo = navigateTo;
    window.addToCart = addToCart;
    window.updateCartItemQuantity = updateCartItemQuantity;
    window.handleProductFormSubmit = handleProductFormSubmit;
    window.editProduct = editProduct;
    window.deleteProduct = deleteProduct;
    window.resetForm = resetForm;
    window.confirmAction = confirmAction; 
    
    // NEW Exports
    window.handleCheckout = handleCheckout;
    window.fulfillOrder = fulfillOrder; 

    // --- Initial load setup (Unchanged) ---
    window.onload = function() {
        initializeFirebase();
        navigateTo('home');
        showWelcomeMessage(); 
    };

    window.addEventListener('resize', () => {
        if (currentPage === 'shop' && window.innerWidth <= 600) {
            mobileShopNav.classList.remove('hidden');
        } else {
            mobileShopNav.classList.add('hidden');
        }
    });

</script>
</body>
</html>
