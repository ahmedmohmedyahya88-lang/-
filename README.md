<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>صحتي - دليلك الطبي الشامل</title>
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;500;700;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --bg-primary: #0f172a;
            --bg-secondary: #1e293b;
            --bg-card: #1e293b;
            --bg-hover: #334155;
            --text-primary: #f1f5f9;
            --text-secondary: #94a3b8;
            --accent-teal: #14b8a6;
            --accent-purple: #a855f7;
            --accent-blue: #3b82f6;
            --accent-gold: #f59e0b;
            --accent-rose: #f43f5e;
            --border: #334155;
            --success: #22c55e;
            --warning: #f59e0b;
            --danger: #ef4444;
            --glass: rgba(30, 41, 59, 0.8);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Tajawal', sans-serif;
            background: linear-gradient(135deg, #0f172a 0%, #1e1b4b 50%, #0f172a 100%);
            color: var(--text-primary);
            min-height: 100vh;
            overflow-x: hidden;
        }

        /* Animated Background */
        .bg-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            overflow: hidden;
        }

        .bg-animation .circle {
            position: absolute;
            border-radius: 50%;
            filter: blur(80px);
            opacity: 0.15;
            animation: float 20s infinite ease-in-out;
        }

        .bg-animation .circle:nth-child(1) {
            width: 400px;
            height: 400px;
            background: var(--accent-teal);
            top: -10%;
            right: -10%;
            animation-delay: 0s;
        }

        .bg-animation .circle:nth-child(2) {
            width: 300px;
            height: 300px;
            background: var(--accent-purple);
            bottom: -10%;
            left: -10%;
            animation-delay: 5s;
        }

        .bg-animation .circle:nth-child(3) {
            width: 250px;
            height: 250px;
            background: var(--accent-blue);
            top: 50%;
            left: 50%;
            animation-delay: 10s;
        }

        @keyframes float {
            0%, 100% { transform: translate(0, 0) scale(1); }
            33% { transform: translate(30px, -30px) scale(1.1); }
            66% { transform: translate(-20px, 20px) scale(0.9); }
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: var(--glass);
            backdrop-filter: blur(20px);
            border-bottom: 1px solid var(--border);
            z-index: 1000;
            padding: 1rem 2rem;
        }

        .nav-container {
            max-width: 1400px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 0.75rem;
            font-size: 1.5rem;
            font-weight: 800;
            color: var(--accent-teal);
            text-decoration: none;
        }

        .logo i {
            font-size: 2rem;
            background: linear-gradient(135deg, var(--accent-teal), var(--accent-blue));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
        }

        .nav-links a {
            color: var(--text-secondary);
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s;
            position: relative;
            padding: 0.5rem 0;
        }

        .nav-links a:hover, .nav-links a.active {
            color: var(--accent-teal);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: 0;
            right: 0;
            width: 0;
            height: 2px;
            background: linear-gradient(90deg, var(--accent-teal), var(--accent-blue));
            transition: width 0.3s;
        }

        .nav-links a:hover::after, .nav-links a.active::after {
            width: 100%;
        }

        /* Hero Section */
        .hero {
            padding: 10rem 2rem 6rem;
            text-align: center;
            max-width: 1400px;
            margin: 0 auto;
        }

        .hero-badge {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            background: rgba(20, 184, 166, 0.1);
            border: 1px solid var(--accent-teal);
            color: var(--accent-teal);
            padding: 0.5rem 1.5rem;
            border-radius: 50px;
            font-size: 0.9rem;
            margin-bottom: 2rem;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { box-shadow: 0 0 0 0 rgba(20, 184, 166, 0.4); }
            50% { box-shadow: 0 0 0 10px rgba(20, 184, 166, 0); }
        }

        .hero h1 {
            font-size: 4rem;
            font-weight: 800;
            margin-bottom: 1.5rem;
            line-height: 1.2;
        }

        .hero h1 span {
            background: linear-gradient(135deg, var(--accent-teal), var(--accent-purple), var(--accent-blue));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero p {
            font-size: 1.25rem;
            color: var(--text-secondary);
            max-width: 700px;
            margin: 0 auto 3rem;
            line-height: 1.8;
        }

        .hero-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn {
            padding: 1rem 2.5rem;
            border-radius: 12px;
            font-weight: 700;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s;
            border: none;
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            text-decoration: none;
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--accent-teal), var(--accent-blue));
            color: white;
            box-shadow: 0 4px 15px rgba(20, 184, 166, 0.3);
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(20, 184, 166, 0.4);
        }

        .btn-secondary {
            background: transparent;
            color: var(--text-primary);
            border: 2px solid var(--border);
        }

        .btn-secondary:hover {
            border-color: var(--accent-teal);
            color: var(--accent-teal);
        }

        /* Stats Bar */
        .stats-bar {
            display: flex;
            justify-content: center;
            gap: 4rem;
            padding: 3rem 2rem;
            flex-wrap: wrap;
        }

        .stat-item {
            text-align: center;
        }

        .stat-number {
            font-size: 3rem;
            font-weight: 800;
            background: linear-gradient(135deg, var(--accent-teal), var(--accent-purple));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .stat-label {
            color: var(--text-secondary);
            font-size: 0.9rem;
            margin-top: 0.5rem;
        }

        /* Sections */
        section {
            padding: 5rem 2rem;
            max-width: 1400px;
            margin: 0 auto;
        }

        .section-header {
            text-align: center;
            margin-bottom: 4rem;
        }

        .section-header h2 {
            font-size: 2.5rem;
            font-weight: 800;
            margin-bottom: 1rem;
        }

        .section-header h2 span {
            color: var(--accent-teal);
        }

        .section-header p {
            color: var(--text-secondary);
            font-size: 1.1rem;
            max-width: 600px;
            margin: 0 auto;
        }

        /* Cards Grid */
        .cards-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
        }

        .card {
            background: var(--bg-card);
            border: 1px solid var(--border);
            border-radius: 20px;
            padding: 2rem;
            transition: all 0.4s;
            position: relative;
            overflow: hidden;
        }

        .card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 3px;
            background: linear-gradient(90deg, var(--accent-teal), var(--accent-purple));
            transform: scaleX(0);
            transition: transform 0.4s;
        }

        .card:hover {
            transform: translateY(-5px);
            border-color: var(--accent-teal);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
        }

        .card:hover::before {
            transform: scaleX(1);
        }

        .card-icon {
            width: 60px;
            height: 60px;
            border-radius: 16px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            margin-bottom: 1.5rem;
        }

        .card-icon.teal { background: rgba(20, 184, 166, 0.1); color: var(--accent-teal); }
        .card-icon.purple { background: rgba(168, 85, 247, 0.1); color: var(--accent-purple); }
        .card-icon.blue { background: rgba(59, 130, 246, 0.1); color: var(--accent-blue); }
        .card-icon.gold { background: rgba(245, 158, 11, 0.1); color: var(--accent-gold); }
        .card-icon.rose { background: rgba(244, 63, 94, 0.1); color: var(--accent-rose); }

        .card h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
        }

        .card p {
            color: var(--text-secondary);
            line-height: 1.8;
            margin-bottom: 1.5rem;
        }

        .card-features {
            list-style: none;
            margin-bottom: 1.5rem;
        }

        .card-features li {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            color: var(--text-secondary);
            margin-bottom: 0.5rem;
            font-size: 0.9rem;
        }

        .card-features li i {
            color: var(--accent-teal);
            font-size: 0.8rem;
        }

        .card-btn {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            color: var(--accent-teal);
            text-decoration: none;
            font-weight: 700;
            transition: gap 0.3s;
        }

        .card-btn:hover {
            gap: 1rem;
        }

        /* Diabetes Special Section */
        .diabetes-hero {
            background: linear-gradient(135deg, rgba(20, 184, 166, 0.05), rgba(168, 85, 247, 0.05));
            border: 1px solid var(--border);
            border-radius: 24px;
            padding: 4rem;
            margin: 4rem auto;
            max-width: 1400px;
            position: relative;
            overflow: hidden;
        }

        .diabetes-hero::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -20%;
            width: 600px;
            height: 600px;
            background: radial-gradient(circle, rgba(20, 184, 166, 0.1), transparent 70%);
            border-radius: 50%;
        }

        .diabetes-content {
            position: relative;
            z-index: 1;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
        }

        .diabetes-text h2 {
            font-size: 2.5rem;
            margin-bottom: 1.5rem;
        }

        .diabetes-text h2 span {
            color: var(--accent-teal);
        }

        .diabetes-text p {
            color: var(--text-secondary);
            line-height: 1.8;
            margin-bottom: 2rem;
        }

        .diabetes-stats {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 1.5rem;
        }

        .diabetes-stat {
            background: var(--bg-primary);
            border: 1px solid var(--border);
            border-radius: 16px;
            padding: 1.5rem;
            text-align: center;
        }

        .diabetes-stat i {
            font-size: 2rem;
            color: var(--accent-teal);
            margin-bottom: 0.5rem;
        }

        .diabetes-stat h4 {
            font-size: 1.5rem;
            margin-bottom: 0.25rem;
        }

        .diabetes-stat span {
            color: var(--text-secondary);
            font-size: 0.85rem;
        }

        /* Blood Sugar Tracker */
        .tracker-section {
            background: var(--bg-card);
            border: 1px solid var(--border);
            border-radius: 24px;
            padding: 3rem;
            margin: 3rem auto;
            max-width: 900px;
        }

        .tracker-form {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1.5rem;
            margin-bottom: 2rem;
        }

        .form-group {
            display: flex;
            flex-direction: column;
            gap: 0.5rem;
        }

        .form-group label {
            color: var(--text-secondary);
            font-size: 0.9rem;
            font-weight: 500;
        }

        .form-group input, .form-group select {
            background: var(--bg-primary);
            border: 1px solid var(--border);
            border-radius: 12px;
            padding: 0.875rem 1rem;
            color: var(--text-primary);
            font-family: inherit;
            font-size: 1rem;
            transition: all 0.3s;
        }

        .form-group input:focus, .form-group select:focus {
            outline: none;
            border-color: var(--accent-teal);
            box-shadow: 0 0 0 3px rgba(20, 184, 166, 0.1);
        }

        .tracker-result {
            background: var(--bg-primary);
            border-radius: 16px;
            padding: 2rem;
            text-align: center;
            display: none;
        }

        .tracker-result.show {
            display: block;
            animation: fadeIn 0.5s;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .result-value {
            font-size: 4rem;
            font-weight: 800;
            margin: 1rem 0;
        }

        .result-value.normal { color: var(--success); }
        .result-value.warning { color: var(--warning); }
        .result-value.danger { color: var(--danger); }

        .result-message {
            font-size: 1.1rem;
            margin-bottom: 1rem;
        }

        /* Symptoms Checker */
        .symptoms-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 1.5rem;
        }

        .symptom-card {
            background: var(--bg-card);
            border: 1px solid var(--border);
            border-radius: 16px;
            padding: 1.5rem;
            cursor: pointer;
            transition: all 0.3s;
            position: relative;
        }

        .symptom-card:hover {
            border-color: var(--accent-rose);
            transform: translateY(-3px);
        }

        .symptom-card.selected {
            border-color: var(--accent-rose);
            background: rgba(244, 63, 94, 0.05);
        }

        .symptom-card input {
            position: absolute;
            opacity: 0;
        }

        .symptom-card label {
            display: flex;
            align-items: center;
            gap: 1rem;
            cursor: pointer;
            font-weight: 500;
        }

        .symptom-card .checkbox {
            width: 24px;
            height: 24px;
            border: 2px solid var(--border);
            border-radius: 6px;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s;
            flex-shrink: 0;
        }

        .symptom-card.selected .checkbox {
            background: var(--accent-rose);
            border-color: var(--accent-rose);
        }

        .symptom-card.selected .checkbox::after {
            content: '\f00c';
            font-family: 'Font Awesome 6 Free';
            font-weight: 900;
            color: white;
            font-size: 0.8rem;
        }

        /* Comments Section */
        .comments-section {
            margin-top: 3rem;
            padding-top: 3rem;
            border-top: 1px solid var(--border);
        }

        .comments-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 2rem;
        }

        .comments-header h3 {
            font-size: 1.5rem;
        }

        .comment-form {
            background: var(--bg-primary);
            border-radius: 16px;
            padding: 1.5rem;
            margin-bottom: 2rem;
        }

        .comment-form textarea {
            width: 100%;
            background: var(--bg-card);
            border: 1px solid var(--border);
            border-radius: 12px;
            padding: 1rem;
            color: var(--text-primary);
            font-family: inherit;
            resize: vertical;
            min-height: 100px;
            margin-bottom: 1rem;
        }

        .comment-form textarea:focus {
            outline: none;
            border-color: var(--accent-teal);
        }

        .comment-actions {
            display: flex;
            gap: 1rem;
            align-items: center;
            flex-wrap: wrap;
        }

        .vote-buttons {
            display: flex;
            gap: 0.5rem;
        }

        .vote-btn {
            padding: 0.5rem 1rem;
            border-radius: 8px;
            border: 1px solid var(--border);
            background: transparent;
            color: var(--text-secondary);
            cursor: pointer;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            font-family: inherit;
        }

        .vote-btn:hover {
            border-color: var(--accent-teal);
            color: var(--accent-teal);
        }

        .vote-btn.active-agree {
            background: rgba(34, 197, 94, 0.1);
            border-color: var(--success);
            color: var(--success);
        }

        .vote-btn.active-disagree {
            background: rgba(239, 68, 68, 0.1);
            border-color: var(--danger);
            color: var(--danger);
        }

        .comments-list {
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }

        .comment {
            background: var(--bg-primary);
            border-radius: 16px;
            padding: 1.5rem;
            border: 1px solid var(--border);
            transition: all 0.3s;
        }

        .comment:hover {
            border-color: var(--accent-teal);
        }

        .comment-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1rem;
        }

        .comment-author {
            display: flex;
            align-items: center;
            gap: 0.75rem;
        }

        .comment-avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--accent-teal), var(--accent-blue));
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 700;
            color: white;
        }

        .comment-meta {
            display: flex;
            flex-direction: column;
        }

        .comment-name {
            font-weight: 700;
        }

        .comment-date {
            font-size: 0.8rem;
            color: var(--text-secondary);
        }

        .comment-badge {
            padding: 0.25rem 0.75rem;
            border-radius: 50px;
            font-size: 0.75rem;
            font-weight: 700;
        }

        .comment-badge.agree {
            background: rgba(34, 197, 94, 0.1);
            color: var(--success);
        }

        .comment-badge.disagree {
            background: rgba(239, 68, 68, 0.1);
            color: var(--danger);
        }

        .comment-body {
            color: var(--text-secondary);
            line-height: 1.8;
            margin-bottom: 1rem;
        }

        .comment-footer {
            display: flex;
            gap: 1rem;
            color: var(--text-secondary);
            font-size: 0.9rem;
        }

        .comment-footer button {
            background: none;
            border: none;
            color: var(--text-secondary);
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            font-family: inherit;
            transition: color 0.3s;
        }

        .comment-footer button:hover {
            color: var(--accent-teal);
        }

        /* Emergency Banner */
        .emergency-banner {
            background: linear-gradient(135deg, rgba(239, 68, 68, 0.1), rgba(245, 158, 11, 0.1));
            border: 1px solid var(--danger);
            border-radius: 16px;
            padding: 2rem;
            margin: 3rem auto;
            max-width: 1400px;
            display: flex;
            align-items: center;
            gap: 2rem;
            flex-wrap: wrap;
        }

        .emergency-icon {
            width: 60px;
            height: 60px;
            background: rgba(239, 68, 68, 0.2);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            color: var(--danger);
            flex-shrink: 0;
        }

        .emergency-text h3 {
            color: var(--danger);
            margin-bottom: 0.5rem;
        }

        .emergency-text p {
            color: var(--text-secondary);
        }

        .emergency-btn {
            margin-right: auto;
            background: var(--danger);
            color: white;
            padding: 0.875rem 2rem;
            border-radius: 12px;
            text-decoration: none;
            font-weight: 700;
            transition: all 0.3s;
        }

        .emergency-btn:hover {
            background: #dc2626;
            transform: translateY(-2px);
        }

        /* Footer */
        footer {
            background: var(--bg-card);
            border-top: 1px solid var(--border);
            padding: 4rem 2rem 2rem;
            margin-top: 6rem;
        }

        .footer-content {
            max-width: 1400px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 3rem;
        }

        .footer-section h4 {
            font-size: 1.25rem;
            margin-bottom: 1.5rem;
            color: var(--accent-teal);
        }

        .footer-section ul {
            list-style: none;
        }

        .footer-section ul li {
            margin-bottom: 0.75rem;
        }

        .footer-section ul li a {
            color: var(--text-secondary);
            text-decoration: none;
            transition: color 0.3s;
        }

        .footer-section ul li a:hover {
            color: var(--accent-teal);
        }

        .footer-bottom {
            max-width: 1400px;
            margin: 3rem auto 0;
            padding-top: 2rem;
            border-top: 1px solid var(--border);
            text-align: center;
            color: var(--text-secondary);
            font-size: 0.9rem;
        }

        /* Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
            z-index: 2000;
            align-items: center;
            justify-content: center;
            padding: 2rem;
        }

        .modal.show {
            display: flex;
        }

        .modal-content {
            background: var(--bg-card);
            border: 1px solid var(--border);
            border-radius: 24px;
            padding: 3rem;
            max-width: 800px;
            width: 100%;
            max-height: 90vh;
            overflow-y: auto;
            position: relative;
        }

        .modal-close {
            position: absolute;
            top: 1.5rem;
            left: 1.5rem;
            background: none;
            border: none;
            color: var(--text-secondary);
            font-size: 1.5rem;
            cursor: pointer;
            transition: color 0.3s;
        }

        .modal-close:hover {
            color: var(--text-primary);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero h1 { font-size: 2.5rem; }
            .nav-links { display: none; }
            .diabetes-content { grid-template-columns: 1fr; }
            .stats-bar { gap: 2rem; }
            .cards-grid { grid-template-columns: 1fr; }
        }

        /* Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }

        ::-webkit-scrollbar-track {
            background: var(--bg-primary);
        }

        ::-webkit-scrollbar-thumb {
            background: var(--border);
            border-radius: 4px;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: var(--accent-teal);
        }

        /* Animations */
        .fade-in {
            animation: fadeIn 0.6s ease-out;
        }

        .slide-up {
            animation: slideUp 0.6s ease-out;
        }

        @keyframes slideUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body>
    <!-- Background Animation -->
    <div class="bg-animation">
        <div class="circle"></div>
        <div class="circle"></div>
        <div class="circle"></div>
    </div>

    <!-- Navigation -->
    <nav>
        <div class="nav-container">
            <a href="#" class="logo">
                <i class="fas fa-heart-pulse"></i>
                <span>صحتي</span>
            </a>
            <ul class="nav-links">
                <li><a href="#home" class="active">الرئيسية</a></li>
                <li><a href="#diabetes">السكري</a></li>
                <li><a href="#cancer">السرطان</a></li>
                <li><a href="#burns">الحروق</a></li>
                <li><a href="#symptoms">الأعراض</a></li>
                <li><a href="#tracker">تتبع السكر</a></li>
            </ul>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="hero-badge">
            <i class="fas fa-shield-heart"></i>
            دليلك الطبي الشامل
        </div>
        <h1>صحتك تهمنا<br><span>نحميك ونوقيك</span></h1>
        <p>منصة صحية متكاملة تساعدك في الوقاية من الأمراض، الكشف المبكر عن السرطان، إدارة مرض السكري، والإسعافات الأولية للحروق</p>
        <div class="hero-buttons">
            <a href="#diabetes" class="btn btn-primary">
                <i class="fas fa-droplet"></i>
                ابدأ رحلتك الصحية
            </a>
            <a href="#symptoms" class="btn btn-secondary">
                <i class="fas fa-stethoscope"></i>
                فحص الأعراض
            </a>
        </div>
    </section>

    <!-- Stats -->
    <div class="stats-bar">
        <div class="stat-item">
            <div class="stat-number">+500</div>
            <div class="stat-label">نصيحة طبية</div>
        </div>
        <div class="stat-item">
            <div class="stat-number">+50</div>
            <div class="stat-label">مقالة توعوية</div>
        </div>
        <div class="stat-item">
            <div class="stat-number">24/7</div>
            <div class="stat-label">دعم صحي</div>
        </div>
        <div class="stat-item">
            <div class="stat-number">100%</div>
            <div class="stat-label">مجاني</div>
        </div>
    </div>

    <!-- Diabetes Special Section -->
    <section class="diabetes-hero" id="diabetes">
        <div class="diabetes-content">
            <div class="diabetes-text">
                <div class="hero-badge" style="margin-bottom: 1rem;">
                    <i class="fas fa-star"></i>
                    قسم مخصص
                </div>
                <h2>مرض السكري<br><span>تفهم .. تعايش .. تتحكم</span></h2>
                <p>مرض السكري مش نهاية العالم! مع المتابعة الصحيحة والنظام الغذائي المتوازن، تقدر تعيش حياة طبيعية وسعيدة. نقدم لك أدوات تتبع مستوى السكر، نصائح يومية، ودليل شامل للأعراض والمضاعفات.</p>
                <div class="hero-buttons">
                    <button class="btn btn-primary" onclick="openModal('diabetesModal')">
                        <i class="fas fa-book-medical"></i>
                        الدليل الشامل
                    </button>
                    <a href="#tracker" class="btn btn-secondary">
                        <i class="fas fa-chart-line"></i>
                        تتبع السكر
                    </a>
                </div>
            </div>
            <div class="diabetes-stats">
                <div class="diabetes-stat">
                    <i class="fas fa-droplet"></i>
                    <h4>70-180</h4>
                    <span>مستوى السكر الطبيعي</span>
                </div>
                <div class="diabetes-stat">
                    <i class="fas fa-clock"></i>
                    <h4>كل 3 شهور</h4>
                    <span>فحص HbA1c</span>
                </div>
                <div class="diabetes-stat">
                    <i class="fas fa-footprints"></i>
                    <h4>يومياً</h4>
                    <span>فحص القدم</span>
                </div>
                <div class="diabetes-stat">
                    <i class="fas fa-eye"></i>
                    <h4>سنوياً</h4>
                    <span>فحص العين</span>
                </div>
            </div>
        </div>
    </section>

    <!-- Blood Sugar Tracker -->
    <section class="tracker-section" id="tracker">
        <div class="section-header">
            <h2>📊 <span>تتبع مستوى السكر</span></h2>
            <p>سجل قياساتك اليومية واحصل على تحليل فوري لحالتك</p>
        </div>
        <div class="tracker-form">
            <div class="form-group">
                <label>مستوى السكر (mg/dL)</label>
                <input type="number" id="sugarLevel" placeholder="مثال: 120" min="30" max="600">
            </div>
            <div class="form-group">
                <label>وقت القياس</label>
                <select id="measureTime">
                    <option value="fasting">الصيام (قبل الأكل)</option>
                    <option value="before">قبل الأكل</option>
                    <option value="after">بعد الأكل بساعتين</option>
                    <option value="random">عشوائي</option>
                </select>
            </div>
            <div class="form-group">
                <label>التاريخ</label>
                <input type="date" id="measureDate">
            </div>
        </div>
        <button class="btn btn-primary" onclick="checkSugar()" style="width: 100%; justify-content: center;">
            <i class="fas fa-calculator"></i>
            تحليل القياس
        </button>
        
        <div class="tracker-result" id="trackerResult">
            <div id="resultIcon" style="font-size: 3rem; margin-bottom: 1rem;"></div>
            <div class="result-value" id="resultValue"></div>
            <div class="result-message" id="resultMessage"></div>
            <div id="resultAdvice" style="color: var(--text-secondary); line-height: 1.8;"></div>
        </div>
    </section>

    <!-- Sections Grid -->
    <section id="cancer">
        <div class="section-header">
            <h2>🎗️ <span>الوقاية من السرطان</span></h2>
            <p>الكشف المبكر ينقذ الأرواح - تعرف على طرق الوقاية والكشف المبكر</p>
        </div>
        <div class="cards-grid">
            <div class="card">
                <div class="card-icon purple"><i class="fas fa-ribbon"></i></div>
                <h3>الكشف المبكر عن سرطان الثدي</h3>
                <p>الفحص الذاتي الشهري ضروري لكل سيدة فوق 20 سنة. الكشف المبكر يزيد فرص الشفاء إلى 95%.</p>
                <ul class="card-features">
                    <li><i class="fas fa-check"></i> الفحص الذاتي الشهري</li>
                    <li><i class="fas fa-check"></i> الماموجرام سنوياً بعد 40 سنة</li>
                    <li><i class="fas fa-check"></i> استشارة الطبيب فوراً عند أي تغيير</li>
                </ul>
                <a href="#" class="card-btn" onclick="openModal('breastModal'); return false;">
                    اقرأ المزيد <i class="fas fa-arrow-left"></i>
                </a>
                <div class="comments-section" style="margin-top: 1.5rem; padding-top: 1.5rem;">
                    <div class="comment-form">
                        <textarea placeholder="شارك رأيك أو تجربتك هنا..."></textarea>
                        <div class="comment-actions">
                            <div class="vote-buttons">
                                <button class="vote-btn" onclick="toggleVote(this, 'agree')">
                                    <i class="fas fa-thumbs-up"></i> فعلاً
                                </button>
                                <button class="vote-btn" onclick="toggleVote(this, 'disagree')">
                                    <i class="fas fa-thumbs-down"></i> مش صحيح
                                </button>
                            </div>
                            <button class="btn btn-primary" style="padding: 0.5rem 1.5rem; font-size: 0.9rem;">
                                <i class="fas fa-paper-plane"></i> نشر
                            </button>
                        </div>
                    </div>
                    <div class="comments-list">
                        <div class="comment">
                            <div class="comment-header">
                                <div class="comment-author">
                                    <div class="comment-avatar">س</div>
                                    <div class="comment-meta">
                                        <span class="comment-name">سارة أحمد</span>
                                        <span class="comment-date">منذ يومين</span>
                                    </div>
                                </div>
                                <span class="comment-badge agree">✓ فعلاً</span>
                            </div>
                            <div class="comment-body">الكشف المبكر فعلاً أنقذ حياة قريبتي. اكتشفت الورم في مرحلة مبكرة والحمد لله شافت تماماً.</div>
                            <div class="comment-footer">
                                <button><i class="fas fa-heart"></i> 24</button>
                                <button><i class="fas fa-reply"></i> رد</button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <div class="card">
                <div class="card-icon rose"><i class="fas fa-lungs"></i></div>
                <h3>سرطان الرئة - أعراض ووقاية</h3>
                <p>أكثر أنواع السرطان شيوعاً. الإقلاع عن التدخين يقلل الخطر بنسبة 90%.</p>
                <ul class="card-features">
                    <li><i class="fas fa-check"></i> سعال مستمر أكثر من 3 أسابيع</li>
                    <li><i class="fas fa-check"></i> دم في البلغم</li>
                    <li><i class="fas fa-check"></i> ألم في الصدر عند التنفس</li>
                </ul>
                <a href="#" class="card-btn" onclick="openModal('lungModal'); return false;">
                    اقرأ المزيد <i class="fas fa-arrow-left"></i>
                </a>
                <div class="comments-section" style="margin-top: 1.5rem; padding-top: 1.5rem;">
                    <div class="comment-form">
                        <textarea placeholder="شارك رأيك أو تجربتك هنا..."></textarea>
                        <div class="comment-actions">
                            <div class="vote-buttons">
                                <button class="vote-btn" onclick="toggleVote(this, 'agree')">
                                    <i class="fas fa-thumbs-up"></i> فعلاً
                                </button>
                                <button class="vote-btn" onclick="toggleVote(this, 'disagree')">
                                    <i class="fas fa-thumbs-down"></i> مش صحيح
                                </button>
                            </div>
                            <button class="btn btn-primary" style="padding: 0.5rem 1.5rem; font-size: 0.9rem;">
                                <i class="fas fa-paper-plane"></i> نشر
                            </button>
                        </div>
                    </div>
                </div>
            </div>

            <div class="card">
                <div class="card-icon gold"><i class="fas fa-apple-whole"></i></div>
                <h3>النظام الغذائي الوقائي</h3>
                <p>تناول الأطعمة الغنية بمضادات الأكسدة يقلل خطر الإصابة بالسرطان بنسبة 30%.</p>
                <ul class="card-features">
                    <li><i class="fas fa-check"></i> 5 حصص خضروات و فواكه يومياً</li>
                    <li><i class="fas fa-check"></i> تقليل اللحوم المصنعة</li>
                    <li><i class="fas fa-check"></i> ممارسة الرياضة 150 دقيقة أسبوعياً</li>
                </ul>
                <a href="#" class="card-btn" onclick="openModal('dietModal'); return false;">
                    اقرأ المزيد <i class="fas fa-arrow-left"></i>
                </a>
                <div class="comments-section" style="margin-top: 1.5rem; padding-top: 1.5rem;">
                    <div class="comment-form">
                        <textarea placeholder="شارك رأيك أو تجربتك هنا..."></textarea>
                        <div class="comment-actions">
                            <div class="vote-buttons">
                                <button class="vote-btn" onclick="toggleVote(this, 'agree')">
                                    <i class="fas fa-thumbs-up"></i> فعلاً
                                </button>
                                <button class="vote-btn" onclick="toggleVote(this, 'disagree')">
                                    <i class="fas fa-thumbs-down"></i> مش صحيح
                                </button>
                            </div>
                            <button class="btn btn-primary" style="padding: 0.5rem 1.5rem; font-size: 0.9rem;">
                                <i class="fas fa-paper-plane"></i> نشر
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Burns Section -->
    <section id="burns">
        <div class="section-header">
            <h2>🔥 <span>الوقاية من الحروق والإسعافات الأولية</span></h2>
            <p>تعرف على كيفية الوقاية من الحروق وخطوات الإسعافات الأولية الصحيحة</p>
        </div>
        <div class="cards-grid">
            <div class="card">
                <div class="card-icon gold"><i class="fas fa-fire-extinguisher"></i></div>
                <h3>الوقاية من الحروق المنزلية</h3>
                <p>80% من الحروق تحدث في المنزل. اتبع هذه النصائح لحماية عائلتك.</p>
                <ul class="card-features">
                    <li><i class="fas fa-check"></i> تركيب جهاز إنذار الحريق</li>
                    <li><i class="fas fa-check"></i> وضع مقابض الأواني للخلف</li>
                    <li><i class="fas fa-check"></i> تعيين درجة حرارة الماء بـ 49°م</li>
                </ul>
                <a href="#" class="card-btn" onclick="openModal('burnsModal'); return false;">
                    اقرأ المزيد <i class="fas fa-arrow-left"></i>
                </a>
                <div class="comments-section" style="margin-top: 1.5rem; padding-top: 1.5rem;">
                    <div class="comment-form">
                        <textarea placeholder="شارك رأيك أو تجربتك هنا..."></textarea>
                        <div class="comment-actions">
                            <div class="vote-buttons">
                                <button class="vote-btn" onclick="toggleVote(this, 'agree')">
                                    <i class="fas fa-thumbs-up"></i> فعلاً
                                </button>
                                <button class="vote-btn" onclick="toggleVote(this, 'disagree')">
                                    <i class="fas fa-thumbs-down"></i> مش صحيح
                                </button>
                            </div>
                            <button class="btn btn-primary" style="padding: 0.5rem 1.5rem; font-size: 0.9rem;">
                                <i class="fas fa-paper-plane"></i> نشر
                            </button>
                        </div>
                    </div>
                </div>
            </div>

            <div class="card">
                <div class="card-icon rose"><i class="fas fa-kit-medical"></i></div>
                <h3>الإسعافات الأولية للحروق</h3>
                <p>الدقائق الأولى بعد الحرق هي الأهم. تعرف على الخطوات الصحيحة.</p>
                <ul class="card-features">
                    <li><i class="fas fa-check"></i> تبريد المنطقة بماء جاري 20 دقيقة</li>
                    <li><i class="fas fa-check"></i> عدم استخدام الثلج مباشرة</li>
                    <li><i class="fas fa-check"></i> تغطية الحرق بضمادة نظيفة</li>
                </ul>
                <a href="#" class="card-btn" onclick="openModal('firstAidModal'); return false;">
                    اقرأ المزيد <i class="fas fa-arrow-left"></i>
                </a>
                <div class="comments-section" style="margin-top: 1.5rem; padding-top: 1.5rem;">
                    <div class="comment-form">
                        <textarea placeholder="شارك رأيك أو تجربتك هنا..."></textarea>
                        <div class="comment-actions">
                            <div class="vote-buttons">
                                <button class="vote-btn" onclick="toggleVote(this, 'agree')">
                                    <i class="fas fa-thumbs-up"></i> فعلاً
                                </button>
                                <button class="vote-btn" onclick="toggleVote(this, 'disagree')">
                                    <i class="fas fa-thumbs-down"></i> مش صحيح
                                </button>
                            </div>
                            <button class="btn btn-primary" style="padding: 0.5rem 1.5rem; font-size: 0.9rem;">
                                <i class="fas fa-paper-plane"></i> نشر
                            </button>
                        </div>
                    </div>
                </div>
            </div>

            <div class="card">
                <div class="card-icon blue"><i class="fas fa-child"></i></div>
                <h3>حماية الأطفال من الحروق</h3>
                <p>الأطفال هم الأكثر عرضة للحروق. احمِ طفلك بهذه الإجراءات.</p>
                <ul class="card-features">
                    <li><i class="fas fa-check"></i> وضع حواجز أمام المدافئ</li>
                    <li><i class="fas fa-check"></i> تخزين المواد الكيميائية بعيداً</li>
                    <li><i class="fas fa-check"></i> تعليم الأطفال مخاطر النار</li>
                </ul>
                <a href="#" class="card-btn" onclick="openModal('kidsModal'); return false;">
                    اقرأ المزيد <i class="fas fa-arrow-left"></i>
                </a>
                <div class="comments-section" style="margin-top: 1.5rem; padding-top: 1.5rem;">
                    <div class="comment-form">
                        <textarea placeholder="شارك رأيك أو تجربتك هنا..."></textarea>
                        <div class="comment-actions">
                            <div class="vote-buttons">
                                <button class="vote-btn" onclick="toggleVote(this, 'agree')">
                                    <i class="fas fa-thumbs-up"></i> فعلاً
                                </button>
                                <button class="vote-btn" onclick="toggleVote(this, 'disagree')">
                                    <i class="fas fa-thumbs-down"></i> مش صحيح
                                </button>
                            </div>
                            <button class="btn btn-primary" style="padding: 0.5rem 1.5rem; font-size: 0.9rem;">
                                <i class="fas fa-paper-plane"></i> نشر
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Diabetes Detailed Section -->
    <section>
        <div class="section-header">
            <h2>💉 <span>إدارة مرض السكري</span></h2>
            <p>دليلك الشامل للتعايش مع السكري بصحة وسعادة</p>
        </div>
        <div class="cards-grid">
            <div class="card">
                <div class="card-icon teal"><i class="fas fa-utensils"></i></div>
                <h3>النظام الغذائي للسكري</h3>
                <p>تناول 3 وجبات رئيسية + وجبتين خفيفة يومياً مع مراعاة توزيع الكربوهيدرات.</p>
                <ul class="card-features">
                    <li><i class="fas fa-check"></i> تقليل السكريات المضافة</li>
                    <li><i class="fas fa-check"></i> تناول الألياف (25-30 جرام يومياً)</li>
                    <li><i class="fas fa-check"></i> شرب 8 أكواب ماء يومياً</li>
                </ul>
                <div class="comments-section" style="margin-top: 1.5rem; padding-top: 1.5rem;">
                    <div class="comment-form">
                        <textarea placeholder="شارك رأيك أو تجربتك هنا..."></textarea>
                        <div class="comment-actions">
                            <div class="vote-buttons">
                                <button class="vote-btn" onclick="toggleVote(this, 'agree')">
                                    <i class="fas fa-thumbs-up"></i> فعلاً
                                </button>
                                <button class="vote-btn" onclick="toggleVote(this, 'disagree')">
                                    <i class="fas fa-thumbs-down"></i> مش صحيح
                                </button>
                            </div>
                            <button class="btn btn-primary" style="padding: 0.5rem 1.5rem; font-size: 0.9rem;">
                                <i class="fas fa-paper-plane"></i> نشر
                            </button>
                        </div>
                    </div>
                </div>
            </div>

            <div class="card">
                <div class="card-icon purple"><i class="fas fa-person-running"></i></div>
                <h3>الرياضة والسكري</h3>
                <p>ممارسة 150 دقيقة رياضة معتدلة أسبوعياً تساعد في خفض السكر وتحسين حساسية الإنسولين.</p>
                <ul class="card-features">
                    <li><i class="fas fa-check"></i> المشي السريع 30 دقيقة يومياً</li>
                    <li><i class="fas fa-check"></i> فحص السكر قبل وبعد الرياضة</li>
                    <li><i class="fas fa-check"></i> حمل سكر أو وجبة خفيفة</li>
                </ul>
                <div class="comments-section" style="margin-top: 1.5rem; padding-top: 1.5rem;">
                    <div class="comment-form">
                        <textarea placeholder="شارك رأيك أو تجربتك هنا..."></textarea>
                        <div class="comment-actions">
                            <div class="vote-buttons">
                                <button class="vote-btn" onclick="toggleVote(this, 'agree')">
                                    <i class="fas fa-thumbs-up"></i> فعلاً
                                </button>
                                <button class="vote-btn" onclick="toggleVote(this, 'disagree')">
                                    <i class="fas fa-thumbs-down"></i> مش صحيح
                                </button>
                            </div>
                            <button class="btn btn-primary" style="padding: 0.5rem 1.5rem; font-size: 0.9rem;">
                                <i class="fas fa-paper-plane"></i> نشر
                            </button>
                        </div>
                    </div>
                </div>
            </div>

            <div class="card">
                <div class="card-icon rose"><i class="fas fa-triangle-exclamation"></i></div>
                <h3>أعراض انخفاض/ارتفاع السكر</h3>
                <p>تعرف على الأعراض الخطيرة التي تستدعي التدخل الفوري.</p>
                <ul class="card-features">
                    <li><i class="fas fa-check"></i> انخفاض: رعشة، تعرق، جوع شديد، دوار</li>
                    <li><i class="fas fa-check"></i> ارتفاع: عطش شديد، تبول متكرر، غثيان</li>
                    <li><i class="fas fa-check"></i> اتصل بالطوارئ فوراً</li>
                </ul>
                <div class="comments-section" style="margin-top: 1.5rem; padding-top: 1.5rem;">
                    <div class="comment-form">
                        <textarea placeholder="شارك رأيك أو تجربتك هنا..."></textarea>
                        <div class="comment-actions">
                            <div class="vote-buttons">
                                <button class="vote-btn" onclick="toggleVote(this, 'agree')">
                                    <i class="fas fa-thumbs-up"></i> فعلاً
                                </button>
                                <button class="vote-btn" onclick="toggleVote(this, 'disagree')">
                                    <i class="fas fa-thumbs-down"></i> مش صحيح
                                </button>
                            </div>
                            <button class="btn btn-primary" style="padding: 0.5rem 1.5rem; font-size: 0.9rem;">
                                <i class="fas fa-paper-plane"></i> نشر
                            </button>
                        </div>
                    </div>
                </div>
            </div>

            <div class="card">
                <div class="card-icon blue"><i class="fas fa-footprints"></i></div>
                <h3>العناية بالقدم السكرية</h3>
                <p>فحص القدم يومياً يمنع 85% من بتر الأطراف السكري.</p>
                <ul class="card-features">
                    <li><i class="fas fa-check"></i> فحص القدم يومياً (بين الأصابع)</li>
                    <li><i class="fas fa-check"></i> غسل القدم بماء فاتر (مش ساخن)</li>
                    <li><i class="fas fa-check"></i> ترطيب الكعبين (مش بين الأصابع)</li>
                </ul>
                <div class="comments-section" style="margin-top: 1.5rem; padding-top: 1.5rem;">
                    <div class="comment-form">
                        <textarea placeholder="شارك رأيك أو تجربتك هنا..."></textarea>
                        <div class="comment-actions">
                            <div class="vote-buttons">
                                <button class="vote-btn" onclick="toggleVote(this, 'agree')">
                                    <i class="fas fa-thumbs-up"></i> فعلاً
                                </button>
                                <button class="vote-btn" onclick="toggleVote(this, 'disagree')">
                                    <i class="fas fa-thumbs-down"></i> مش صحيح
                                </button>
                            </div>
                            <button class="btn btn-primary" style="padding: 0.5rem 1.5rem; font-size: 0.9rem;">
                                <i class="fas fa-paper-plane"></i> نشر
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Symptoms Checker -->
    <section id="symptoms">
        <div class="section-header">
            <h2>🔍 <span>فاحص الأعراض</span></h2>
            <p>اختار الأعراض اللي عندك واعرف إذا كانت تحتاج زيارة الطبيب</p>
        </div>
        <div class="symptoms-grid">
            <div class="symptom-card" onclick="toggleSymptom(this)">
                <label>
                    <div class="checkbox"></div>
                    <span>سعال مستمر أكثر من 3 أسابيع</span>
                </label>
            </div>
            <div class="symptom-card" onclick="toggleSymptom(this)">
                <label>
                    <div class="checkbox"></div>
                    <span>فقدان وزن غير مبرر</span>
                </label>
            </div>
            <div class="symptom-card" onclick="toggleSymptom(this)">
                <label>
                    <div class="checkbox"></div>
                    <span>تعب مستمر وإرهاق</span>
                </label>
            </div>
            <div class="symptom-card" onclick="toggleSymptom(this)">
                <label>
                    <div class="checkbox"></div>
                    <span>تغيير في عادات الأمعاء</span>
                </label>
            </div>
            <div class="symptom-card" onclick="toggleSymptom(this)">
                <label>
                    <div class="checkbox"></div>
                    <span>كدمات أو نزيف متكرر</span>
                </label>
            </div>
            <div class="symptom-card" onclick="toggleSymptom(this)">
                <label>
                    <div class="checkbox"></div>
                    <span>ألم مستمر في أي مكان</span>
                </label>
            </div>
            <div class="symptom-card" onclick="toggleSymptom(this)">
                <label>
                    <div class="checkbox"></div>
                    <span>تغيير في لون البول أو البراز</span>
                </label>
            </div>
            <div class="symptom-card" onclick="toggleSymptom(this)">
                <label>
                    <div class="checkbox"></div>
                    <span>تورم في أي مكان بالجسم</span>
                </label>
            </div>
        </div>
        <div style="text-align: center; margin-top: 2rem;">
            <button class="btn btn-primary" onclick="checkSymptoms()">
                <i class="fas fa-stethoscope"></i>
                تحليل الأعراض
            </button>
        </div>
        <div class="tracker-result" id="symptomsResult" style="margin-top: 2rem;">
            <div id="symptomsMessage"></div>
        </div>
    </section>

    <!-- Emergency Banner -->
    <div class="emergency-banner">
        <div class="emergency-icon">
            <i class="fas fa-truck-medical"></i>
        </div>
        <div class="emergency-text">
            <h3>حالة طوارئ؟</h3>
            <p>في حالة الأعراض الخطيرة (صعوبة في التنفس، ألم صدر حاد، نزيف حاد) اتصل بالإسعاف فوراً</p>
        </div>
        <a href="tel:123" class="emergency-btn">
            <i class="fas fa-phone"></i>
            اتصل بالإسعاف
        </a>
    </div>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="footer-section">
                <h4><i class="fas fa-heart-pulse"></i> صحتي</h4>
                <p style="color: var(--text-secondary); line-height: 1.8; margin-top: 1rem;">
                    منصة صحية مجانية تهدف لنشر الوعي الطبي ومساعدة الناس في الوقاية من الأمراض وإدارتها.
                </p>
            </div>
            <div class="footer-section">
                <h4>أقسام الموقع</h4>
                <ul>
                    <li><a href="#diabetes">السكري</a></li>
                    <li><a href="#cancer">السرطان</a></li>
                    <li><a href="#burns">الحروق</a></li>
                    <li><a href="#symptoms">فاحص الأعراض</a></li>
                </ul>
            </div>
            <div class="footer-section">
                <h4>موارد مهمة</h4>
                <ul>
                    <li><a href="#">حاسبة BMI</a></li>
                    <li><a href="#">جدول السعرات</a></li>
                    <li><a href="#">تمارين منزلية</a></li>
                    <li><a href="#">أسئلة شائعة</a></li>
                </ul>
            </div>
            <div class="footer-section">
                <h4>تواصل معنا</h4>
                <ul>
                    <li><a href="#"><i class="fas fa-envelope"></i> info@sehati.com</a></li>
                    <li><a href="#"><i class="fas fa-phone"></i> 19000</a></li>
                    <li><a href="#"><i class="fab fa-facebook"></i> فيسبوك</a></li>
                    <li><a href="#"><i class="fab fa-twitter"></i> تويتر</a></li>
                </ul>
            </div>
        </div>
        <div class="footer-bottom">
            <p>⚠️ هذا الموقع للتوعية فقط ولا يغني عن استشارة الطبيب المختص</p>
            <p style="margin-top: 0.5rem;">© 2026 صحتي - جميع الحقوق محفوظة</p>
        </div>
    </footer>

    <!-- Modals -->
    <div class="modal" id="diabetesModal">
        <div class="modal-content">
            <button class="modal-close" onclick="closeModal('diabetesModal')"><i class="fas fa-times"></i></button>
            <h2 style="margin-bottom: 1.5rem; color: var(--accent-teal);">الدليل الشامل لمرض السكري</h2>
            <div style="line-height: 2; color: var(--text-secondary);">
                <h3 style="color: var(--text-primary); margin: 1.5rem 0 0.5rem;">ما هو مرض السكري؟</h3>
                <p>مرض السكري هو اضطراب أيضي مزمن يتميز بارتفاع مستوى السكر في الدم نتيجة نقص إنتاج الإنسولين أو مقاومة الخلايا له.</p>
                
                <h3 style="color: var(--text-primary); margin: 1.5rem 0 0.5rem;">أنواع السكري</h3>
                <ul style="margin-right: 1.5rem;">
                    <li><strong>النوع الأول:</strong> يحدث عندما لا ينتج البنكرياس إنسولين (يعتمد على الإنسولين الخارجي)</li>
                    <li><strong>النوع الثاني:</strong> يحدث عندما لا يستخدم الجسم الإنسولين بشكل صحيح (الأكثر شيوعاً - 90% من الحالات)</li>
                    <li><strong>سكري الحمل:</strong> يحدث أثناء الحصول وعادة ما يختفي بعد الولادة</li>
                </ul>

                <h3 style="color: var(--text-primary); margin: 1.5rem 0 0.5rem;">الأهداف العلاجية</h3>
                <ul style="margin-right: 1.5rem;">
                    <li>مستوى السكر الصيام: 80-130 mg/dL</li>
                    <li>مستوى السكر بعد الأكل: أقل من 180 mg/dL</li>
                    <li>HbA1c: أقل من 7%</li>
                </ul>

                <h3 style="color: var(--text-primary); margin: 1.5rem 0 0.5rem;">نصائح يومية</h3>
                <ul style="margin-right: 1.5rem;">
                    <li>فحص السكر 4 مرات يومياً (قبل الوجبات وقبل النوم)</li>
                    <li>تناول وجبات منتظمة كل 3-4 ساعات</li>
                    <li>ممارسة الرياضة 30 دقيقة يومياً</li>
                    <li>شرب 8 أكواب ماء يومياً</li>
                    <li>فحص القدم يومياً</li>
                    <li>أخذ الأدوية في مواعيدها</li>
                </ul>
            </div>
        </div>
    </div>

    <script>
        // Set today's date
        document.getElementById('measureDate').valueAsDate = new Date();

        // Navigation active state
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', function() {
                document.querySelectorAll('.nav-links a').forEach(l => l.classList.remove('active'));
                this.classList.add('active');
            });
        });

        // Blood Sugar Tracker
        function checkSugar() {
            const level = parseFloat(document.getElementById('sugarLevel').value);
            const time = document.getElementById('measureTime').value;
            const resultDiv = document.getElementById('trackerResult');
            const valueDiv = document.getElementById('resultValue');
            const messageDiv = document.getElementById('resultMessage');
            const adviceDiv = document.getElementById('resultAdvice');
            const iconDiv = document.getElementById('resultIcon');

            if (!level || level < 30 || level > 600) {
                alert('الرجاء إدخال مستوى سكر صحيح (30-600)');
                return;
            }

            let status = '';
            let message = '';
            let advice = '';
            let icon = '';
            let colorClass = '';

            if (time === 'fasting') {
                if (level < 70) {
                    status = 'منخفض';
                    colorClass = 'danger';
                    icon = '⚠️';
                    message = 'مستوى السكر منخفض - يحتاج تدخل فوري';
                    advice = 'تناول 15 جرام من الكربوهيدرات السريعة (عصير، سكر، حلوى) وانتظر 15 دقيقة ثم أعد القياس. إذا استمر الانخفاض اتصل بالطبيب.';
                } else if (level >= 70 && level <= 130) {
                    status = 'طبيعي';
                    colorClass = 'normal';
                    icon = '✅';
                    message = 'مستوى السكر في المعدل الطبيعي - أحسنت!';
                    advice = 'استمر على نظامك الغذائي والرياضة الحالية. تذكر فحص HbA1c كل 3 شهور.';
                } else if (level > 130 && level <= 180) {
                    status = 'مرتفع قليلاً';
                    colorClass = 'warning';
                    icon = '⚡';
                    message = 'مستوى السكر أعلى من المطلوب';
                    advice = 'راجع نظامك الغذائي وقلل الكربوهيدرات في الوجبة القادمة. مارس رياضة خفيفة واشرب ماء.';
                } else {
                    status = 'مرتفع جداً';
                    colorClass = 'danger';
                    icon = '🚨';
                    message = 'مستوى السكر مرتفع جداً - خطر!';
                    advice = 'اشرب ماء كثيراً. إذا كنت تشعر بغثيان أو قيء أو صعوبة في التنفس، اتصل بالطوارئ فوراً (قد يكون DKA).';
                }
            } else if (time === 'after') {
                if (level < 70) {
                    status = 'منخفض';
                    colorClass = 'danger';
                    icon = '⚠️';
                    message = 'مستوى السكر منخفض بعد الأكل';
                    advice = 'تناول وجبة خفيفة تحتوي على كربوهيدرات وبروتين. راجع جرعة الأنسولين مع طبيبك.';
                } else if (level <= 180) {
                    status = 'طبيعي';
                    colorClass = 'normal';
                    icon = '✅';
                    message = 'مستوى السكر طبيعي بعد الأكل';
                    advice = 'ممتاز! استمر على نفس النظام الغذائي والأدوية.';
                } else {
                    status = 'مرتفع';
                    colorClass = 'warning';
                    icon = '⚡';
                    message = 'مستوى السكر مرتفع بعد الأكل';
                    advice = 'قلل من كمية الكربوهيدرات في الوجبات القادمة. راجع جرعة الأنسولين مع طبيبك.';
                }
            } else {
                if (level < 70) {
                    status = 'منخفض';
                    colorClass = 'danger';
                    icon = '⚠️';
                    message = 'مستوى السكر منخفض';
                   
