<!--
=========================================================
YUJINETWORK - TİKTOK JETON İLE SATIN ALMA SİSTEMİ
YouTube: @yujiminicıraft | Sürüm: 1.21.1 | IP: yujismp.mcsh.io
=========================================================
-->
<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>YujiNetwork - TikTok Jeton ile Satın Al</title>
    <!-- Modern Fontlar -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">
    <!-- Font Awesome 6 -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        /* =============================================
        MODERN DEĞİŞKENLER - YUJINETWORK TEMASI
        ============================================= */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --bg-dark: #0a0c0f;
            --bg-card: #14181c;
            --bg-hover: #1c2126;
            --primary: #ff4d4d;
            --primary-light: #ff6b6b;
            --primary-glow: rgba(255, 77, 77, 0.3);
            --secondary: #ffb347;
            --tiktok: #00f2ea;
            --tiktok-dark: #25f4ee;
            --tiktok-pink: #ff0050;
            --tiktok-glow: rgba(0, 242, 234, 0.3);
            --text: #e8eef2;
            --text-muted: #8a939b;
            --border: #2a3138;
            --success: #00d68f;
            --gradient-1: linear-gradient(135deg, #ff4d4d, #ff8080);
            --gradient-2: linear-gradient(135deg, #ffb347, #ffd700);
            --gradient-3: linear-gradient(135deg, #00d68f, #00b8ff);
            --gradient-tiktok: linear-gradient(135deg, #00f2ea, #ff0050);
            --shadow: 0 20px 40px rgba(0, 0, 0, 0.4);
            --shadow-glow: 0 20px 40px rgba(255, 77, 77, 0.3);
        }

        body {
            font-family: 'Inter', sans-serif;
            background: var(--bg-dark);
            color: var(--text);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Modern Arkaplan */
        .background {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -2;
        }

        .background video {
            width: 100%;
            height: 100%;
            object-fit: cover;
            opacity: 0.1;
            filter: blur(5px) brightness(0.3);
        }

        .gradient-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 50% 50%, rgba(255, 77, 77, 0.1) 0%, var(--bg-dark) 70%);
            z-index: -1;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 2rem;
            position: relative;
            z-index: 10;
        }

        /* =============================================
        MODERN HEADER - YUJINETWORK
        ============================================= */
        header {
            position: sticky;
            top: 0;
            z-index: 1000;
            background: rgba(10, 12, 15, 0.8);
            backdrop-filter: blur(20px);
            border-bottom: 1px solid rgba(255, 77, 77, 0.2);
        }

        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            height: 80px;
        }

        .logo {
            font-size: 2rem;
            font-weight: 800;
            background: var(--gradient-1);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            letter-spacing: -0.5px;
            position: relative;
        }

        .logo span {
            font-size: 0.8rem;
            background: var(--primary);
            color: white;
            padding: 0.2rem 0.5rem;
            border-radius: 20px;
            margin-left: 0.5rem;
            font-weight: 600;
        }

        .nav-menu {
            display: flex;
            gap: 2.5rem;
            list-style: none;
        }

        .nav-menu a {
            color: var(--text);
            text-decoration: none;
            font-weight: 500;
            font-size: 1rem;
            transition: color 0.3s;
            position: relative;
            padding: 0.5rem 0;
        }

        .nav-menu a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--gradient-1);
            transition: width 0.3s;
        }

        .nav-menu a:hover::after,
        .nav-menu a.active::after {
            width: 100%;
        }

        .nav-menu a:hover,
        .nav-menu a.active {
            color: var(--primary);
        }

        .nav-social {
            display: flex;
            gap: 1rem;
        }

        .nav-social a {
            width: 40px;
            height: 40px;
            background: var(--bg-card);
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--text);
            transition: all 0.3s;
            border: 1px solid var(--border);
        }

        .nav-social a:hover {
            background: var(--primary);
            color: white;
            transform: translateY(-3px);
            border-color: transparent;
            box-shadow: 0 10px 20px var(--primary-glow);
        }

        /* =============================================
        HERO BÖLÜMÜ - YUJINETWORK
        ============================================= */
        .hero {
            min-height: 90vh;
            display: flex;
            align-items: center;
            position: relative;
            overflow: hidden;
        }

        .hero-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('https://i.imgur.com/2Uqx8cK.jpg') center/cover;
            filter: brightness(0.2) blur(2px);
            z-index: -1;
            animation: slowZoom 20s infinite alternate;
        }

        @keyframes slowZoom {
            from { transform: scale(1); }
            to { transform: scale(1.1); }
        }

        .hero-content {
            max-width: 800px;
        }

        .hero-title {
            font-size: 5rem;
            font-weight: 800;
            line-height: 1.1;
            margin-bottom: 1.5rem;
            letter-spacing: -2px;
        }

        .hero-title span {
            background: var(--gradient-1);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            position: relative;
            display: inline-block;
        }

        .hero-title span::after {
            content: '⚔️';
            position: absolute;
            top: -10px;
            right: -30px;
            font-size: 2rem;
            transform: rotate(15deg);
        }

        .hero-subtitle {
            font-size: 1.2rem;
            color: var(--text-muted);
            margin-bottom: 2.5rem;
            max-width: 600px;
        }

        /* YouTube Kanal Butonu - ÖZEL */
        .youtube-channel {
            display: flex;
            align-items: center;
            gap: 1rem;
            background: rgba(255, 0, 0, 0.1);
            border: 1px solid rgba(255, 0, 0, 0.3);
            border-radius: 50px;
            padding: 0.5rem 1.5rem 0.5rem 0.5rem;
            margin-bottom: 2rem;
            width: fit-content;
        }

        .channel-icon {
            width: 50px;
            height: 50px;
            background: #ff0000;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.8rem;
            color: white;
        }

        .channel-info {
            display: flex;
            flex-direction: column;
        }

        .channel-name {
            font-size: 1.2rem;
            font-weight: 700;
            color: white;
        }

        .channel-handle {
            color: #ff0000;
            font-size: 0.9rem;
        }

        .subscribe-btn {
            background: #ff0000;
            color: white;
            border: none;
            padding: 0.5rem 1.2rem;
            border-radius: 50px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            margin-left: 1rem;
        }

        .subscribe-btn:hover {
            background: #cc0000;
            transform: scale(1.05);
        }

        /* Modern IP Kutusu */
        .server-ip-card {
            background: rgba(20, 24, 28, 0.7);
            backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 77, 77, 0.3);
            border-radius: 20px;
            padding: 1.5rem 2rem;
            display: inline-flex;
            align-items: center;
            gap: 2rem;
            margin-bottom: 2rem;
            box-shadow: var(--shadow);
        }

        .ip-info {
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .ip-label {
            color: var(--text-muted);
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .ip-address {
            font-size: 2rem;
            font-weight: 700;
            color: var(--primary);
            letter-spacing: 1px;
        }

        .version-badge {
            background: var(--gradient-1);
            color: white;
            padding: 0.4rem 1rem;
            border-radius: 50px;
            font-size: 0.9rem;
            font-weight: 600;
        }

        .copy-btn {
            background: transparent;
            border: 2px solid var(--primary);
            color: var(--primary);
            padding: 0.8rem 2rem;
            border-radius: 12px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .copy-btn:hover {
            background: var(--primary);
            color: white;
            box-shadow: 0 10px 20px var(--primary-glow);
        }

        /* =============================================
        YOUTUBE VİDEOLARI - @yujiminicıraft
        ============================================= */
        .videos-section {
            padding: 6rem 0;
        }

        .section-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 3rem;
            flex-wrap: wrap;
            gap: 1rem;
        }

        .section-title {
            font-size: 2.5rem;
            font-weight: 700;
            letter-spacing: -1px;
        }

        .section-title span {
            background: var(--gradient-1);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }

        .channel-stats {
            display: flex;
            gap: 2rem;
            background: var(--bg-card);
            padding: 1rem 2rem;
            border-radius: 50px;
            border: 1px solid var(--border);
        }

        .stat {
            text-align: center;
        }

        .stat-number {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary);
        }

        .stat-label {
            color: var(--text-muted);
            font-size: 0.9rem;
        }

        .videos-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 2rem;
        }

        .video-card {
            background: var(--bg-card);
            border-radius: 20px;
            overflow: hidden;
            border: 1px solid var(--border);
            transition: all 0.3s;
            cursor: pointer;
        }

        .video-card:hover {
            transform: translateY(-10px);
            border-color: var(--primary);
            box-shadow: 0 20px 40px var(--primary-glow);
        }

        .video-thumbnail {
            position: relative;
            aspect-ratio: 16/9;
            overflow: hidden;
        }

        .video-thumbnail img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }

        .video-card:hover .video-thumbnail img {
            transform: scale(1.1);
        }

        .video-duration {
            position: absolute;
            bottom: 10px;
            right: 10px;
            background: rgba(0, 0, 0, 0.8);
            padding: 0.3rem 0.6rem;
            border-radius: 6px;
            font-size: 0.8rem;
            font-weight: 600;
        }

        .video-info {
            padding: 1.5rem;
        }

        .video-title {
            font-size: 1.1rem;
            font-weight: 600;
            margin-bottom: 0.5rem;
            line-height: 1.4;
        }

        .video-meta {
            display: flex;
            justify-content: space-between;
            color: var(--text-muted);
            font-size: 0.9rem;
        }

        .video-views i {
            margin-right: 0.3rem;
            color: var(--primary);
        }

        /* =============================================
        TİKTOK JETON İLE SATIN ALMA BÖLÜMÜ
        ============================================= */
        .shop-section {
            padding: 6rem 0;
            background: linear-gradient(180deg, var(--bg-card), var(--bg-dark));
            position: relative;
            overflow: hidden;
        }

        .shop-section::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(0, 242, 234, 0.05) 0%, transparent 70%);
            animation: rotate 30s linear infinite reverse;
        }

        .shop-header {
            text-align: center;
            margin-bottom: 3rem;
            position: relative;
            z-index: 2;
        }

        .shop-header h2 {
            font-size: 3.5rem;
            font-weight: 800;
            margin-bottom: 1rem;
            letter-spacing: -1px;
        }

        .shop-header h2 span {
            background: var(--gradient-tiktok);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }

        .shop-header p {
            color: var(--text-muted);
            font-size: 1.2rem;
            max-width: 600px;
            margin: 0 auto;
        }

        .tiktok-balance {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 1rem;
            margin: 2rem auto;
            background: rgba(0, 242, 234, 0.1);
            border: 1px solid var(--tiktok);
            border-radius: 50px;
            padding: 1rem 2rem;
            width: fit-content;
        }

        .tiktok-icon {
            font-size: 2rem;
            color: var(--tiktok);
        }

        .balance-text {
            font-size: 1.2rem;
            color: var(--text-muted);
        }

        .balance-amount {
            font-size: 2rem;
            font-weight: 800;
            background: var(--gradient-tiktok);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }

        .add-balance {
            margin-left: 1rem;
            padding: 0.5rem 1.5rem;
            background: var(--gradient-tiktok);
            border: none;
            border-radius: 50px;
            color: white;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
        }

        .add-balance:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 30px var(--tiktok-glow);
        }

        .shop-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 2rem;
            position: relative;
            z-index: 2;
            margin-bottom: 3rem;
        }

        .shop-card {
            background: var(--bg-card);
            border: 1px solid var(--border);
            border-radius: 30px;
            padding: 2rem;
            transition: all 0.4s;
            position: relative;
            overflow: hidden;
        }

        .shop-card:hover {
            transform: translateY(-15px);
            border-color: var(--tiktok);
            box-shadow: 0 30px 60px var(--tiktok-glow);
        }

        .shop-card.tiktok-card {
            border: 2px solid var(--tiktok);
            background: linear-gradient(145deg, var(--bg-card), rgba(0, 242, 234, 0.05));
        }

        .shop-badge {
            position: absolute;
            top: 1rem;
            right: 1rem;
            background: var(--gradient-tiktok);
            color: white;
            padding: 0.3rem 1rem;
            border-radius: 50px;
            font-size: 0.8rem;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 0.3rem;
        }

        .shop-badge i {
            font-size: 1rem;
        }

        .shop-icon {
            font-size: 3rem;
            margin-bottom: 1.5rem;
        }

        .shop-title {
            font-size: 2rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
        }

        .shop-description {
            color: var(--text-muted);
            margin-bottom: 1.5rem;
            font-size: 0.95rem;
        }

        .shop-price {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            margin-bottom: 1.5rem;
        }

        .price-amount {
            font-size: 2.5rem;
            font-weight: 800;
            color: var(--tiktok);
        }

        .price-amount span {
            font-size: 1rem;
            color: var(--text-muted);
        }

        .price-icon {
            font-size: 2rem;
            color: var(--tiktok);
        }

        .shop-features {
            list-style: none;
            margin-bottom: 2rem;
        }

        .shop-features li {
            margin-bottom: 0.8rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            color: var(--text-muted);
            font-size: 0.95rem;
        }

        .shop-features i {
            color: var(--tiktok);
        }

        .buy-tiktok-btn {
            width: 100%;
            padding: 1.2rem;
            background: var(--gradient-tiktok);
            border: none;
            border-radius: 15px;
            color: white;
            font-weight: 700;
            font-size: 1.1rem;
            cursor: pointer;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.8rem;
        }

        .buy-tiktok-btn:hover {
            transform: scale(1.02);
            box-shadow: 0 10px 30px var(--tiktok-glow);
        }

        .buy-tiktok-btn:disabled {
            opacity: 0.5;
            cursor: not-allowed;
            transform: none;
        }

        /* =============================================
        SON SATIN ALIMLAR BÖLÜMÜ - YENİ!
        ============================================= */
        .recent-purchases {
            margin-top: 4rem;
            background: rgba(0, 0, 0, 0.3);
            border-radius: 30px;
            padding: 2rem;
            border: 1px solid var(--tiktok);
        }

        .recent-header {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin-bottom: 2rem;
        }

        .recent-header h3 {
            font-size: 2rem;
            font-weight: 700;
            color: var(--tiktok);
        }

        .recent-header i {
            font-size: 2rem;
            color: var(--tiktok);
        }

        .purchases-list {
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }

        .purchase-item {
            display: flex;
            align-items: center;
            gap: 1rem;
            padding: 1rem;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 15px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.3s;
            animation: slideIn 0.5s ease;
        }

        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .purchase-item:hover {
            background: rgba(0, 242, 234, 0.1);
            border-color: var(--tiktok);
        }

        .purchase-rank {
            width: 60px;
            height: 60px;
            background: var(--gradient-tiktok);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            font-weight: 700;
            color: white;
        }

        .purchase-info {
            flex: 1;
        }

        .purchase-player {
            font-size: 1.2rem;
            font-weight: 700;
            margin-bottom: 0.3rem;
        }

        .purchase-details {
            display: flex;
            gap: 1rem;
            color: var(--text-muted);
            font-size: 0.9rem;
        }

        .purchase-rank-name {
            color: var(--tiktok);
            font-weight: 600;
        }

        .purchase-time {
            display: flex;
            align-items: center;
            gap: 0.3rem;
        }

        .purchase-time i {
            font-size: 0.8rem;
        }

        .purchase-badge {
            background: var(--gradient-tiktok);
            color: white;
            padding: 0.3rem 1rem;
            border-radius: 50px;
            font-size: 0.8rem;
            font-weight: 600;
        }

        /* =============================================
        MODERN KAYIT SİSTEMİ
        ============================================= */
        .register-section {
            padding: 6rem 0;
            background: linear-gradient(180deg, var(--bg-dark), var(--bg-card));
            position: relative;
            overflow: hidden;
        }

        .register-section::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255, 77, 77, 0.1) 0%, transparent 70%);
            animation: rotate 30s linear infinite;
        }

        .register-header {
            text-align: center;
            margin-bottom: 4rem;
            position: relative;
            z-index: 2;
        }

        .register-header h2 {
            font-size: 3.5rem;
            font-weight: 800;
            margin-bottom: 1rem;
            letter-spacing: -1px;
        }

        .register-header h2 span {
            background: var(--gradient-1);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }

        .register-header p {
            color: var(--text-muted);
            font-size: 1.2rem;
            max-width: 600px;
            margin: 0 auto;
        }

        .register-options {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 2rem;
            margin-bottom: 4rem;
            position: relative;
            z-index: 2;
        }

        .register-card {
            background: var(--bg-card);
            border: 1px solid var(--border);
            border-radius: 30px;
            padding: 2.5rem 2rem;
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
            cursor: pointer;
        }

        .register-card:hover {
            transform: translateY(-15px);
            border-color: var(--primary);
            box-shadow: 0 30px 60px var(--primary-glow);
        }

        .register-card.active {
            border-color: var(--primary);
            box-shadow: 0 0 0 2px var(--primary), 0 30px 60px var(--primary-glow);
        }

        .card-icon {
            font-size: 3rem;
            margin-bottom: 1.5rem;
        }

        .card-title {
            font-size: 2rem;
            font-weight: 700;
            margin-bottom: 1rem;
        }

        .card-description {
            color: var(--text-muted);
            margin-bottom: 2rem;
            font-size: 0.95rem;
        }

        .card-features {
            list-style: none;
            margin-bottom: 2rem;
        }

        .card-features li {
            margin-bottom: 0.8rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            color: var(--text-muted);
            font-size: 0.9rem;
        }

        .card-features i {
            color: var(--primary);
        }

        .card-badge {
            position: absolute;
            top: 1rem;
            right: 1rem;
            background: var(--gradient-1);
            color: white;
            padding: 0.3rem 1rem;
            border-radius: 50px;
            font-size: 0.8rem;
            font-weight: 600;
        }

        .main-register-form {
            background: var(--bg-card);
            border: 1px solid var(--border);
            border-radius: 30px;
            padding: 3rem;
            max-width: 600px;
            margin: 0 auto;
            position: relative;
            z-index: 2;
            backdrop-filter: blur(10px);
        }

        .form-title {
            text-align: center;
            font-size: 2rem;
            font-weight: 700;
            margin-bottom: 2rem;
        }

        .form-title i {
            color: var(--primary);
            margin-right: 0.5rem;
        }

        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1rem;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: var(--text-muted);
            font-size: 0.9rem;
            font-weight: 500;
        }

        .form-group label i {
            color: var(--primary);
            margin-right: 0.3rem;
        }

        .input-wrapper {
            position: relative;
        }

        .input-wrapper i {
            position: absolute;
            left: 1rem;
            top: 50%;
            transform: translateY(-50%);
            color: var(--text-muted);
            font-size: 1rem;
        }

        .form-control {
            width: 100%;
            padding: 1rem 1rem 1rem 2.5rem;
            background: var(--bg-dark);
            border: 2px solid var(--border);
            border-radius: 12px;
            color: var(--text);
            font-size: 1rem;
            transition: all 0.3s;
        }

        .form-control:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 4px var(--primary-glow);
        }

        .password-strength {
            margin-top: 0.5rem;
            height: 4px;
            background: var(--border);
            border-radius: 2px;
            overflow: hidden;
        }

        .strength-bar {
            height: 100%;
            width: 0;
            background: var(--gradient-1);
            transition: width 0.3s;
        }

        .checkbox-group {
            display: flex;
            align-items: center;
            gap: 0.8rem;
            margin: 1.5rem 0;
        }

        .checkbox-group input {
            width: 20px;
            height: 20px;
            accent-color: var(--primary);
        }

        .checkbox-group label {
            color: var(--text-muted);
            font-size: 0.95rem;
        }

        .checkbox-group a {
            color: var(--primary);
            text-decoration: none;
        }

        .register-submit-btn {
            width: 100%;
            padding: 1.2rem;
            background: var(--gradient-1);
            border: none;
            border-radius: 12px;
            color: white;
            font-weight: 700;
            font-size: 1.2rem;
            cursor: pointer;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 1rem;
        }

        .register-submit-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 20px 40px var(--primary-glow);
        }

        .login-link {
            text-align: center;
            margin-top: 1.5rem;
            color: var(--text-muted);
        }

        .login-link a {
            color: var(--primary);
            text-decoration: none;
            font-weight: 600;
        }

        /* =============================================
        OYUN MODLARI
        ============================================= */
        .modes-section {
            padding: 6rem 0;
        }

        .online-total {
            background: rgba(255, 77, 77, 0.1);
            padding: 0.8rem 1.5rem;
            border-radius: 50px;
            border: 1px solid rgba(255, 77, 77, 0.3);
            display: flex;
            align-items: center;
            gap: 0.8rem;
        }

        .total-online {
            font-size: 1.8rem;
            font-weight: 800;
            color: var(--primary);
        }

        .total-label {
            color: var(--text-muted);
            font-size: 0.9rem;
        }

        .modes-grid-modern {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 2rem;
        }

        .mode-card-modern {
            background: var(--bg-card);
            border: 1px solid var(--border);
            border-radius: 30px;
            padding: 2rem;
            transition: all 0.4s;
            position: relative;
            overflow: hidden;
        }

        .mode-card-modern:hover {
            transform: translateY(-15px);
            border-color: var(--primary);
            box-shadow: 0 30px 60px var(--primary-glow);
        }

        .mode-card-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1.5rem;
        }

        .mode-icon {
            font-size: 3rem;
        }

        .mode-badge {
            padding: 0.4rem 1rem;
            border-radius: 50px;
            font-size: 0.8rem;
            font-weight: 700;
            text-transform: uppercase;
        }

        .mode-badge.populer {
            background: linear-gradient(135deg, #ff4d4d, #ff8080);
            color: white;
        }

        .mode-badge.yeni {
            background: linear-gradient(135deg, #4da6ff, #80bfff);
            color: white;
        }

        .mode-title {
            font-size: 2.2rem;
            font-weight: 700;
            margin-bottom: 1rem;
        }

        .mode-description {
            color: var(--text-muted);
            margin-bottom: 2rem;
        }

        .live-counter {
            background: rgba(0, 0, 0, 0.3);
            border-radius: 20px;
            padding: 1.5rem;
            margin-bottom: 2rem;
            border: 1px solid rgba(255, 77, 77, 0.2);
            position: relative;
            overflow: hidden;
        }

        .live-counter::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 77, 77, 0.1), transparent);
            animation: shine 2s infinite;
        }

        @keyframes shine {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }

        .counter-header {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            margin-bottom: 0.8rem;
        }

        .live-dot {
            width: 10px;
            height: 10px;
            background: #ff4d4d;
            border-radius: 50%;
            animation: pulseLive 1.5s infinite;
        }

        @keyframes pulseLive {
            0%, 100% { opacity: 1; transform: scale(1); }
            50% { opacity: 0.5; transform: scale(1.3); }
        }

        .counter-number {
            font-size: 3.5rem;
            font-weight: 800;
            color: var(--primary);
            line-height: 1;
            margin-bottom: 0.3rem;
        }

        .mode-features {
            display: flex;
            gap: 1rem;
            margin-bottom: 2rem;
            flex-wrap: wrap;
        }

        .mode-feature {
            background: rgba(255, 255, 255, 0.05);
            padding: 0.5rem 1rem;
            border-radius: 50px;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            font-size: 0.9rem;
            color: var(--text-muted);
        }

        .mode-feature i {
            color: var(--primary);
        }

        .join-btn {
            width: 100%;
            padding: 1.2rem;
            background: transparent;
            border: 2px solid var(--primary);
            border-radius: 15px;
            color: var(--primary);
            font-weight: 700;
            font-size: 1.1rem;
            cursor: pointer;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.8rem;
        }

        .join-btn:hover {
            background: var(--primary);
            color: var(--bg-dark);
            transform: scale(1.02);
            box-shadow: 0 10px 30px var(--primary-glow);
        }

        /* =============================================
        İSTATİSTİKLER
        ============================================= */
        .stats-section {
            padding: 4rem 0;
            background: var(--bg-card);
            border-radius: 30px;
            margin: 4rem 0;
        }

        .stats-grid-modern {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 2rem;
            text-align: center;
        }

        .stat-item-modern {
            padding: 2rem;
        }

        .stat-value {
            font-size: 3rem;
            font-weight: 800;
            background: var(--gradient-1);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            margin-bottom: 0.5rem;
        }

        .stat-label-modern {
            color: var(--text-muted);
            font-size: 1rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        /* =============================================
        FOOTER
        ============================================= */
        footer {
            background: var(--bg-card);
            border-top: 1px solid var(--border);
            padding: 4rem 0 2rem;
            margin-top: 4rem;
        }

        .footer-grid {
            display: grid;
            grid-template-columns: 2fr 1fr 1fr 1.5fr;
            gap: 4rem;
            margin-bottom: 4rem;
        }

        .footer-logo {
            font-size: 2rem;
            font-weight: 800;
            background: var(--gradient-1);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            margin-bottom: 1rem;
        }

        .footer-text {
            color: var(--text-muted);
            line-height: 1.6;
        }

        .footer-title {
            font-size: 1.2rem;
            font-weight: 700;
            margin-bottom: 1.5rem;
        }

        .footer-links {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 0.8rem;
        }

        .footer-links a {
            color: var(--text-muted);
            text-decoration: none;
            transition: color 0.3s;
        }

        .footer-links a:hover {
            color: var(--primary);
        }

        .social-grid {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
        }

        .social-grid a {
            width: 45px;
            height: 45px;
            background: var(--bg-dark);
            border: 1px solid var(--border);
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--text);
            transition: all 0.3s;
        }

        .social-grid a:hover {
            background: var(--primary);
            color: white;
            transform: translateY(-3px);
        }

        .copyright {
            text-align: center;
            padding-top: 2rem;
            border-top: 1px solid var(--border);
            color: var(--text-muted);
        }

        /* Responsive */
        @media (max-width: 1200px) {
            .hero-title { font-size: 4rem; }
            .videos-grid,
            .shop-grid,
            .modes-grid-modern,
            .register-options { grid-template-columns: repeat(2, 1fr); }
            .stats-grid-modern { grid-template-columns: repeat(2, 1fr); }
            .footer-grid { grid-template-columns: repeat(2, 1fr); }
        }

        @media (max-width: 768px) {
            .navbar {
                flex-direction: column;
                height: auto;
                padding: 1rem 0;
            }
            .nav-menu {
                flex-direction: column;
                text-align: center;
                gap: 1rem;
                margin: 1rem 0;
            }
            .hero-title { font-size: 3rem; }
            .server-ip-card {
                flex-direction: column;
                text-align: center;
            }
            .ip-info { flex-direction: column; }
            .videos-grid,
            .shop-grid,
            .modes-grid-modern,
            .register-options,
            .stats-grid-modern { grid-template-columns: 1fr; }
            .form-row { grid-template-columns: 1fr; }
            .footer-grid { grid-template-columns: 1fr; }
            .tiktok-balance {
                flex-direction: column;
                text-align: center;
            }
            .recent-header {
                flex-direction: column;
                text-align: center;
            }
        }
    </style>
</head>
<body>
    <!-- Arkaplan -->
    <div class="background">
        <video autoplay loop muted playsinline>
            <source src="https://videos.pexels.com/video-files/30357295/1300530065_1440_2560_60fps.mp4" type="video/mp4">
        </video>
    </div>
    <div class="gradient-overlay"></div>

    <!-- HEADER -->
    <header>
        <div class="container">
            <nav class="navbar">
                <div class="logo">YujiNetwork <span>MC</span></div>
                <ul class="nav-menu">
                    <li><a href="#" class="active">Ana Sayfa</a></li>
                    <li><a href="#videolar">Videolar</a></li>
                    <li><a href="#modlar">Modlar</a></li>
                    <li><a href="#magaza">Mağaza</a></li>
                    <li><a href="#kayit">Kayıt</a></li>
                </ul>
                <div class="nav-social">
                    <a href="https://youtube.com/@yujiminicıraft" target="_blank"><i class="fab fa-youtube"></i></a>
                    <a href="#"><i class="fab fa-tiktok"></i></a>
                    <a href="#"><i class="fab fa-discord"></i></a>
                    <a href="#"><i class="fab fa-instagram"></i></a>
                </div>
            </nav>
        </div>
    </header>

    <!-- HERO BÖLÜMÜ -->
    <section class="hero">
        <div class="hero-bg"></div>
        <div class="container">
            <div class="hero-content">
                <h1 class="hero-title">
                    <span>YujiNetwork</span><br>
                    Minecraft Sunucusu
                </h1>
                <p class="hero-subtitle">Bedwars, Skywars ve daha fazlası! TikTok jeton ile özel rankler satın al, ayrıcalıkları yaşa!</p>
                
                <!-- YouTube Kanalı -->
                <div class="youtube-channel">
                    <div class="channel-icon">
                        <i class="fab fa-youtube"></i>
                    </div>
                    <div class="channel-info">
                        <span class="channel-name">yujiminicıraft</span>
                        <span class="channel-handle">@yujiminicıraft</span>
                    </div>
                    <button class="subscribe-btn" onclick="window.open('https://youtube.com/@yujiminicıraft', '_blank')">
                        <i class="fab fa-youtube"></i> ABONE OL
                    </button>
                </div>
                
                <!-- IP Kutusu -->
                <div class="server-ip-card">
                    <div class="ip-info">
                        <span class="ip-label">SUNUCU IP</span>
                        <span class="ip-address">yujismp.mcsh.io</span>
                        <span class="version-badge">1.21.1</span>
                    </div>
                    <button class="copy-btn" onclick="copyIP()">
                        <i class="far fa-copy"></i> KOPYALA
                    </button>
                </div>
            </div>
        </div>
    </section>

    <!-- YOUTUBE VİDEOLARI -->
    <section id="videolar" class="videos-section">
        <div class="container">
            <div class="section-header">
                <h2 class="section-title">SON <span>VİDEOLAR</span></h2>
                <div class="channel-stats">
                    <div class="stat">
                        <div class="stat-number">18</div>
                        <div class="stat-label">Abone</div>
                    </div>
                    <div class="stat">
                        <div class="stat-number">14</div>
                        <div class="stat-label">Video</div>
                    </div>
                    <div class="stat">
                        <div class="stat-number">320</div>
                        <div class="stat-label">Görüntülenme</div>
                    </div>
                </div>
            </div>

            <div class="videos-grid">
                <!-- Video 1 -->
                <div class="video-card" onclick="watchVideo('bedwars edit')">
                    <div class="video-thumbnail">
                        <img src="https://img.youtube.com/vi/1/maxresdefault.jpg" alt="Bedwars Edit">
                        <span class="video-duration">3:10</span>
                    </div>
                    <div class="video-info">
                        <h3 class="video-title">bedwars edit</h3>
                        <div class="video-meta">
                            <span class="video-views"><i class="fas fa-eye"></i> 11</span>
                            <span class="video-date">2 gün önce</span>
                        </div>
                    </div>
                </div>

                <!-- Video 2 -->
                <div class="video-card" onclick="watchVideo('hile ile bedwars')">
                    <div class="video-thumbnail">
                        <img src="https://img.youtube.com/vi/2/maxresdefault.jpg" alt="Hile ile Bedwars">
                        <span class="video-duration">16:13</span>
                    </div>
                    <div class="video-info">
                        <h3 class="video-title">hile ile bedwars</h3>
                        <div class="video-meta">
                            <span class="video-views"><i class="fas fa-eye"></i> 14</span>
                            <span class="video-date">2 gün önce</span>
                        </div>
                    </div>
                </div>

                <!-- Video 3 -->
                <div class="video-card" onclick="watchVideo('bedwars hileli')">
                    <div class="video-thumbnail">
                        <img src="https://img.youtube.com/vi/3/maxresdefault.jpg" alt="Bedwars Hileli">
                        <span class="video-duration">14:05</span>
                    </div>
                    <div class="video-info">
                        <h3 class="video-title">bedwars hileli</h3>
                        <div class="video-meta">
                            <span class="video-views"><i class="fas fa-eye"></i> 43</span>
                            <span class="video-date">2 hafta önce</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- TİKTOK JETON İLE SATIN ALMA BÖLÜMÜ -->
    <section id="magaza" class="shop-section">
        <div class="container">
            <div class="shop-header">
                <h2>TİKTOK JETON <span>MAĞAZASI</span></h2>
                <p>TikTok jetonlarınla özel rankler ve ayrıcalıklar satın al!</p>
                
                <!-- TikTok Bakiye Göstergesi -->
                <div class="tiktok-balance" id="tiktokBalance">
                    <i class="fab fa-tiktok tiktok-icon"></i>
                    <span class="balance-text">Jetony:</span>
                    <span class="balance-amount" id="tokenBalance">0</span>
                    <button class="add-balance" onclick="addTokens()">
                        <i class="fas fa-plus"></i> Jeton Ekle
                    </button>
                </div>
            </div>

            <!-- Satın Alma Kartları -->
            <div class="shop-grid">
                <!-- VIP Rank -->
                <div class="shop-card tiktok-card">
                    <div class="shop-badge">
                        <i class="fab fa-tiktok"></i> POPÜLER
                    </div>
                    <div class="shop-icon">⚡</div>
                    <h3 class="shop-title">VIP Rank</h3>
                    <p class="shop-description">Temel ayrıcalıklar ve özel eşyalar</p>
                    <div class="shop-price">
                        <span class="price-amount">250 <span>jeton</span></span>
                        <i class="fab fa-tiktok price-icon"></i>
                    </div>
                    <ul class="shop-features">
                        <li><i class="fas fa-check"></i> Özel chat rengi</li>
                        <li><i class="fas fa-check"></i> /fly komutu</li>
                        <li><i class="fas fa-check"></i> 2x daha fazla loot</li>
                        <li><i class="fas fa-check"></i> Özel spawn bölgesi</li>
                    </ul>
                    <button class="buy-tiktok-btn" onclick="buyItem('VIP', 250)" id="buyVIP">
                        <i class="fab fa-tiktok"></i> SATIN AL
                    </button>
                </div>

                <!-- ELITE Rank -->
                <div class="shop-card tiktok-card">
                    <div class="shop-badge">
                        <i class="fab fa-tiktok"></i> ÖNERİLEN
                    </div>
                    <div class="shop-icon">💎</div>
                    <h3 class="shop-title">ELITE Rank</h3>
                    <p class="shop-description">Profesyonel oyuncular için özel paket</p>
                    <div class="shop-price">
                        <span class="price-amount">500 <span>jeton</span></span>
                        <i class="fab fa-tiktok price-icon"></i>
                    </div>
                    <ul class="shop-features">
                        <li><i class="fas fa-check"></i> Tüm VIP özellikleri</li>
                        <li><i class="fas fa-check"></i> Özel eşya kutuları</li>
                        <li><i class="fas fa-check"></i> 3x daha fazla loot</li>
                        <li><i class="fas fa-check"></i> Özel nick rengi</li>
                        <li><i class="fas fa-check"></i> Haftalık ödüller</li>
                    </ul>
                    <button class="buy-tiktok-btn" onclick="buyItem('ELITE', 500)" id="buyELITE">
                        <i class="fab fa-tiktok"></i> SATIN AL
                    </button>
                </div>

                <!-- LEGEND Rank -->
                <div class="shop-card tiktok-card">
                    <div class="shop-badge">
                        <i class="fab fa-tiktok"></i> PREMIUM
                    </div>
                    <div class="shop-icon">👑</div>
                    <h3 class="shop-title">LEGEND Rank</h3>
                    <p class="shop-description">En yüksek ayrıcalıklar ve özel avantajlar</p>
                    <div class="shop-price">
                        <span class="price-amount">1000 <span>jeton</span></span>
                        <i class="fab fa-tiktok price-icon"></i>
                    </div>
                    <ul class="shop-features">
                        <li><i class="fas fa-check"></i> Tüm ELITE özellikleri</li>
                        <li><i class="fas fa-check"></i> Özel prefix [LEGEND]</li>
                        <li><i class="fas fa-check"></i> 5x daha fazla loot</li>
                        <li><i class="fas fa-check"></i> Özel boss alanı</li>
                        <li><i class="fas fa-check"></i> Aylık özel etkinlik</li>
                    </ul>
                    <button class="buy-tiktok-btn" onclick="buyItem('LEGEND', 1000)" id="buyLEGEND">
                        <i class="fab fa-tiktok"></i> SATIN AL
                    </button>
                </div>
            </div>

            <!-- SON SATIN ALIMLAR BÖLÜMÜ -->
            <div class="recent-purchases">
                <div class="recent-header">
                    <i class="fab fa-tiktok"></i>
                    <h3>SON SATIN ALIMLAR</h3>
                    <i class="fas fa-shopping-cart"></i>
                </div>
                <div class="purchases-list" id="purchasesList">
                    <!-- JavaScript ile doldurulacak -->
                </div>
            </div>
        </div>
    </section>

    <!-- KAYIT BÖLÜMÜ -->
    <section id="kayit" class="register-section">
        <div class="container">
            <div class="register-header">
                <h2>YUJINETWORK'A <span>KAYIT OL</span></h2>
                <p>Sunucuya katıl, Bedwars ve Skywars'ta arkadaşlarınla savaş!</p>
            </div>

            <!-- 3 Farklı Kayıt Seçeneği -->
            <div class="register-options">
                <div class="register-card" onclick="selectCard(1)" id="card1">
                    <div class="card-icon">⚡</div>
                    <h3 class="card-title">Hızlı Kayıt</h3>
                    <p class="card-description">Sadece kullanıcı adı ve e-posta ile hemen kaydol.</p>
                    <ul class="card-features">
                        <li><i class="fas fa-check"></i> 30 saniyede kayıt</li>
                        <li><i class="fas fa-check"></i> E-posta onayı yok</li>
                        <li><i class="fas fa-check"></i> Hemen oyuna başla</li>
                    </ul>
                    <div class="card-badge">POPÜLER</div>
                </div>

                <div class="register-card active" onclick="selectCard(2)" id="card2">
                    <div class="card-icon">🔒</div>
                    <h3 class="card-title">Tam Kayıt</h3>
                    <p class="card-description">Tüm özelliklere erişim için güvenli kayıt.</p>
                    <ul class="card-features">
                        <li><i class="fas fa-check"></i> Şifreli hesap</li>
                        <li><i class="fas fa-check"></i> Tüm modlara erişim</li>
                        <li><i class="fas fa-check"></i> Özel etkinlikler</li>
                    </ul>
                    <div class="card-badge">ÖNERİLEN</div>
                </div>

                <div class="register-card" onclick="selectCard(3)" id="card3">
                    <div class="card-icon">🎮</div>
                    <h3 class="card-title">Minecraft ile</h3>
                    <p class="card-description">Minecraft hesabınla direkt bağlan.</p>
                    <ul class="card-features">
                        <li><i class="fas fa-check"></i> Premium hesap gerekli</li>
                        <li><i class="fas fa-check"></i> Otomatik tanıma</li>
                        <li><i class="fas fa-check"></i> Skin aktarımı</li>
                    </ul>
                    <div class="card-badge">PREMIUM</div>
                </div>
            </div>

            <!-- Ana Kayıt Formu -->
            <div class="main-register-form" id="registerForm">
                <h3 class="form-title"><i class="fas fa-pen-fancy"></i> YUJINETWORK KAYIT FORMU</h3>
                
                <form id="registrationForm">
                    <div class="form-row">
                        <div class="form-group">
                            <label><i class="fas fa-user"></i> Kullanıcı Adı</label>
                            <div class="input-wrapper">
                                <i class="fas fa-user"></i>
                                <input type="text" class="form-control" id="username" placeholder="Minecraft kullanıcı adın" required>
                            </div>
                        </div>

                        <div class="form-group">
                            <label><i class="fas fa-envelope"></i> E-posta</label>
                            <div class="input-wrapper">
                                <i class="fas fa-envelope"></i>
                                <input type="email" class="form-control" id="email" placeholder="ornek@email.com" required>
                            </div>
                        </div>
                    </div>

                    <div class="form-row">
                        <div class="form-group">
                            <label><i class="fas fa-lock"></i> Şifre</label>
                            <div class="input-wrapper">
                                <i class="fas fa-lock"></i>
                                <input type="password" class="form-control" id="password" placeholder="••••••••" required onkeyup="checkPasswordStrength(this.value)">
                            </div>
                            <div class="password-strength">
                                <div class="strength-bar" id="strengthBar"></div>
                            </div>
                        </div>

                        <div class="form-group">
                            <label><i class="fas fa-lock"></i> Şifre Tekrar</label>
                            <div class="input-wrapper">
                                <i class="fas fa-lock"></i>
                                <input type="password" class="form-control" id="confirmPassword" placeholder="••••••••" required>
                            </div>
                        </div>
                    </div>

                    <div class="checkbox-group">
                        <input type="checkbox" id="terms" required>
                        <label for="terms"><a href="#">Kullanım koşulları</a>'nı kabul ediyorum.</label>
                    </div>

                    <button type="submit" class="register-submit-btn">
                        <i class="fas fa-check-circle"></i>
                        HESAP OLUŞTUR
                    </button>

                    <div class="login-link">
                        Zaten hesabın var mı? <a href="#" onclick="showLogin()">Giriş Yap</a>
                    </div>
                </form>
            </div>
        </div>
    </section>

    <!-- OYUN MODLARI -->
    <section id="modlar" class="modes-section">
        <div class="container">
            <div class="section-header">
                <h2 class="section-title">OYUN <span>MODLARI</span></h2>
                <div class="online-total">
                    <i class="fas fa-users" style="color: var(--primary);"></i>
                    <span class="total-online" id="totalOnline">468</span>
                    <span class="total-label">oyuncu online</span>
                </div>
            </div>

            <div class="modes-grid-modern">
                <!-- BEDWARS -->
                <div class="mode-card-modern">
                    <div class="mode-card-header">
                        <span class="mode-icon">⚔️</span>
                        <span class="mode-badge populer">POPÜLER</span>
                    </div>
                    <h3 class="mode-title">Bedwars</h3>
                    <p class="mode-description">Takımınla yatakları koru, rakipleri ele!</p>
                    <div class="live-counter">
                        <div class="counter-header">
                            <span class="live-dot"></span>
                            <span class="live-text">CANLI</span>
                        </div>
                        <div class="counter-number" id="bedwars-count">124</div>
                        <div class="counter-label">oyuncu aktif</div>
                    </div>
                    <button class="join-btn" onclick="joinGame('bedwars')">
                        <i class="fas fa-play"></i> HEMEN OYNA
                    </button>
                </div>

                <!-- SKYWARS -->
                <div class="mode-card-modern">
                    <div class="mode-card-header">
                        <span class="mode-icon">🌌</span>
                        <span class="mode-badge yeni">YENİ</span>
                    </div>
                    <h3 class="mode-title">Skywars</h3>
                    <p class="mode-description">Gökyüzü adalarında hayatta kal!</p>
                    <div class="live-counter">
                        <div class="counter-header">
                            <span class="live-dot"></span>
                            <span class="live-text">CANLI</span>
                        </div>
                        <div class="counter-number" id="skywars-count">89</div>
                        <div class="counter-label">oyuncu aktif</div>
                    </div>
                    <button class="join-btn" onclick="joinGame('skywars')">
                        <i class="fas fa-play"></i> HEMEN OYNA
                    </button>
                </div>

                <!-- SURVIVAL -->
                <div class="mode-card-modern">
                    <div class="mode-card-header">
                        <span class="mode-icon">🏝️</span>
                        <span class="mode-badge klasik">KLASİK</span>
                    </div>
                    <h3 class="mode-title">Survival</h3>
                    <p class="mode-description">Arkadaşlarınla hayatta kal ve inşa et!</p>
                    <div class="live-counter">
                        <div class="counter-header">
                            <span class="live-dot"></span>
                            <span class="live-text">CANLI</span>
                        </div>
                        <div class="counter-number" id="survival-count">256</div>
                        <div class="counter-label">oyuncu aktif</div>
                    </div>
                    <button class="join-btn" onclick="joinGame('survival')">
                        <i class="fas fa-play"></i> HEMEN OYNA
                    </button>
                </div>
            </div>
        </div>
    </section>

    <!-- İSTATİSTİKLER -->
    <div class="container">
        <div class="stats-section">
            <div class="stats-grid-modern">
                <div class="stat-item-modern">
                    <div class="stat-value">1.5K+</div>
                    <div class="stat-label-modern">Kayıtlı Oyuncu</div>
                </div>
                <div class="stat-item-modern">
                    <div class="stat-value" id="totalOnlineStat">468</div>
                    <div class="stat-label-modern">Online Oyuncu</div>
                </div>
                <div class="stat-item-modern">
                    <div class="stat-value">7/24</div>
                    <div class="stat-label-modern">Aktif Sunucu</div>
                </div>
                <div class="stat-item-modern">
                    <div class="stat-value">1.21</div>
                    <div class="stat-label-modern">Sürüm</div>
                </div>
            </div>
        </div>
    </div>

    <!-- FOOTER -->
    <footer id="iletisim">
        <div class="container">
            <div class="footer-grid">
                <div>
                    <div class="footer-logo">YujiNetwork</div>
                    <p class="footer-text">Minecraft sunucusu ve YouTube kanalı. Bedwars, Skywars ve eğlenceli içerikler. TikTok jeton ile rank satın al!</p>
                </div>

                <div>
                    <h4 class="footer-title">Hızlı Linkler</h4>
                    <ul class="footer-links">
                        <li><a href="#">Ana Sayfa</a></li>
                        <li><a href="#videolar">Videolar</a></li>
                        <li><a href="#modlar">Modlar</a></li>
                        <li><a href="#magaza">Mağaza</a></li>
                        <li><a href="#kayit">Kayıt</a></li>
                    </ul>
                </div>

                <div>
                    <h4 class="footer-title">Yasal</h4>
                    <ul class="footer-links">
                        <li><a href="#">Gizlilik Politikası</a></li>
                        <li><a href="#">Kullanım Şartları</a></li>
                        <li><a href="#">Kurallar</a></li>
                    </ul>
                </div>

                <div>
                    <h4 class="footer-title">Takip Et</h4>
                    <div class="social-grid">
                        <a href="https://youtube.com/@yujiminicıraft" target="_blank"><i class="fab fa-youtube"></i></a>
                        <a href="#"><i class="fab fa-tiktok"></i></a>
                        <a href="#"><i class="fab fa-discord"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-twitch"></i></a>
                    </div>
                </div>
            </div>

            <div class="copyright">
                © 2026 YujiNetwork. Tüm hakları saklıdır. | YouTube: @yujiminicıraft | TikTok Jeton ile Satın Al
            </div>
        </div>
    </footer>

    <!-- JAVASCRIPT -->
    <script>
        // Token sistemi
        let userTokens = localStorage.getItem('tiktokTokens') ? parseInt(localStorage.getItem('tiktokTokens')) : 0;
        
        // Satın alma geçmişi
        let purchaseHistory = localStorage.getItem('purchaseHistory') ? JSON.parse(localStorage.getItem('purchaseHistory')) : [
            { player: "Notch", rank: "LEGEND", time: "5 dk önce" },
            { player: "Steve", rank: "ELITE", time: "12 dk önce" },
            { player: "Alex", rank: "VIP", time: "25 dk önce" },
            { player: "Herobrine", rank: "ELITE", time: "32 dk önce" },
            { player: "Dream", rank: "VIP", time: "45 dk önce" }
        ];
        
        function updateTokenDisplay() {
            document.getElementById('tokenBalance').textContent = userTokens;
            localStorage.setItem('tiktokTokens', userTokens);
        }
        
        function updatePurchasesList() {
            const listElement = document.getElementById('purchasesList');
            listElement.innerHTML = '';
            
            purchaseHistory.forEach(purchase => {
                const item = document.createElement('div');
                item.className = 'purchase-item';
                
                let rankColor = '';
                let rankIcon = '';
                if (purchase.rank === 'VIP') {
                    rankIcon = '⚡';
                } else if (purchase.rank === 'ELITE') {
                    rankIcon = '💎';
                } else if (purchase.rank === 'LEGEND') {
                    rankIcon = '👑';
                }
                
                item.innerHTML = `
                    <div class="purchase-rank">${rankIcon}</div>
                    <div class="purchase-info">
                        <div class="purchase-player">${purchase.player}</div>
                        <div class="purchase-details">
                            <span class="purchase-rank-name">${purchase.rank} Rank</span>
                            <span class="purchase-time"><i class="far fa-clock"></i> ${purchase.time}</span>
                        </div>
                    </div>
                    <div class="purchase-badge">${purchase.rank}</div>
                `;
                
                listElement.appendChild(item);
            });
            
            localStorage.setItem('purchaseHistory', JSON.stringify(purchaseHistory));
        }
        
        function addTokens() {
            let amount = prompt('Kaç jeton eklemek istersin? (Demo amaçlıdır)', '100');
            if (amount && !isNaN(amount) && amount > 0) {
                userTokens += parseInt(amount);
                updateTokenDisplay();
                alert(`✅ ${amount} jeton hesabına eklendi! Toplam: ${userTokens} jeton`);
            }
        }
        
        function buyItem(itemName, price) {
            if (userTokens >= price) {
                userTokens -= price;
                updateTokenDisplay();
                
                // Rastgele oyuncu ismi oluştur
                const players = ["Notch", "Steve", "Alex", "Herobrine", "Dream", "George", "Sapnap", "BadBoyHalo"];
                const randomPlayer = players[Math.floor(Math.random() * players.length)];
                
                // Zamanı hesapla
                const now = new Date();
                const timeStr = "az önce";
                
                // Satın almayı listeye ekle
                purchaseHistory.unshift({
                    player: randomPlayer,
                    rank: itemName,
                    time: timeStr
                });
                
                // Son 10 kaydı tut
                if (purchaseHistory.length > 10) {
                    purchaseHistory.pop();
                }
                
                updatePurchasesList();
                
                alert(`✅ ${itemName} rank başarıyla satın alındı! Kalan jeton: ${userTokens}\n\n🎉 Tebrikler ${randomPlayer}!`);
            } else {
                alert(`❌ Yetersiz jeton! İhtiyacın olan: ${price - userTokens} jeton daha eklemelisin.`);
            }
        }

        function copyIP() {
            const ip = "yujismp.mcsh.io";
            navigator.clipboard.writeText(ip).then(() => {
                alert("✅ Sunucu IP'si kopyalandı: " + ip);
            });
        }

        function watchVideo(title) {
            window.open('https://youtube.com/@yujiminicıraft', '_blank');
        }

        function selectCard(cardNumber) {
            document.getElementById('card1').classList.remove('active');
            document.getElementById('card2').classList.remove('active');
            document.getElementById('card3').classList.remove('active');
            document.getElementById(`card${cardNumber}`).classList.add('active');
        }

        function checkPasswordStrength(password) {
            const strengthBar = document.getElementById('strengthBar');
            let strength = 0;
            if (password.length >= 6) strength += 33;
            if (password.match(/[a-z]+/)) strength += 33;
            if (password.match(/[0-9]+/)) strength += 34;
            strengthBar.style.width = strength + '%';
        }

        function showLogin() {
            alert('🔐 Giriş sayfası yakında!');
        }

        function joinGame(mode) {
            alert(`⚔️ ${mode} moduna bağlanmak için IP: yujismp.mcsh.io`);
        }

        // Canlı oyuncu sayıları
        let players = { bedwars: 124, skywars: 89, survival: 256 };
        
        function updateCounts() {
            document.getElementById('bedwars-count').textContent = players.bedwars;
            document.getElementById('skywars-count').textContent = players.skywars;
            document.getElementById('survival-count').textContent = players.survival;
            let total = players.bedwars + players.skywars + players.survival;
            document.getElementById('totalOnline').textContent = total;
            document.getElementById('totalOnlineStat').textContent = total;
        }

        setInterval(() => {
            players.bedwars = Math.max(80, Math.min(200, players.bedwars + Math.floor(Math.random() * 11) - 5));
            players.skywars = Math.max(50, Math.min(150, players.skywars + Math.floor(Math.random() * 11) - 5));
            players.survival = Math.max(150, Math.min(350, players.survival + Math.floor(Math.random() * 11) - 5));
            updateCounts();
        }, 8000);

        document.getElementById('registrationForm').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('✅ Kayıt başarılı! Sunucuya giriş yapabilirsin.');
        });

        // Sayfa yüklendiğinde
        window.onload = function() {
            updateTokenDisplay();
            updatePurchasesList();
        };
    </script>
</body>
</html>
