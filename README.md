<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Yash Surana - Frontend Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0a0a0a 0%, #1a1a2e 50%, #16213e 100%);
            color: #ffffff;
            overflow-x: hidden;
            line-height: 1.6;
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
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

        .bg-animation::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(56, 189, 248, 0.05) 0%, transparent 70%);
            animation: rotate 30s linear infinite;
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        /* Floating particles */
        .particle {
            position: absolute;
            border-radius: 50%;
            background: rgba(56, 189, 248, 0.3);
            animation: float 6s ease-in-out infinite;
        }

        .particle:nth-child(1) { width: 4px; height: 4px; top: 20%; left: 10%; animation-delay: 0s; }
        .particle:nth-child(2) { width: 6px; height: 6px; top: 60%; left: 80%; animation-delay: 1s; }
        .particle:nth-child(3) { width: 3px; height: 3px; top: 40%; left: 60%; animation-delay: 2s; }
        .particle:nth-child(4) { width: 5px; height: 5px; top: 80%; left: 30%; animation-delay: 3s; }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); opacity: 1; }
            50% { transform: translateY(-20px) rotate(180deg); opacity: 0.5; }
        }

        /* Header Section */
        .header {
            text-align: center;
            padding: 80px 0 60px;
            position: relative;
        }

        .profile-container {
            position: relative;
            display: inline-block;
            margin-bottom: 30px;
        }

        .profile-img {
            width: 140px;
            height: 140px;
            border-radius: 50%;
            background: linear-gradient(45deg, #38bdf8, #8b5cf6, #f59e0b);
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto;
            position: relative;
            animation: profilePulse 3s ease-in-out infinite;
            box-shadow: 0 0 50px rgba(56, 189, 248, 0.3);
        }

        .profile-img::before {
            content: '👋';
            font-size: 60px;
            animation: wave 2s ease-in-out infinite;
        }

        @keyframes profilePulse {
            0%, 100% { transform: scale(1); box-shadow: 0 0 50px rgba(56, 189, 248, 0.3); }
            50% { transform: scale(1.05); box-shadow: 0 0 80px rgba(56, 189, 248, 0.5); }
        }

        @keyframes wave {
            0%, 50%, 100% { transform: rotate(0deg); }
            25% { transform: rotate(20deg); }
            75% { transform: rotate(-10deg); }
        }

        .title {
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 20px;
            background: linear-gradient(45deg, #38bdf8, #8b5cf6, #f59e0b);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: titleGlow 2s ease-in-out infinite alternate;
        }

        @keyframes titleGlow {
            from { filter: brightness(1); }
            to { filter: brightness(1.2); }
        }

        .subtitle {
            font-size: 1.5rem;
            color: #94a3b8;
            margin-bottom: 30px;
            animation: fadeInUp 1s ease-out 0.5s both;
        }

        .profile-stats {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-bottom: 40px;
            animation: fadeInUp 1s ease-out 1s both;
        }

        .stat-item {
            background: rgba(255, 255, 255, 0.05);
            padding: 15px 25px;
            border-radius: 15px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.3s ease;
        }

        .stat-item:hover {
            transform: translateY(-5px);
            background: rgba(56, 189, 248, 0.1);
            border-color: rgba(56, 189, 248, 0.3);
        }

        .stat-number {
            font-size: 1.5rem;
            font-weight: bold;
            color: #38bdf8;
            display: block;
        }

        .stat-label {
            font-size: 0.9rem;
            color: #94a3b8;
        }

        /* About Section */
        .about-section {
            padding: 60px 0;
            animation: fadeInUp 1s ease-out 1.5s both;
        }

        .section-title {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 50px;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: linear-gradient(45deg, #38bdf8, #8b5cf6);
            border-radius: 2px;
        }

        .about-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-bottom: 50px;
        }

        .about-card {
            background: rgba(255, 255, 255, 0.05);
            padding: 30px;
            border-radius: 20px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .about-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(56, 189, 248, 0.1), transparent);
            transition: left 0.5s;
        }

        .about-card:hover::before {
            left: 100%;
        }

        .about-card:hover {
            transform: translateY(-10px);
            border-color: rgba(56, 189, 248, 0.3);
            box-shadow: 0 20px 40px rgba(56, 189, 248, 0.1);
        }

        .about-item {
            display: flex;
            align-items: flex-start;
            margin-bottom: 15px;
            position: relative;
            z-index: 1;
        }

        .about-icon {
            margin-right: 15px;
            font-size: 1.2rem;
        }

        /* Skills Section */
        .skills-section {
            padding: 60px 0;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
            gap: 20px;
            margin-top: 40px;
        }

        .skill-item {
            background: rgba(255, 255, 255, 0.05);
            padding: 25px;
            border-radius: 15px;
            text-align: center;
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.1);
            position: relative;
            overflow: hidden;
        }

        .skill-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: linear-gradient(45deg, #38bdf8, #
