# My-KENZAZASTORE
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>𖤐 KENZ AZA STORE 𖤐</title>
    <style>
        /* ============================================================
           RESET + BASE
           ============================================================ */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html,
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            min-height: 100vh;
            background: #0b0f1a;
            color: #fff;
            overflow-x: hidden;
            overflow-y: auto;
        }

        body {
            display: flex;
            justify-content: center;
            align-items: flex-start;
            padding: 20px;
            position: relative;
            min-height: 100vh;
        }

        /* ============================================================
           BACKGROUND - SIMPLE TAPI ELEGAN (TANPA ANIMASI BERAT)
           ============================================================ */
        .bg-layer {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            background:
                radial-gradient(ellipse at 20% 50%, rgba(255, 68, 68, 0.12) 0%, transparent 55%),
                radial-gradient(ellipse at 80% 20%, rgba(255, 0, 200, 0.08) 0%, transparent 50%),
                radial-gradient(ellipse at 50% 80%, rgba(0, 200, 255, 0.06) 0%, transparent 50%),
                linear-gradient(160deg, #0a0e1a 0%, #141828 40%, #0f1422 70%, #0a0e1a 100%);
        }

        /* ============================================================
           CONTAINER UTAMA
           ============================================================ */
        .container-wrapper {
            max-width: 850px;
            width: 100%;
            position: relative;
            z-index: 1;
            margin: 20px auto;
            animation: fadeUp 0.6s ease;
        }

        @keyframes fadeUp {
            from {
                opacity: 0;
                transform: translateY(25px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .container {
            width: 100%;
            background: rgba(20, 28, 45, 0.7);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border-radius: 28px;
            padding: 30px 28px;
            border: 1px solid rgba(255, 255, 255, 0.05);
            box-shadow:
                0 30px 80px rgba(0, 0, 0, 0.6),
                inset 0 1px 0 rgba(255, 255, 255, 0.03);
            position: relative;
            overflow: visible;
        }

        /* ===== BORDER GLOW HALUS (TANPA ANIMASI BERAT) ===== */
        .container::before {
            content: '';
            position: absolute;
            top: -1px;
            left: -1px;
            right: -1px;
            bottom: -1px;
            background: conic-gradient(from 0deg, transparent, rgba(0, 255, 200, 0.06), transparent, rgba(255, 68, 68, 0.06), transparent);
            border-radius: 29px;
            z-index: -1;
            animation: borderRotate 12s linear infinite;
        }

        @keyframes borderRotate {
            0% {
                transform: rotate(0deg);
            }
            100% {
                transform: rotate(360deg);
            }
        }

        /* ============================================================
           SPLASH SCREEN (RINGAN)
           ============================================================ */
        .splash-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: #0b0f1a;
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 9999;
            transition: opacity 0.6s ease, transform 0.6s ease;
            pointer-events: all;
        }

        .splash-screen.hide {
            opacity: 0;
            pointer-events: none;
            transform: scale(1.02);
        }

        .splash-content {
            text-align: center;
            max-width: 450px;
            width: 90%;
            padding: 30px 20px;
            animation: fadeUp 0.6s ease;
        }

        .splash-content .logo-big {
            font-size: 65px;
            margin-bottom: 8px;
            display: block;
        }

        .splash-content h1 {
            font-size: 32px;
            font-weight: 900;
            background: linear-gradient(135deg, #ff4444, #ff8800, #ffcc00);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            letter-spacing: 1px;
            margin-bottom: 4px;
        }

        .splash-content .sub {
            color: #8892b0;
            font-size: 13px;
            letter-spacing: 3px;
            text-transform: uppercase;
            margin-bottom: 6px;
        }

        .splash-content .tagline {
            color: #495670;
            font-size: 12px;
            letter-spacing: 1px;
            margin-bottom: 25px;
            border-top: 1px solid rgba(255, 255, 255, 0.04);
            padding-top: 12px;
        }

        .splash-content .tagline span {
            color: #00ffc8;
            font-weight: 700;
        }

        .btn-enter {
            padding: 14px 45px;
            background: linear-gradient(135deg, #ff8800, #ffaa00);
            border: none;
            border-radius: 50px;
            color: #000;
            font-size: 18px;
            font-weight: 800;
            cursor: pointer;
            transition: transform 0.2s ease, box-shadow 0.2s ease;
            letter-spacing: 1px;
            box-shadow: 0 0 40px rgba(255, 136, 0, 0.1);
        }

        .btn-enter:hover {
            transform: scale(1.04);
            box-shadow: 0 0 60px rgba(255, 136, 0, 0.2);
        }

        .btn-enter:active {
            transform: scale(0.95);
        }

        .btn-enter .ripple {
            position: absolute;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.3);
            transform: scale(0);
            animation: rippleAnim 0.6s linear;
            pointer-events: none;
        }

        @keyframes rippleAnim {
            to {
                transform: scale(4);
                opacity: 0;
            }
        }

        .splash-content .decor-line {
            display: flex;
            justify-content: center;
            gap: 6px;
            margin: 12px 0;
        }
        .splash-content .decor-line span {
            width: 6px;
            height: 6px;
            border-radius: 50%;
            background: #ff8800;
            opacity: 0.4;
            animation: dotPulse 1.5s infinite alternate;
        }
        .splash-content .decor-line span:nth-child(2) {
            animation-delay: 0.3s;
            background: #ff4444;
        }
        .splash-content .decor-line span:nth-child(3) {
            animation-delay: 0.6s;
            background: #ffcc00;
        }

        @keyframes dotPulse {
            0% {
                opacity: 0.2;
                transform: scale(0.8);
            }
            100% {
                opacity: 1;
                transform: scale(1.2);
            }
        }

        /* ============================================================
           MAIN STORE
           ============================================================ */
        .main-store {
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.6s ease, transform 0.6s ease;
            pointer-events: none;
            width: 100%;
        }

        .main-store.show {
            opacity: 1;
            transform: translateY(0);
            pointer-events: all;
        }

        /* ============================================================
           HEADER
           ============================================================ */
        .header {
            text-align: center;
            margin-bottom: 22px;
        }

        .header h1 {
            font-size: 32px;
            font-weight: 800;
            background: linear-gradient(135deg, #ff4444, #ff8800, #ffcc00);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            letter-spacing: -0.5px;
            cursor: pointer;
            transition: 0.3s;
        }

        .header h1:hover {
            transform: scale(1.02);
        }

        .header .sub-title {
            color: #8892b0;
            font-size: 14px;
            margin-top: 4px;
            letter-spacing: 0.3px;
        }

        .header .sub-title span {
            color: #00ffc8;
            font-weight: 700;
        }

        /* ============================================================
           STATS
           ============================================================ */
        .stats {
            display: grid;
            grid-template-columns: 1fr;
            gap: 12px;
            margin: 20px 0;
        }

        .stat-card {
            background: rgba(255, 255, 255, 0.03);
            border-radius: 14px;
            padding: 18px 15px;
            text-align: center;
            border: 1px solid rgba(0, 255, 200, 0.06);
            transition: 0.3s;
        }

        .stat-card:hover {
            border-color: rgba(0, 255, 200, 0.15);
        }

        .stat-number {
            font-size: 20px;
            font-weight: 700;
            color: #00ffc8;
            letter-spacing: 0.5px;
        }

        .stat-label {
            font-size: 13px;
            color: #8892b0;
            margin-top: 3px;
        }

        /* ============================================================
           FEATURES - RAMBUTAN TAPI GAK GEDE
           ============================================================ */
        .features {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 14px;
            margin: 20px 0;
        }

        .feature-item {
            background: rgba(255, 255, 255, 0.03);
            border-radius: 14px;
            padding: 16px 12px;
            text-align: center;
            border: 1px solid rgba(255, 255, 255, 0.04);
            transition: 0.3s;
        }

        .feature-item:hover {
            border-color: rgba(0, 255, 200, 0.15);
            background: rgba(255, 255, 255, 0.05);
            transform: translateY(-2px);
        }

        .feature-item .icon {
            font-size: 26px;
            display: block;
            margin-bottom: 6px;
        }

        .feature-item h3 {
            font-size: 14px;
            font-weight: 700;
            color: #fff;
            margin-bottom: 3px;
        }

        .feature-item p {
            font-size: 12px;
            color: #8892b0;
            line-height: 1.4;
        }

        /* ============================================================
           PROJECT SELECTOR - 2 KOLOM
           ============================================================ */
        .project-selector {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 16px;
            margin: 22px 0;
        }

        .project-card {
            background: rgba(255, 255, 255, 0.03);
            border-radius: 18px;
            padding: 24px 15px;
            text-align: center;
            border: 2px solid rgba(255, 255, 255, 0.05);
            cursor: pointer;
            transition: 0.3s;
            position: relative;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 130px;
        }

        .project-card:hover {
            transform: translateY(-4px);
            border-color: rgba(0, 255, 200, 0.2);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }

        .project-card.otax {
            border-color: rgba(255, 68, 68, 0.15);
        }
        .project-card.otax:hover {
            border-color: #ff4444;
        }

        .project-card.mantax {
            border-color: rgba(255, 0, 255, 0.15);
        }
        .project-card.mantax:hover {
            border-color: #ff44ff;
        }

        .project-card .icon-big {
            font-size: 34px;
            margin-bottom: 6px;
        }

        .project-card h2 {
            font-size: 20px;
            font-weight: 800;
            margin-bottom: 3px;
        }

        .project-card.otax h2 {
            color: #ff4444;
        }
        .project-card.mantax h2 {
            color: #ff44ff;
        }

        .project-card p {
            color: #8892b0;
            font-size: 11px;
        }

        .project-status {
            position: absolute;
            top: 10px;
            right: 10px;
            font-size: 18px;
            line-height: 1;
        }

        .project-status.on {
            color: #00ffc8;
        }
        .project-status.off {
            color: #ff4444;
        }

        .project-selector.hidden {
            display: none;
        }

        /* ============================================================
           PRODUCT SECTION
           ============================================================ */
        .product-section {
            margin: 22px 0;
            display: none;
        }

        .product-section.active {
            display: block;
            animation: fadeIn 0.3s ease;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(12px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .product-section h2 {
            font-size: 20px;
            margin-bottom: 16px;
            color: #fff;
            text-align: center;
        }

        .product-section .back-btn {
            display: inline-block;
            background: rgba(255, 255, 255, 0.04);
            border: 1px solid rgba(255, 255, 255, 0.06);
            border-radius: 30px;
            padding: 6px 18px;
            color: #8892b0;
            cursor: pointer;
            font-size: 12px;
            margin-bottom: 16px;
            transition: 0.3s;
        }

        .product-section .back-btn:hover {
            border-color: #00ffc8;
            color: #00ffc8;
        }

        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(175px, 1fr));
            gap: 12px;
        }

        .product-card {
            background: rgba(255, 255, 255, 0.03);
            border-radius: 14px;
            padding: 16px 12px;
            text-align: center;
            border: 1px solid rgba(255, 255, 255, 0.05);
            transition: 0.3s;
            cursor: pointer;
            position: relative;
        }

        .product-card:hover {
            border-color: #00ffc8;
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
        }

        .product-status-small {
            position: absolute;
            top: 8px;
            right: 8px;
            font-size: 16px;
            line-height: 1;
        }

        .product-status-small.on {
            color: #00ffc8;
        }
        .product-status-small.off {
            color: #ff4444;
        }

        .product-card .level-badge {
            display: inline-block;
            padding: 3px 12px;
            border-radius: 20px;
            font-size: 10px;
            font-weight: 700;
            margin-bottom: 8px;
            background: #00ffc8;
            color: #000;
        }

        .product-card .level-badge.reseller {
            background: #00b4ff;
            color: #fff;
        }
        .product-card .level-badge.pt {
            background: #ff8800;
            color: #000;
        }
        .product-card .level-badge.tk {
            background: #ff44ff;
            color: #000;
        }
        .product-card .level-badge.mantax {
            background: #ff00ff;
            color: #fff;
        }
        .product-card .level-badge.custom {
            background: #ff6600;
            color: #000;
        }
        .product-card .level-badge.bulanan {
            background: #00ccff;
            color: #000;
        }

        .product-card h4 {
            font-size: 16px;
            margin-bottom: 4px;
            color: #fff;
        }

        .product-card .price {
            font-size: 18px;
            font-weight: 700;
            color: #00ffc8;
            margin: 8px 0 3px 0;
        }

        .product-card .price-note {
            font-size: 9px;
            color: #ff8800;
            font-weight: 600;
            letter-spacing: 0.3px;
            margin-bottom: 6px;
        }

        .product-card .stock {
            font-size: 11px;
            color: #00ffc8;
        }

        .product-card .stock .unlimited {
            color: #00ffc8;
            font-weight: 700;
        }

        .order-btn {
            display: inline-block;
            padding: 8px 20px;
            background: linear-gradient(135deg, #00ffc8, #00b4ff);
            border-radius: 30px;
            color: #000;
            font-weight: 700;
            font-size: 13px;
            transition: 0.3s;
            border: none;
            cursor: pointer;
            margin-top: 8px;
            width: 100%;
        }

        .order-btn:hover {
            transform: scale(1.03);
            box-shadow: 0 0 25px rgba(0, 255, 200, 0.15);
        }

        .order-btn.mantax-btn {
            background: linear-gradient(135deg, #ff00ff, #ff44ff);
        }
        .order-btn.custom-btn {
            background: linear-gradient(135deg, #ff6600, #ffaa00);
        }
        .order-btn.bulanan-btn {
            background: linear-gradient(135deg, #00ccff, #0066ff);
        }

        /* ============================================================
           FOOTER
           ============================================================ */
        .footer {
            text-align: center;
            margin-top: 25px;
            padding-top: 16px;
            border-top: 1px solid rgba(255, 255, 255, 0.03);
            color: #495670;
            font-size: 12px;
        }

        .footer a {
            color: #00ffc8;
            text-decoration: none;
        }

        /* ============================================================
           PAYMENT MODAL
           ============================================================ */
        .payment-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
            backdrop-filter: blur(8px);
            z-index: 9999;
            justify-content: center;
            align-items: center;
            padding: 20px;
            animation: fadeIn 0.25s ease;
        }

        .payment-modal.show {
            display: flex;
        }

        .payment-modal .modal-box {
            background: #1a2332;
            border-radius: 20px;
            padding: 25px 22px;
            max-width: 380px;
            width: 100%;
            border: 1px solid rgba(0, 255, 200, 0.1);
            box-shadow: 0 30px 80px rgba(0, 0, 0, 0.6);
        }

        .payment-modal .modal-box h2 {
            font-size: 20px;
            text-align: center;
            margin-bottom: 4px;
            color: #fff;
        }

        .payment-modal .modal-box .modal-sub {
            text-align: center;
            color: #8892b0;
            font-size: 13px;
            margin-bottom: 10px;
        }

        .payment-modal .modal-box .product-info {
            background: rgba(255, 255, 255, 0.04);
            border-radius: 10px;
            padding: 10px 12px;
            margin: 8px 0 16px;
            text-align: center;
        }

        .payment-modal .modal-box .product-info .pname {
            color: #00ffc8;
            font-weight: 700;
            font-size: 15px;
        }

        .payment-modal .modal-box .product-info .pprice {
            color: #fff;
            font-size: 17px;
            font-weight: 700;
            margin-top: 3px;
        }

        .payment-modal .modal-box .product-info .pnote {
            color: #ff8800;
            font-size: 10px;
            font-weight: 600;
            margin-top: 4px;
            letter-spacing: 0.3px;
        }

        .payment-options {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 10px;
            margin: 12px 0;
        }

        .payment-options .pay-btn {
            padding: 12px 8px;
            border-radius: 12px;
            border: 2px solid rgba(255, 255, 255, 0.06);
            background: rgba(255, 255, 255, 0.02);
            color: #fff;
            font-weight: 700;
            font-size: 14px;
            cursor: pointer;
            transition: 0.3s;
            text-align: center;
        }

        .payment-options .pay-btn:hover {
            transform: translateY(-2px);
        }

        .payment-options .pay-btn.full {
            border-color: #00ffc8;
        }
        .payment-options .pay-btn.full:hover {
            background: #00ffc8;
            color: #000;
            box-shadow: 0 0 25px rgba(0, 255, 200, 0.15);
        }

        .payment-options .pay-btn.dp {
            border-color: #ff8800;
        }
        .payment-options .pay-btn.dp:hover {
            background: #ff8800;
            color: #000;
            box-shadow: 0 0 25px rgba(255, 136, 0, 0.15);
        }

        .payment-options .pay-btn .sub {
            font-size: 10px;
            font-weight: 400;
            color: #8892b0;
            display: block;
            margin-top: 2px;
        }

        .payment-options .pay-btn .sub.highlight {
            color: #00ffc8;
        }

        .payment-options .pay-btn.dp.hidden {
            display: none;
        }

        .payment-options .pay-btn.full.only {
            grid-column: 1 / -1;
        }

        .modal-close {
            display: block;
            width: 100%;
            padding: 10px;
            margin-top: 8px;
            background: rgba(255, 255, 255, 0.03);
            border: 1px solid rgba(255, 255, 255, 0.06);
            border-radius: 12px;
            color: #8892b0;
            font-size: 13px;
            cursor: pointer;
            transition: 0.3s;
            text-align: center;
        }

        .modal-close:hover {
            border-color: #ff4444;
            color: #ff4444;
        }

        /* ============================================================
           TOAST
           ============================================================ */
        .toast-notif {
            position: fixed;
            bottom: 25px;
            left: 50%;
            transform: translateX(-50%);
            background: rgba(20, 28, 45, 0.95);
            backdrop-filter: blur(8px);
            border: 1px solid #ff4444;
            border-radius: 14px;
            padding: 14px 22px;
            max-width: 380px;
            width: 90%;
            text-align: center;
            z-index: 99999;
            animation: slideUp 0.4s ease;
            box-shadow: 0 15px 50px rgba(0, 0, 0, 0.4);
        }

        .toast-notif .toast-title {
            font-size: 16px;
            font-weight: 800;
            color: #ff4444;
        }

        .toast-notif .toast-msg {
            font-size: 12px;
            color: #ffaaaa;
            margin-top: 3px;
        }

        .toast-notif .toast-icon {
            font-size: 24px;
            display: block;
            margin-bottom: 3px;
        }

        @keyframes slideUp {
            from {
                opacity: 0;
                transform: translateX(-50%) translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateX(-50%) translateY(0);
            }
        }

        /* ============================================================
           RESPONSIVE
           ============================================================ */
        @media (max-width: 600px) {
            .features {
                grid-template-columns: 1fr;
                gap: 10px;
            }

            .project-selector {
                grid-template-columns: 1fr 1fr;
                gap: 12px;
            }

            .project-card {
                padding: 18px 12px;
                min-height: 110px;
            }

            .project-card .icon-big {
                font-size: 28px;
            }
            .project-card h2 {
                font-size: 17px;
            }

            .container {
                padding: 18px 14px;
            }
            .header h1 {
                font-size: 26px;
            }
            .payment-options {
                grid-template-columns: 1fr;
            }
            .product-grid {
                grid-template-columns: 1fr 1fr;
            }
            .container-wrapper {
                margin: 10px auto;
            }
            .feature-item {
                padding: 14px 12px;
            }
            .feature-item .icon {
                font-size: 22px;
            }
            .feature-item h3 {
                font-size: 13px;
            }
            .feature-item p {
                font-size: 11px;
            }
        }

        @media (max-width: 400px) {
            .project-selector {
                grid-template-columns: 1fr 1fr;
                gap: 10px;
            }
            .project-card {
                padding: 14px 8px;
                min-height: 95px;
            }
            .project-card .icon-big {
                font-size: 24px;
            }
            .project-card h2 {
                font-size: 15px;
            }
            .product-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>

    <!-- ============================================================
    BACKGROUND
    ============================================================ -->
    <div class="bg-layer"></div>

    <!-- ============================================================
    SPLASH SCREEN
    ============================================================ -->
    <div class="splash-screen" id="splashScreen">
        <div class="splash-content">
            <span class="logo-big">👻</span>
            <h1>WELCOME TO</h1>
            <h1 style="font-size:34px; margin-top:-4px;">KENZ AZA STORE</h1>
            <div class="sub">✦ WEB BUY APK BUG ✦</div>
            <div class="decor-line">
                <span></span>
                <span></span>
                <span></span>
            </div>
            <div class="tagline">
                <span>🔥</span> TERPERCAYA & AUTOMATIC <span>🔥</span>
            </div>
            <button class="btn-enter" id="enterBtn">🚀 BUKA STORE</button>
        </div>
    </div>

    <!-- ============================================================
    MAIN STORE
    ============================================================ -->
    <div class="main-store" id="mainStore">
        <div class="container-wrapper">
            <div class="container" id="appContainer">
                <!-- HEADER -->
                <div class="header">
                    <h1>🔥 ORDER APK BUG</h1>
                    <div class="sub-title">Powered by <span>KENZ AZA STORE</span> • Terpercaya & Automatic</div>
                </div>

                <!-- STATS -->
                <div class="stats">
                    <div class="stat-card">
                        <div class="stat-number">🔥 SELAMAT DATANG DI KENZ AZA STORE</div>
                        <div class="stat-label">JIKA MAU ORDER ADA TULISAN OFF BERARTI SELLER BELUM BISA MEMBUAT AKUN BUYER</div>
                    </div>
                </div>

                <!-- ============================================================
                FEATURES - RINGAN & GAK GEDE
                ============================================================ -->
                <div class="features">
                    <div class="feature-item">
                        <span class="icon">⚡</span>
                        <h3>Proses Instan</h3>
                        <p>Transaksi otomatis dalam hitungan detik.</p>
                    </div>
                    <div class="feature-item">
                        <span class="icon">🔒</span>
                        <h3>Keamanan Terjamin</h3>
                        <p>Sistem terenkripsi & aman.</p>
                    </div>
                    <div class="feature-item">
                        <span class="icon">🛡️</span>
                        <h3>Support 24/7</h3>
                        <p>Tim siap bantu kapan saja.</p>
                    </div>
                </div>

                <!-- ============================================================
                PROJECT SELECTOR - 2 KOLOM
                ============================================================ -->
                <div class="project-selector" id="projectSelector">
                    <div class="project-card otax" onclick="selectProject('otax')" id="projectOtax">
                        <div class="icon-big">🔶</div>
                        <h2>Project OTAX</h2>
                        <p>Klik untuk lihat daftar</p>
                        <div class="project-status" id="statusOtax">✅</div>
                    </div>
                    <div class="project-card mantax" onclick="selectProject('mantax')" id="projectMantax">
                        <div class="icon-big">🔷</div>
                        <h2>Project MANTAX</h2>
                        <p>Klik untuk lihat daftar</p>
                        <div class="project-status" id="statusMantax">✅</div>
                    </div>
                </div>

                <!-- OTAX SECTION -->
                <div class="product-section" id="otaxSection">
                    <button class="back-btn" onclick="backToProject()">⬅ Kembali ke Pilihan Project</button>
                    <h2>📦 Pilih Project OTAX</h2>
                    <div class="product-grid">
                        <div class="product-card" data-product="OTAX FULL UP" data-price="60000" data-project="OTAX">
                            <div class="product-status-small" id="otax-fullup">✅</div>
                            <span class="level-badge">FULL UP</span>
                            <h4>OTAX FULL UP</h4>
                            <div class="price">Rp 60.000</div>
                            <div class="price-note">⏳ BATAS PELUNASAN 2 MINGGU / 14 HARI</div>
                            <div class="stock">♾️ <span class="unlimited">Unlimited</span></div>
                            <button class="order-btn" onclick="openPayment('OTAX FULL UP', 60000, 'OTAX')">Order Sekarang</button>
                        </div>
                        <div class="product-card" data-product="RESELLER OTAX" data-price="80000" data-project="OTAX">
                            <div class="product-status-small" id="otax-reseller">✅</div>
                            <span class="level-badge reseller">RESELLER</span>
                            <h4>RESELLER OTAX</h4>
                            <div class="price">Rp 80.000</div>
                            <div class="price-note">⏳ BATAS PELUNASAN 2 MINGGU / 14 HARI</div>
                            <div class="stock">♾️ <span class="unlimited">Unlimited</span></div>
                            <button class="order-btn" onclick="openPayment('RESELLER OTAX', 80000, 'OTAX')">Order Sekarang</button>
                        </div>
                        <div class="product-card" data-product="PT OTAX" data-price="100000" data-project="OTAX">
                            <div class="product-status-small" id="otax-pt">✅</div>
                            <span class="level-badge pt">PT</span>
                            <h4>PT OTAX</h4>
                            <div class="price">Rp 100.000</div>
                            <div class="price-note">⏳ BATAS PELUNASAN 2 MINGGU / 14 HARI</div>
                            <div class="stock">♾️ <span class="unlimited">Unlimited</span></div>
                            <button class="order-btn" onclick="openPayment('PT OTAX', 100000, 'OTAX')">Order Sekarang</button>
                        </div>
                        <div class="product-card" data-product="TK OTAX" data-price="150000" data-project="OTAX">
                            <div class="product-status-small" id="otax-tk">✅</div>
                            <span class="level-badge tk">TK</span>
                            <h4>TK OTAX</h4>
                            <div class="price">Rp 150.000</div>
                            <div class="price-note">⏳ BATAS PELUNASAN 2 MINGGU / 14 HARI</div>
                            <div class="stock">♾️ <span class="unlimited">Unlimited</span></div>
                            <button class="order-btn" onclick="openPayment('TK OTAX', 150000, 'OTAX')">Order Sekarang</button>
                        </div>
                    </div>
                </div>

                <!-- MANTAX SECTION -->
                <div class="product-section" id="mantaxSection">
                    <button class="back-btn" onclick="backToProject()">⬅ Kembali ke Pilihan Project</button>
                    <h2>📦 Pilih Project MANTAX</h2>
                    <div class="product-grid">
                        <div class="product-card" data-product="MANTAX CUSTOM HARI" data-price="5000" data-project="MANTAX" data-nodp="true">
                            <div class="product-status-small" id="mantax-custom">✅</div>
                            <span class="level-badge custom">⚡ CUSTOM</span>
                            <h4>MANTAX CUSTOM HARI</h4>
                            <div class="price">Rp 5.000 / 1 HARI</div>
                            <div class="price-note">⏳ BATAS PELUNASAN 2 MINGGU / 14 HARI</div>
                            <div class="stock">♾️ <span class="unlimited">Unlimited</span></div>
                            <button class="order-btn custom-btn" onclick="openPayment('MANTAX CUSTOM HARI', 5000, 'MANTAX', true, true)">Order Sekarang</button>
                        </div>
                        <div class="product-card" data-product="MANTAX 1 BULAN" data-price="40000" data-project="MANTAX" data-nodp="true">
                            <div class="product-status-small" id="mantax-bulan">✅</div>
                            <span class="level-badge bulanan">📅 BULANAN</span>
                            <h4>MANTAX 1 BULAN</h4>
                            <div class="price">Rp 40.000</div>
                            <div class="price-note">⏳ BATAS PELUNASAN 2 MINGGU / 14 HARI</div>
                            <div class="stock">♾️ <span class="unlimited">Unlimited</span></div>
                            <button class="order-btn bulanan-btn" onclick="openPayment('MANTAX 1 BULAN', 40000, 'MANTAX', false, true)">Order Sekarang</button>
                        </div>
                        <div class="product-card" data-product="MANTAX FULL UP" data-price="60000" data-project="MANTAX">
                            <div class="product-status-small" id="mantax-fullup">✅</div>
                            <span class="level-badge mantax">FULL UP</span>
                            <h4>MANTAX FULL UP</h4>
                            <div class="price">Rp 60.000</div>
                            <div class="price-note">⏳ BATAS PELUNASAN 2 MINGGU / 14 HARI</div>
                            <div class="stock">♾️ <span class="unlimited">Unlimited</span></div>
                            <button class="order-btn mantax-btn" onclick="openPayment('MANTAX FULL UP', 60000, 'MANTAX')">Order Sekarang</button>
                        </div>
                        <div class="product-card" data-product="MANTAX RESELLER" data-price="80000" data-project="MANTAX">
                            <div class="product-status-small" id="mantax-reseller">✅</div>
                            <span class="level-badge mantax">RESELLER</span>
                            <h4>MANTAX RESELLER</h4>
                            <div class="price">Rp 80.000</div>
                            <div class="price-note">⏳ BATAS PELUNASAN 2 MINGGU / 14 HARI</div>
                            <div class="stock">♾️ <span class="unlimited">Unlimited</span></div>
                            <button class="order-btn mantax-btn" onclick="openPayment('MANTAX RESELLER', 80000, 'MANTAX')">Order Sekarang</button>
                        </div>
                        <div class="product-card" data-product="MANTAX PT" data-price="100000" data-project="MANTAX">
                            <div class="product-status-small" id="mantax-pt">✅</div>
                            <span class="level-badge mantax">PT</span>
                            <h4>MANTAX PT</h4>
                            <div class="price">Rp 100.000</div>
                            <div class="price-note">⏳ BATAS PELUNASAN 2 MINGGU / 14 HARI</div>
                            <div class="stock">♾️ <span class="unlimited">Unlimited</span></div>
                            <button class="order-btn mantax-btn" onclick="openPayment('MANTAX PT', 100000, 'MANTAX')">Order Sekarang</button>
                        </div>
                        <div class="product-card" data-product="MANTAX TK" data-price="150000" data-project="MANTAX">
                            <div class="product-status-small" id="mantax-tk">✅</div>
                            <span class="level-badge mantax">TK</span>
                            <h4>MANTAX TK</h4>
                            <div class="price">Rp 150.000</div>
                            <div class="price-note">⏳ BATAS PELUNASAN 2 MINGGU / 14 HARI</div>
                            <div class="stock">♾️ <span class="unlimited">Unlimited</span></div>
                            <button class="order-btn mantax-btn" onclick="openPayment('MANTAX TK', 150000, 'MANTAX')">Order Sekarang</button>
                        </div>
                    </div>
                </div>

                <!-- FOOTER -->
                <div class="footer">
                    © 2026 KENZ AZA STORE • KENZZ AZA • <a href="#">Support 24/7</a>
                    <br><br />
                    <a href="admin.html" style="font-size: 11px; opacity: 0.3;">⚙️ ADMIN PANEL</a>
                </div>
            </div>
        </div>
    </div>

    <!-- ============================================================
    PAYMENT MODAL
    ============================================================ -->
    <div class="payment-modal" id="paymentModal">
        <div class="modal-box">
            <h2>💳 Pilih Metode Pembayaran</h2>
            <div class="modal-sub">Pilih opsi pembayaran untuk produk di bawah ini:</div>
            <div class="product-info">
                <div class="pname" id="modalProductName">-</div>
                <div class="pprice" id="modalProductPrice">Rp 0</div>
                <div class="pnote" id="modalProductNote">⏳ BATAS PELUNASAN 2 MINGGU / 14 HARI</div>
            </div>
            <div class="payment-options" id="paymentOptions">
                <div class="pay-btn full" id="payFull" onclick="confirmOrder('full')">
                    💰 PELUNASAN
                    <span class="sub highlight">Bayar penuh</span>
                </div>
                <div class="pay-btn dp" id="payDp" onclick="confirmOrder('dp')">
                    📋 DP 50%
                    <span class="sub">Bayar setengah dulu</span>
                </div>
            </div>
            <div class="modal-close" onclick="closePayment()">❌ Batal</div>
        </div>
    </div>

    <!-- ============================================================
    JAVASCRIPT
    ============================================================ -->
    <script>
        // ============================================================
        // SPLASH SCREEN
        // ============================================================
        document.getElementById('enterBtn').addEventListener('click', function(e) {
            // RIPPLE
            const rect = this.getBoundingClientRect();
            const ripple = document.createElement('span');
            ripple.className = 'ripple';
            const size = Math.max(rect.width, rect.height);
            ripple.style.width = ripple.style.height = size + 'px';
            ripple.style.left = (e.clientX - rect.left - size / 2) + 'px';
            ripple.style.top = (e.clientY - rect.top - size / 2) + 'px';
            this.appendChild(ripple);
            setTimeout(() => ripple.remove(), 600);

            document.getElementById('splashScreen').classList.add('hide');
            document.getElementById('mainStore').classList.add('show');
        });

        // ============================================================
        // KONFIGURASI
        // ============================================================
        const WA_NUMBER = '6285111234638';

        let selectedProduct = '';
        let selectedPrice = 0;
        let selectedProject = '';
        let isCustomMantax = false;
        let isNoDp = false;

        // ============================================================
        // DATA STATUS PRODUK
        // ============================================================
        const productStatus = {
            'project_otax': true,
            'project_mantax': true,
            'otax_fullup': true,
            'otax_reseller': true,
            'otax_pt': true,
            'otax_tk': true,
            'mantax_custom': true,
            'mantax_bulan': true,
            'mantax_fullup': true,
            'mantax_reseller': true,
            'mantax_pt': true,
            'mantax_tk': true
        };

        // ============================================================
        // TOAST
        // ============================================================
        function showToast(title, msg) {
            const oldToast = document.querySelector('.toast-notif');
            if (oldToast) oldToast.remove();
            const toast = document.createElement('div');
            toast.className = 'toast-notif';
            toast.innerHTML = `
                <span class="toast-icon">⛔️</span>
                <div class="toast-title">${title}</div>
                <div class="toast-msg">${msg}</div>
            `;
            document.body.appendChild(toast);
            setTimeout(() => { if (toast) toast.remove(); }, 4000);
        }

        // ============================================================
        // UPDATE STATUS UI
        // ============================================================
        function updateStatusUI() {
            const otaxStatus = document.getElementById('statusOtax');
            const mantaxStatus = document.getElementById('statusMantax');
            otaxStatus.textContent = productStatus['project_otax'] ? '✅' : '❌';
            otaxStatus.className = 'project-status ' + (productStatus['project_otax'] ? 'on' : 'off');
            mantaxStatus.textContent = productStatus['project_mantax'] ? '✅' : '❌';
            mantaxStatus.className = 'project-status ' + (productStatus['project_mantax'] ? 'on' : 'off');

            const otaxMap = {
                'otax_fullup': document.getElementById('otax-fullup'),
                'otax_reseller': document.getElementById('otax-reseller'),
                'otax_pt': document.getElementById('otax-pt'),
                'otax_tk': document.getElementById('otax-tk')
            };
            for (const [key, el] of Object.entries(otaxMap)) {
                if (el) {
                    const isOn = productStatus[key] !== false;
                    el.textContent = isOn ? '✅' : '❌';
                    el.className = 'product-status-small ' + (isOn ? 'on' : 'off');
                }
            }
            const mantaxMap = {
                'mantax_custom': document.getElementById('mantax-custom'),
                'mantax_bulan': document.getElementById('mantax-bulan'),
                'mantax_fullup': document.getElementById('mantax-fullup'),
                'mantax_reseller': document.getElementById('mantax-reseller'),
                'mantax_pt': document.getElementById('mantax-pt'),
                'mantax_tk': document.getElementById('mantax-tk')
            };
            for (const [key, el] of Object.entries(mantaxMap)) {
                if (el) {
                    const isOn = productStatus[key] !== false;
                    el.textContent = isOn ? '✅' : '❌';
                    el.className = 'product-status-small ' + (isOn ? 'on' : 'off');
                }
            }
        }

        // ============================================================
        // PROJECT STATE
        // ============================================================
        function getProjectState(project) {
            const key = 'project_' + project;
            const statusKey = project === 'otax' ? 'project_otax' : 'project_mantax';
            const saved = localStorage.getItem(key);
            let state = true;
            if (saved !== null) state = saved === 'true';
            else localStorage.setItem(key, 'true');
            productStatus[statusKey] = state;
            updateStatusUI();
            return state;
        }

        // ============================================================
        // NAVIGASI
        // ============================================================
        function selectProject(type) {
            if (!getProjectState(type)) {
                const name = type === 'otax' ? 'OTAX' : 'MANTAX';
                showToast('⚠️ Project ' + name + ' OFF!', 'BELUM BISA BUY, BOSS!');
                return;
            }
            document.getElementById('projectSelector').classList.add('hidden');
            if (type === 'otax') {
                document.getElementById('otaxSection').classList.add('active');
                document.getElementById('mantaxSection').classList.remove('active');
            } else {
                document.getElementById('mantaxSection').classList.add('active');
                document.getElementById('otaxSection').classList.remove('active');
            }
        }

        function backToProject() {
            document.getElementById('projectSelector').classList.remove('hidden');
            document.getElementById('otaxSection').classList.remove('active');
            document.getElementById('mantaxSection').classList.remove('active');
        }

        // ============================================================
        // PAYMENT
        // ============================================================
        function openPayment(product, price, project, isCustom = false, noDp = false) {
            const projectKey = project.toLowerCase();
            const statusKey = projectKey === 'otax' ? 'project_otax' : 'project_mantax';
            if (productStatus[statusKey] === false) {
                const name = project === 'OTAX' ? 'OTAX' : 'MANTAX';
                showToast('⚠️ Project ' + name + ' OFF!', 'BELUM BISA BUY, BOSS!');
                return;
            }
            selectedProduct = product;
            selectedPrice = price;
            selectedProject = project;
            isCustomMantax = isCustom;
            isNoDp = noDp;
            let priceText = isCustom ? 'Rp 5.000 / 1 HARI' : `Rp ${price.toLocaleString()}`;
            document.getElementById('modalProductName').textContent = product;
            document.getElementById('modalProductPrice').textContent = priceText;
            document.getElementById('modalProductNote').textContent = '⏳ BATAS PELUNASAN 2 MINGGU / 14 HARI';
            const payFull = document.getElementById('payFull');
            const payDp = document.getElementById('payDp');
            if (noDp) { payDp.classList.add('hidden');
                payFull.classList.add('only'); } else { payDp.classList.remove('hidden');
                payFull.classList.remove('only'); }
            document.getElementById('paymentModal').classList.add('show');
        }

        function closePayment() {
            document.getElementById('paymentModal').classList.remove('show');
        }

        function confirmOrder(type) {
            closePayment();
            let priceText = isCustomMantax ? 'Rp 5.000 / 1 HARI' : `Rp ${selectedPrice.toLocaleString()}`;
            let paymentMethod, jumlahBayar;
            if (type === 'full') { paymentMethod = 'PELUNASAN (FULL)';
                jumlahBayar = priceText; } else { paymentMethod = 'DP 50%';
                let dpAmount = isCustomMantax ? 2500 : Math.round(selectedPrice / 2);
                jumlahBayar = `Rp ${dpAmount.toLocaleString()} (50% dari ${priceText})`; }
            const message =
                `Halo KENZ AZA%0A%0AGw mau order:%0A📦 Produk: ${selectedProduct}%0A💰 Harga: ${priceText}%0A💳 Metode: ${paymentMethod}%0A💵 Bayar: ${jumlahBayar}%0A%0A📌 METODE PEMBAYARAN:%0A✅ QRIS%0A%0AThx.`;
            window.open(`https://wa.me/${WA_NUMBER}?text=${message}`, '_blank');
        }

        // ============================================================
        // CLICK PRODUCT
        // ============================================================
        document.querySelectorAll('#otaxSection .product-card, #mantaxSection .product-card').forEach(card => {
            card.addEventListener('click', function(e) {
                if (e.target.tagName === 'BUTTON') return;
                const product = this.dataset.product;
                const price = parseInt(this.dataset.price);
                const project = this.dataset.project;
                const isCustom = product === 'MANTAX CUSTOM HARI';
                const noDp = this.dataset.nodp === 'true';
                openPayment(product, price, project, isCustom, noDp);
            });
        });

        document.querySelectorAll('.order-btn').forEach(btn => {
            btn.addEventListener('click', function(e) {
                e.stopPropagation();
            });
        });

        document.getElementById('paymentModal').addEventListener('click', function(e) {
            if (e.target === this) closePayment();
        });

        // ============================================================
        // LOAD STATUS
        // ============================================================
        function loadAllStatus() {
            const keys = [
                'project_otax', 'project_mantax',
                'otax_fullup', 'otax_reseller', 'otax_pt', 'otax_tk',
                'mantax_custom', 'mantax_bulan', 'mantax_fullup',
                'mantax_reseller', 'mantax_pt', 'mantax_tk'
            ];
            for (const key of keys) {
                const saved = localStorage.getItem(key);
                productStatus[key] = saved !== null ? saved === 'true' : true;
                if (saved === null) localStorage.setItem(key, 'true');
            }
            updateStatusUI();
        }

        // ============================================================
        // ADMIN PANEL
        // ============================================================
        let adminClickCount = 0;
        let adminTimeout = null;
        document.querySelector('.header h1').addEventListener('click', function() {
            adminClickCount++;
            if (adminTimeout) clearTimeout(adminTimeout);
            adminTimeout = setTimeout(() => { adminClickCount = 0; }, 3000);
            if (adminClickCount >= 5) {
                adminClickCount = 0;
                const otaxState = productStatus['project_otax'] !== false;
                productStatus['project_otax'] = !otaxState;
                localStorage.setItem('project_otax', productStatus['project_otax'] ? 'true' : 'false');
                const mantaxState = productStatus['project_mantax'] !== false;
                productStatus['project_mantax'] = !mantaxState;
                localStorage.setItem('project_mantax', productStatus['project_mantax'] ? 'true' : 'false');
                updateStatusUI();
                showToast('🔧 Admin Panel', 'Project OTAX & MANTAX sekarang ' + (productStatus['project_otax'] ?
                    'ON ✅' : 'OFF ❌'));
            }
        });

        // ============================================================
        // INIT
        // ============================================================
        loadAllStatus();
        console.log('%c🔥 KENZ AZA STORE %cLIGHTWEIGHT',
            'background:#ff4444;color:#fff;padding:5px 10px;font-weight:bold;',
            'background:#ff8800;color:#000;padding:5px 10px;font-weight:bold;'
        );
        console.log('%c💡 Klik logo 5x untuk buka Admin Panel', 'color:#8892b0;font-size:12px;');
        console.log('%c⚡ Lightweight & Smooth!', 'color:#00ffc8;font-size:13px;');
    </script>

</body>
</html>
