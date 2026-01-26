<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Profile Header</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 20px;
        }

        .profile-container {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-radius: 24px;
            padding: 48px 40px;
            max-width: 600px;
            width: 100%;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
            text-align: center;
        }

        .profile-image {
            width: 180px;
            height: 180px;
            margin: 0 auto 32px;
            animation: fadeInDown 0.8s ease-out;
        }

        .profile-image img {
            width: 100%;
            height: 100%;
            object-fit: contain;
        }

        h2 {
            color: #2d3748;
            font-size: 32px;
            font-weight: 700;
            margin-bottom: 32px;
            animation: fadeIn 1s ease-out 0.2s both;
        }

        .social-links {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 24px;
            flex-wrap: wrap;
            animation: fadeInUp 1s ease-out 0.4s both;
        }

        .social-link {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 56px;
            height: 56px;
            border-radius: 50%;
            background: white;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            position: relative;
            overflow: hidden;
        }

        .social-link::before {
            content: '';
            position: absolute;
            inset: 0;
            border-radius: 50%;
            background: linear-gradient(135deg, rgba(255,255,255,0.3) 0%, rgba(255,255,255,0) 100%);
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .social-link:hover {
            transform: translateY(-4px) scale(1.05);
            box-shadow: 0 8px 24px rgba(0, 0, 0, 0.15);
        }

        .social-link:hover::before {
            opacity: 1;
        }

        .social-link:active {
            transform: translateY(-2px) scale(1.02);
        }

        .social-link svg,
        .social-link img {
            width: 32px;
            height: 32px;
            position: relative;
            z-index: 1;
        }

        .social-link[data-platform="portfolio"] {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }

        .social-link[data-platform="portfolio"] svg {
            color: white;
        }

        .social-link[data-platform="gmail"]:hover {
            background: linear-gradient(135deg, #EA4335 0%, #C5221F 100%);
        }

        .social-link[data-platform="outlook"]:hover {
            background: linear-gradient(135deg, #0078D4 0%, #005A9E 100%);
        }

        .social-link[data-platform="linkedin"]:hover {
            background: linear-gradient(135deg, #0A66C2 0%, #004182 100%);
        }

        .social-link[data-platform="instagram"]:hover {
            background: linear-gradient(135deg, #F56040 0%, #E1306C 50%, #C13584 100%);
        }

        /* Tooltip */
        .social-link::after {
            content: attr(aria-label);
            position: absolute;
            bottom: -40px;
            left: 50%;
            transform: translateX(-50%);
            background: #2d3748;
            color: white;
            padding: 8px 12px;
            border-radius: 8px;
            font-size: 12px;
            font-weight: 500;
            white-space: nowrap;
            opacity: 0;
            pointer-events: none;
            transition: all 0.3s ease;
            z-index: 10;
        }

        .social-link:hover::after {
            opacity: 1;
            bottom: -48px;
        }

        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @media (max-width: 480px) {
            .profile-container {
                padding: 32px 24px;
            }

            h2 {
                font-size: 28px;
            }

            .social-links {
                gap: 16px;
            }

            .social-link {
                width: 48px;
                height: 48px;
            }

            .social-link svg,
            .social-link img {
                width: 28px;
                height: 28px;
            }
        }
    </style>
</head>
<body>
    <div class="profile-container">
        <div class="profile-image">
            <img src="assets/index.svg" alt="Welcome" />
        </div>

        <h2>Connect</h2>

        <nav class="social-links" role="navigation" aria-label="Social media links">
            <a href="https://ptanmay143.github.io"
               target="_blank"
               rel="noopener noreferrer"
               class="social-link"
               data-platform="portfolio"
               aria-label="Portfolio">
                <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                    <rect x="2" y="3" width="20" height="18" rx="4" stroke="currentColor" stroke-width="1.8"/>
                    <path d="M8 9h8M8 13h5" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"/>
                </svg>
            </a>

            <a href="mailto:ptanmay143@gmail.com"
               class="social-link"
               data-platform="gmail"
               aria-label="Gmail">
                <img src="https://cdn.simpleicons.org/gmail/D14836" alt="" />
            </a>

            <a href="mailto:ptanmay143@outlook.com"
               class="social-link"
               data-platform="outlook"
               aria-label="Outlook">
                <img src="https://cdn.simpleicons.org/microsoftoutlook/0078D4" alt="" />
            </a>

            <a href="https://www.linkedin.com/in/ptanmay143/"
               target="_blank"
               rel="noopener noreferrer"
               class="social-link"
               data-platform="linkedin"
               aria-label="LinkedIn">
                <img src="https://cdn.simpleicons.org/linkedin/0A66C2" alt="" />
            </a>

            <a href="https://www.instagram.com/ptanmay143/"
               target="_blank"
               rel="noopener noreferrer"
               class="social-link"
               data-platform="instagram"
               aria-label="Instagram">
                <img src="https://cdn.simpleicons.org/instagram/E4405F" alt="" />
            </a>
        </nav>
    </div>
</body>
</html>