# Rique.github.io
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Henrique Perez - Portfólio Pessoal</title>
    <style>
        /* =================== VARIÁVEIS DE COR E TIPOGRAFIA =================== */
        :root {
            /* Cores principais - Paleta de seriedade, confiabilidade e inovação */
            --primary-color: #2563eb;
            --primary-dark: #1d4ed8;
            --secondary-color: #64748b;
            --accent-color: #06b6d4;
            --background-color: #f8fafc;
            --surface-color: #ffffff;
            --text-primary: #1e293b;
            --text-secondary: #64748b;
            --text-light: #94a3b8;
            --border-color: #e2e8f0;
            
            /* Gradientes */
            --gradient-primary: linear-gradient(135deg, var(--primary-color), var(--accent-color));
            --gradient-dark: linear-gradient(135deg, #1e293b, #334155);
            
            /* Tipografia */
            --font-primary: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
            --font-secondary: 'Space Grotesk', sans-serif;
            
            /* Tamanhos de fonte */
            --text-xs: 0.75rem;
            --text-sm: 0.875rem;
            --text-base: 1rem;
            --text-lg: 1.125rem;
            --text-xl: 1.25rem;
            --text-2xl: 1.5rem;
            --text-3xl: 1.875rem;
            --text-4xl: 2.25rem;
            
            /* Espaçamentos */
            --spacing-xs: 0.5rem;
            --spacing-sm: 0.75rem;
            --spacing-md: 1rem;
            --spacing-lg: 1.5rem;
            --spacing-xl: 2rem;
            --spacing-2xl: 3rem;
            
            /* Sombras */
            --shadow-sm: 0 1px 2px 0 rgba(0, 0, 0, 0.05);
            --shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
            --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
            --shadow-xl: 0 20px 25px -5px rgba(0, 0, 0, 0.1);
            
            /* Bordas */
            --border-radius-sm: 0.375rem;
            --border-radius-md: 0.5rem;
            --border-radius-lg: 0.75rem;
            --border-radius-xl: 1rem;
        }

        /* =================== RESET E BASE =================== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: var(--font-primary);
            font-size: var(--text-base);
            line-height: 1.6;
            color: var(--text-primary);
            background-color: var(--background-color);
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 var(--spacing-lg);
        }

        /* =================== HEADER E NAVEGAÇÃO =================== */
        .header {
            background-color: var(--surface-color);
            box-shadow: var(--shadow-sm);
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            z-index: 1000;
            transition: all 0.3s ease;
        }

        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: var(--spacing-md) var(--spacing-lg);
            max-width: 1200px;
            margin: 0 auto;
        }

        .nav-brand h1 {
            font-size: var(--text-2xl);
            font-weight: 700;
            color: var(--primary-color);
            font-family: var(--font-secondary);
        }

        .nav-subtitle {
            font-size: var(--text-sm);
            color: var(--text-secondary);
            margin-left: var(--spacing-xs);
        }

        .nav-list {
            display: flex;
            list-style: none;
            gap: var(--spacing-xl);
        }

        .nav-link {
            text-decoration: none;
            color: var(--text-secondary);
            font-weight: 500;
            font-size: var(--text-sm);
            padding: var(--spacing-xs) var(--spacing-md);
            border-radius: var(--border-radius-md);
            transition: all 0.3s ease;
            position: relative;
            cursor: pointer;
        }

        .nav-link:hover,
        .nav-link.active {
            color: var(--primary-color);
        }

        .nav-link::after {
            content: '';
            position: absolute;
            bottom: -2px;
            left: 50%;
            transform: translateX(-50%);
            width: 0;
            height: 2px;
            background: var(--gradient-primary);
            transition: width 0.3s ease;
        }

        .nav-link:hover::after,
        .nav-link.active::after {
            width: 100%;
        }

        .nav-toggle {
            display: none;
            flex-direction: column;
            cursor: pointer;
        }

        .bar {
            width: 25px;
            height: 2px;
            background-color: var(--text-primary);
            margin: 3px 0;
            transition: 0.3s;
        }

        /* =================== CONTEÚDO DAS PÁGINAS =================== */
        .page {
            display: none;
            margin-top: 80px;
            min-height: calc(100vh - 160px);
        }

        .page.active {
            display: block;
        }

        .page-banner {
            background: var(--gradient-primary);
            padding: var(--spacing-2xl) 0;
            color: white;
            text-align: center;
        }

        .page-title {
            font-size: var(--text-4xl);
            font-weight: 700;
            margin-bottom: var(--spacing-md);
            font-family: var(--font-secondary);
        }

        .page-subtitle {
            font-size: var(--text-lg);
            opacity: 0.9;
        }

        .content-section {
            padding: var(--spacing-2xl) 0;
        }

        .content-section:nth-child(even) {
            background-color: var(--surface-color);
        }

        .section-header {
            text-align: center;
            margin-bottom: var(--spacing-2xl);
        }

        .section-title {
            font-size: var(--text-3xl);
            font-weight: 700;
            color: var(--text-primary);
            margin-bottom: var(--spacing-md);
            font-family: var(--font-secondary);
        }

        /* =================== HOME PAGE =================== */
        .hero {
            padding: calc(80px + var(--spacing-2xl)) 0 var(--spacing-2xl);
            background: var(--gradient-primary);
            color: white;
        }

        .hero-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: var(--spacing-2xl);
            align-items: center;
        }

        .hero-title {
            font-size: var(--text-4xl);
            font-weight: 700;
            margin-bottom: var(--spacing-lg);
            font-family: var(--font-secondary);
        }

        .highlight {
            color: var(--accent-color);
            font-weight: 800;
        }

        .hero-description {
            font-size: var(--text-lg);
            margin-bottom: var(--spacing-xl);
            opacity: 0.9;
        }

        .hero-buttons {
            display: flex;
            gap: var(--spacing-lg);
            margin-top: var(--spacing-xl);
        }

        .btn {
            display: inline-flex;
            align-items: center;
            padding: var(--spacing-sm) var(--spacing-lg);
            border-radius: var(--border-radius-md);
            text-decoration: none;
            font-weight: 600;
            font-size: var(--text-sm);
            transition: all 0.3s ease;
            cursor: pointer;
            border: none;
        }

        .btn-primary {
            background-color: var(--surface-color);
            color: var(--primary-color);
            box-shadow: var(--shadow-md);
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: var(--shadow-lg);
        }

        .btn-secondary {
            background-color: transparent;
            color: white;
            border: 2px solid rgba(255, 255, 255, 0.3);
        }

        .btn-secondary:hover {
            background-color: rgba(255, 255, 255, 0.1);
            border-color: white;
        }

        .hero-image {
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .avatar-circle {
            width: 200px;
            height: 200px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: var(--text-4xl);
            font-weight: 700;
            color: white;
            border: 4px solid rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(10px);
        }

        .highlights {
            padding: var(--spacing-2xl) 0;
            background-color: var(--surface-color);
        }

        .highlights-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: var(--spacing-xl);
            margin-top: var(--spacing-xl);
        }

        .highlight-card {
            background-color: var(--background-color);
            padding: var(--spacing-xl);
            border-radius: var(--border-radius-lg);
            text-align: center;
            transition: all 0.3s ease;
            border: 1px solid var(--border-color);
        }

        .highlight-card:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow-lg);
        }

        .card-icon {
            font-size: var(--text-4xl);
            margin-bottom: var(--spacing-lg);
        }

        .highlight-card h4 {
            font-size: var(--text-xl);
            font-weight: 600;
            margin-bottom: var(--spacing-sm);
            color: var(--primary-color);
        }

        .highlight-card p {
            color: var(--text-secondary);
            font-size: var(--text-sm);
        }

        /* =================== IDENTIFICAÇÃO PAGE =================== */
        .info-card {
            background: var(--surface-color);
            padding: var(--spacing-xl);
            border-radius: var(--border-radius-lg);
            box-shadow: var(--shadow-sm);
            border: 1px solid var(--border-color);
        }

        .card-header {
            display: flex;
            align-items: center;
            gap: var(--spacing-md);
            margin-bottom: var(--spacing-lg);
        }

        .card-header h3 {
            font-size: var(--text-xl);
            font-weight: 600;
            color: var(--primary-color);
        }

        .info-list {
            display: flex;
            flex-direction: column;
            gap: var(--spacing-md);
        }

        .info-item {
            display: flex;
            justify-content: space-between;
            padding: var(--spacing-sm) 0;
            border-bottom: 1px solid var(--border-color);
        }

        .info-item:last-child {
            border-bottom: none;
        }

        .info-label {
            font-weight: 600;
            color: var(--text-secondary);
        }

        .info-value {
            color: var(--text-primary);
            font-weight: 500;
        }

        .timeline {
            max-width: 800px;
            margin: 0 auto;
        }

        .timeline-item {
            position: relative;
            padding-left: var(--spacing-2xl);
            margin-bottom: var(--spacing-2xl);
        }

        .timeline-marker {
            position: absolute;
            left: 0;
            top: 0;
            width: 16px;
            height: 16px;
            background: var(--primary-color);
            border-radius: 50%;
            border: 4px solid white;
            box-shadow: 0 0 0 4px var(--primary-color);
        }

        .timeline-item::before {
            content: '';
            position: absolute;
            left: 7px;
            top: 20px;
            bottom: -20px;
            width: 2px;
            background: var(--border-color);
        }

        .timeline-item:last-child::before {
            display: none;
        }

        .timeline-content {
            background: var(--surface-color);
            padding: var(--spacing-lg);
            border-radius: var(--border-radius-lg);
            box-shadow: var(--shadow-sm);
        }

        .timeline-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: var(--spacing-sm);
        }

        .timeline-header h3 {
            font-size: var(--text-lg);
            font-weight: 600;
            color: var(--primary-color);
        }

        .timeline-date {
            font-size: var(--text-sm);
            color: var(--text-secondary);
            font-weight: 500;
        }

        .timeline-institution {
            font-weight: 600;
            color: var(--text-secondary);
            margin-bottom: var(--spacing-sm);
        }

        .timeline-description {
            color: var(--text-primary);
            margin-bottom: var(--spacing-md);
        }

        .status-badge {
            padding: var(--spacing-xs) var(--spacing-sm);
            border-radius: var(--border-radius-sm);
            font-size: var(--text-xs);
            font-weight: 600;
            text-transform: uppercase;
        }

        .status-badge.current {
            background: #dcfce7;
            color: #166534;
        }

        .status-badge.past {
            background: #f1f5f9;
            color: var(--text-secondary);
        }

        .goals-container {
            max-width: 900px;
            margin: 0 auto;
        }

        .primary-goal {
            margin-bottom: var(--spacing-2xl);
        }

        .goal-card {
            background: var(--surface-color);
            padding: var(--spacing-xl);
            border-radius: var(--border-radius-lg);
            box-shadow: var(--shadow-sm);
            text-align: center;
        }

        .goal-card.primary-goal {
            background: var(--gradient-primary);
            color: white;
            box-shadow: var(--shadow-lg);
        }

        .goal-header {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: var(--spacing-sm);
            margin-bottom: var(--spacing-lg);
        }

        .goal-icon {
            font-size: var(--text-4xl);
        }

        .goals-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: var(--spacing-lg);
        }

        .personal-quote {
            max-width: 800px;
            margin: 0 auto;
            text-align: center;
            font-size: var(--text-lg);
            font-style: italic;
            color: var(--text-secondary);
            padding: var(--spacing-2xl);
            background: var(--surface-color);
            border-radius: var(--border-radius-lg);
            box-shadow: var(--shadow-sm);
        }

        .personal-quote cite {
            display: block;
            margin-top: var(--spacing-lg);
            font-size: var(--text-base);
            font-weight: 600;
            color: var(--primary-color);
        }

        /* =================== INTERESSES PAGE =================== */
        .featured-interest {
            background: var(--gradient-primary);
            color: white;
            padding: var(--spacing-2xl);
            border-radius: var(--border-radius-xl);
            margin-bottom: var(--spacing-2xl);
        }

        .featured-content {
            display: flex;
            align-items: center;
            gap: var(--spacing-xl);
            max-width: 800px;
            margin: 0 auto;
        }

        .featured-icon {
            font-size: 4rem;
            flex-shrink: 0;
        }

        .reasons-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: var(--spacing-xl);
        }

        .reason-card {
            background: var(--surface-color);
            padding: var(--spacing-xl);
            border-radius: var(--border-radius-lg);
            box-shadow: var(--shadow-sm);
            text-align: center;
        }

        .reason-icon {
            font-size: var(--text-4xl);
            margin-bottom: var(--spacing-lg);
        }

        .specializations {
            max-width: 900px;
            margin: 0 auto;
        }

        .spec-category {
            margin-bottom: var(--spacing-xl);
        }

        .spec-category h3 {
            font-size: var(--text-xl);
            font-weight: 600;
            color: var(--primary-color);
            margin-bottom: var(--spacing-md);
        }

        .spec-items {
            display: flex;
            flex-wrap: wrap;
            gap: var(--spacing-sm);
        }

        .spec-tag {
            background: var(--background-color);
            color: var(--text-primary);
            padding: var(--spacing-xs) var(--spacing-md);
            border-radius: var(--border-radius-md);
            font-size: var(--text-sm);
            font-weight: 500;
            border: 1px solid var(--border-color);
        }

        .sectors-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: var(--spacing-lg);
        }

        .sector-card {
            background: var(--surface-color);
            padding: var(--spacing-lg);
            border-radius: var(--border-radius-lg);
            text-align: center;
            border: 1px solid var(--border-color);
            transition: all 0.3s ease;
        }

        .sector-card:hover {
            transform: translateY(-2px);
            box-shadow: var(--shadow-md);
        }

        .sector-icon {
            font-size: var(--text-3xl);
            margin-bottom: var(--spacing-md);
        }

        .complementary-interests {
            max-width: 800px;
            margin: 0 auto;
        }

        .interest-item {
            display: flex;
            gap: var(--spacing-lg);
            align-items: flex-start;
            background: var(--surface-color);
            padding: var(--spacing-xl);
            border-radius: var(--border-radius-lg);
            margin-bottom: var(--spacing-lg);
            box-shadow: var(--shadow-sm);
        }

        .interest-icon {
            font-size: var(--text-3xl);
            flex-shrink: 0;
        }

        /* =================== PROJETOS PAGE =================== */
        .project-highlight {
            background: var(--surface-color);
            border-radius: var(--border-radius-xl);
            padding: var(--spacing-2xl);
            box-shadow: var(--shadow-lg);
            margin-bottom: var(--spacing-2xl);
            border: 1px solid var(--border-color);
        }

        .project-header {
            display: flex;
            align-items: center;
            gap: var(--spacing-lg);
            margin-bottom: var(--spacing-lg);
        }

        .project-icon {
            font-size: var(--text-4xl);
            flex-shrink: 0;
        }

        .project-info h3 {
            font-size: var(--text-2xl);
            font-weight: 700;
            color: var(--primary-color);
            margin-bottom: var(--spacing-xs);
        }

        .project-institution {
            font-size: var(--text-lg);
            color: var(--text-secondary);
            font-weight: 500;
        }

        .project-status {
            display: inline-block;
            margin-top: var(--spacing-xs);
            padding: var(--spacing-xs) var(--spacing-sm);
            background: #dcfce7;
            color: #166534;
            border-radius: var(--border-radius-sm);
            font-size: var(--text-sm);
            font-weight: 600;
        }

        .project-description p {
            font-size: var(--text-lg);
            line-height: 1.7;
            color: var(--text-primary);
            margin-bottom: var(--spacing-lg);
        }

        .project-skills h4 {
            font-size: var(--text-lg);
            font-weight: 600;
            color: var(--text-primary);
            margin-bottom: var(--spacing-md);
        }

        .skills-tags {
            display: flex;
            flex-wrap: wrap;
            gap: var(--spacing-sm);
        }

        .skill-tag {
            background: var(--primary-color);
            color: white;
            padding: var(--spacing-xs) var(--spacing-md);
            border-radius: var(--border-radius-md);
            font-size: var(--text-sm);
            font-weight: 500;
        }

        .experience-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
            gap: var(--spacing-xl);
        }

        .experience-card {
            background: var(--surface-color);
            padding: var(--spacing-xl);
            border-radius: var(--border-radius-lg);
            box-shadow: var(--shadow-sm);
        }

        .exp-header {
            display: flex;
            align-items: center;
            gap: var(--spacing-md);
            margin-bottom: var(--spacing-lg);
        }

        .exp-icon {
            font-size: var(--text-3xl);
        }

        .exp-header h3 {
            font-size: var(--text-xl);
            font-weight: 600;
            color: var(--primary-color);
        }

        .exp-learnings h4 {
            font-size: var(--text-base);
            font-weight: 600;
            color: var(--text-primary);
            margin: var(--spacing-lg) 0 var(--spacing-sm);
        }

        .exp-learnings ul {
            list-style: none;
            padding-left: 0;
        }

        .exp-learnings li {
            position: relative;
            padding-left: var(--spacing-lg);
            margin-bottom: var(--spacing-xs);
            color: var(--text-secondary);
        }

        .exp-learnings li::before {
            content: "→";
            position: absolute;
            left: 0;
            color: var(--primary-color);
            font-weight: 600;
        }

        .social-project-highlight {
            background: var(--gradient-dark);
            color: white;
            border-radius: var(--border-radius-xl);
            padding: var(--spacing-2xl);
            margin-bottom: var(--spacing-2xl);
        }

        .social-header {
            display: flex;
            align-items: center;
            gap: var(--spacing-lg);
            margin-bottom: var(--spacing-lg);
        }

        .social-icon {
            font-size: var(--text-4xl);
        }

        .social-info h3 {
            font-size: var(--text-2xl);
            font-weight: 700;
            margin-bottom: var(--spacing-xs);
        }

        .social-org, .social-role {
            display: block;
            font-size: var(--text-base);
            opacity: 0.8;
        }

        .leadership-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: var(--spacing-lg);
            margin-top: var(--spacing-lg);
        }

        .leadership-item {
            text-align: center;
        }

        .leadership-icon {
            font-size: var(--text-3xl);
            margin-bottom: var(--spacing-sm);
        }

        .leadership-item h4 {
            font-size: var(--text-base);
            font-weight: 600;
            margin-bottom: var(--spacing-xs);
        }

        .leadership-item p {
            font-size: var(--text-sm);
            opacity: 0.8;
        }

        .impact-metrics {
            margin-top: var(--spacing-xl);
        }

        .impact-metrics h4 {
            font-size: var(--text-lg);
            font-weight: 600;
            margin-bottom: var(--spacing-lg);
        }

        .metrics-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: var(--spacing-lg);
        }

        .metric-item {
            display: flex;
            align-items: flex-start;
            gap: var(--spacing-md);
        }

        .metric-icon {
            font-size: var(--text-2xl);
            flex-shrink: 0;
        }

        .metric-content h5 {
            font-size: var(--text-base);
            font-weight: 600;
            margin-bottom: var(--spacing-xs);
        }

        .metric-content p {
            font-size: var(--text-sm);
            opacity: 0.8;
        }

        /* =================== CONTATO PAGE =================== */
        .contact-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: var(--spacing-xl);
            margin-top: var(--spacing-xl);
        }

        .contact-card {
            background: var(--surface-color);
            padding: var(--spacing-xl);
            border-radius: var(--border-radius-lg);
            box-shadow: var(--shadow-sm);
            text-align: center;
            transition: all 0.3s ease;
        }

        .contact-card:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow-lg);
        }

        .contact-icon {
            font-size: var(--text-4xl);
            margin-bottom: var(--spacing-lg);
            color: var(--primary-color);
        }

        .contact-info h3 {
            font-size: var(--text-xl);
            font-weight: 600;
            margin-bottom: var(--spacing-md);
            color: var(--primary-color);
        }

        .contact-detail {
            font-size: var(--text-lg);
            color: var(--text-secondary);
            margin-bottom: var(--spacing-sm);
        }

        .contact-link {
            color: var(--primary-color);
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .contact-link:hover {
            color: var(--primary-dark);
            text-decoration: underline;
        }

        /* =================== FOOTER =================== */
        .footer {
            background-color: var(--text-primary);
            color: var(--text-light);
            text-align: center;
            padding: var(--spacing-xl) 0;
        }

        .footer p {
            font-size: var(--text-sm);
        }

        /* =================== RESPONSIVIDADE =================== */
        @media (max-width: 768px) {
            .nav-menu {
                position: fixed;
                left: -100%;
                top: 70px;
                flex-direction: column;
                background-color: var(--surface-color);
                width: 100%;
                text-align: center;
                transition: 0.3s;
                box-shadow: var(--shadow-lg);
            }

            .nav-menu.active {
                left: 0;
            }

            .nav-list {
                flex-direction: column;
                padding: var(--spacing-lg) 0;
            }

            .nav-toggle {
                display: flex;
            }

            .hero-content {
                grid-template-columns: 1fr;
                text-align: center;
            }

            .featured-content {
                flex-direction: column;
                text-align: center;
            }

            .hero-title, .page-title {
                font-size: var(--text-3xl);
            }

            .hero-buttons {
                flex-direction: column;
                align-items: center;
            }

            .container {
                padding: 0 var(--spacing-md);
            }

            .experience-grid {
                grid-template-columns: 1fr;
            }

            .project-header {
                flex-direction: column;
                text-align: center;
            }

            .social-header {
                flex-direction: column;
                text-align: center;
            }

            .interest-item {
                flex-direction: column;
                text-align: center;
            }

            .timeline-header {
                flex-direction: column;
                align-items: flex-start;
            }

            .contact-grid {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 480px) {
            .hero-title, .page-title {
                font-size: var(--text-2xl);
            }

            .highlights-grid, .reasons-grid, .sectors-grid {
                grid-template-columns: 1fr;
            }

            .avatar-circle {
                width: 150px;
                height: 150px;
                font-size: var(--text-3xl);
            }

            .goals-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Header com navegação -->
    <header class="header">
        <nav class="navbar">
            <div class="nav-brand">
                <h1>Henrique Perez</h1>
                <span class="nav-subtitle">Data Science & AI Student</span>
            </div>
            <div class="nav-menu" id="nav-menu">
                <ul class="nav-list">
                    <li><a href="#" class="nav-link active" data-page="home">Home</a></li>
                    <li><a href="#" class="nav-link" data-page="identificacao">Identificação</a></li>
                    <li><a href="#" class="nav-link" data-page="interesses">Interesses</a></li>
                    <li><a href="#" class="nav-link" data-page="projetos">Projetos</a></li>
                    <li><a href="#" class="nav-link" data-page="contato">Contato</a></li>
                </ul>
            </div>
            <div class="nav-toggle" id="nav-toggle">
                <span class="bar"></span>
                <span class="bar"></span>
                <span class="bar"></span>
            </div>
        </nav>
    </header>

    <!-- HOME PAGE -->
    <div id="home" class="page active">
        <section class="hero">
            <div class="container">
                <div class="hero-content">
                    <div class="hero-text">
                        <h2 class="hero-title">Olá, eu sou <span class="highlight">Henrique Perez</span></h2>
                        <p class="hero-description">
                            Estudante de Ciência de Dados e Inteligência Artificial, apaixonado por tecnologia e inovação. 
                            Transformando dados em insights valiosos para o futuro.
                        </p>
                        <div class="hero-buttons">
                            <a href="#" class="btn btn-primary" data-page="identificacao">Conheça mais</a>
                            <a href="#" class="btn btn-secondary" data-page="projetos">Ver Projetos</a>
                        </div>
                    </div>
                    <div class="hero-image">
                        <div class="avatar-circle">
                            <span>HP</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section class="highlights">
            <div class="container">
                <h3 class="section-title">Destaques</h3>
                <div class="highlights-grid">
                    <div class="highlight-card">
                        <div class="card-icon">🎓</div>
                        <h4>Formação</h4>
                        <p>Ciência de Dados e IA no IBMEC Faria Lima</p>
                    </div>
                    <div class="highlight-card">
                        <div class="card-icon">⚡</div>
                        <h4>Experiência</h4>
                        <p>Liga acadêmica IBTech e liderança em grupos solidários</p>
                    </div>
                    <div class="highlight-card">
                        <div class="card-icon">🚀</div>
                        <h4>Objetivo</h4>
                        <p>Criar empresa de tecnologia e inovação</p>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- IDENTIFICAÇÃO PAGE -->
    <div id="identificacao" class="page">
        <section class="page-banner">
            <div class="container">
                <div class="banner-content">
                    <h1 class="page-title">Identificação</h1>
                    <p class="page-subtitle">Conheça mais sobre minha trajetória e objetivos</p>
                </div>
            </div>
        </section>

        <section class="content-section">
            <div class="container">
                <div class="section-header">
                    <h2 class="section-title">Dados Pessoais</h2>
                </div>
                <div class="info-card">
                    <div class="card-header">
                        <div class="card-icon">👤</div>
                        <h3>Informações Básicas</h3>
                    </div>
                    <div class="info-list">
                        <div class="info-item">
                            <span class="info-label">Nome:</span>
                            <span class="info-value">Henrique Perez</span>
                        </div>
                        <div class="info-item">
                            <span class="info-label">Idade:</span>
                            <span class="info-value">18 anos</span>
                        </div>
                        <div class="info-item">
                            <span class="info-label">Status:</span>
                            <span class="info-value">Estudante Universitário</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section class="content-section">
            <div class="container">
                <div class="section-header">
                    <h2 class="section-title">Formação Acadêmica</h2>
                </div>
                <div class="timeline">
                    <div class="timeline-item current">
                        <div class="timeline-marker"></div>
                        <div class="timeline-content">
                            <div class="timeline-header">
                                <h3>Ciência de Dados e Inteligência Artificial</h3>
                                <span class="timeline-date">2024 - 2028</span>
                            </div>
                            <p class="timeline-institution">IBMEC Faria Lima</p>
                            <p class="timeline-description">
                                Atualmente cursando o 2º semestre do curso de Ciência de Dados e Inteligência Artificial, 
                                focando em análise estatística, machine learning e desenvolvimento de soluções baseadas em dados.
                            </p>
                            <div class="timeline-status">
                                <span class="status-badge current">Em andamento</span>
                            </div>
                        </div>
                    </div>

                    <div class="timeline-item past">
                        <div class="timeline-marker"></div>
                        <div class="timeline-content">
                            <div class="timeline-header">
                                <h3>Experiência Acadêmica Prévia</h3>
                                <span class="timeline-date">Anterior a 2024</span>
                            </div>
                            <p class="timeline-institution">Universidade Mackenzie e Morumbi</p>
                            <p class="timeline-description">
                                Experiência acadêmica prévia que contribuiu para a formação de uma base sólida 
                                e para a escolha definitiva da área de Ciência de Dados.
                            </p>
                            <div class="timeline-status">
                                <span class="status-badge past">Concluído</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section class="content-section">
            <div class="container">
                <div class="section-header">
                    <h2 class="section-title">Metas e Objetivos</h2>
                </div>
                <div class="goals-container">
                    <div class="goal-card primary-goal">
                        <div class="goal-header">
                            <div class="goal-icon">🚀</div>
                            <h3>Objetivo Principal</h3>
                        </div>
                        <div class="goal-content">
                            <h4>Empresa de Tecnologia e Inovação</h4>
                            <p>
                                Minha meta principal é ser dono de uma empresa de tecnologia e inovação, 
                                onde possa aplicar conhecimentos de ciência de dados para resolver problemas 
                                complexos và gerar impacto positivo na sociedade.
                            </p>
                        </div>
                    </div>

                    <div class="goals-grid">
                        <div class="goal-card">
                            <div class="goal-icon">💼</div>
                            <h4>Carreira Profissional</h4>
                            <p>Desenvolver expertise em ciência de dados e inteligência artificial</p>
                        </div>
                        <div class="goal-card">
                            <div class="goal-icon">🌐</div>
                            <h4>Impacto Social</h4>
                            <p>Utilizar tecnologia para criar soluções que beneficiem a sociedade</p>
                        </div>
                        <div class="goal-card">
                            <div class="goal-icon">📈</div>
                            <h4>Inovação</h4>
                            <p>Estar na vanguarda das tecnologias emergentes</p>
                        </div>
                        <div class="goal-card">
                            <div class="goal-icon">🎯</div>
                            <h4>Liderança</h4>
                            <p>Liderar equipes e projetos transformadores</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section class="content-section">
            <div class="container">
                <div class="quote-section">
                    <blockquote class="personal-quote">
                        <p>
                            "Acredito no poder dos dados para transformar realidades e criar oportunidades. 
                            Minha jornada é construir pontes entre a tecnologia e as necessidades humanas, 
                            sempre com foco na inovação responsável."
                        </p>
                        <footer>
                            <cite>— Henrique Perez</cite>
                        </footer>
                    </blockquote>
                </div>
            </div>
        </section>
    </div>

    <!-- INTERESSES PAGE -->
    <div id="interesses" class="page">
        <section class="page-banner">
            <div class="container">
                <div class="banner-content">
                    <h1 class="page-title">Interesses Pessoais</h1>
                    <p class="page-subtitle">Descobrindo paixões e explorando possibilidades</p>
                </div>
            </div>
        </section>

        <section class="content-section">
            <div class="container">
                <div class="featured-interest">
                    <div class="featured-content">
                        <div class="featured-icon">📊</div>
                        <div class="featured-text">
                            <h2>Ciência de Dados</h2>
                            <h3>Minha Grande Paixão</h3>
                            <p>
                                Sou apaixonado pela área de dados principalmente pela sua versatilidade 
                                em atuar em qualquer setor. A capacidade de extrair insights valiosos, 
                                identificar padrões ocultos e transformar informações brutas em 
                                conhecimento estratégico me fascina profundamente.
                            </p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section class="content-section">
            <div class="container">
                <div class="section-header">
                    <h2 class="section-title">Por que Ciência de Dados?</h2>
                </div>
                <div class="reasons-grid">
                    <div class="reason-card">
                        <div class="reason-icon">🌐</div>
                        <h3>Versatilidade Universal</h3>
                        <p>
                            A ciência de dados pode ser aplicada em qualquer setor: saúde, finanças, 
                            educação, entretenimento, agricultura, e muito mais. Essa universalidade 
                            permite explorar diferentes áreas e sempre encontrar novos desafios.
                        </p>
                    </div>
                    <div class="reason-card">
                        <div class="reason-icon">🔍</div>
                        <h3>Descoberta de Padrões</h3>
                        <p>
                            A capacidade de encontrar padrões ocultos em grandes volumes de dados 
                            e transformar esses insights em soluções práticas é extremamente 
                            gratificante e impactante.
                        </p>
                    </div>
                    <div class="reason-card">
                        <div class="reason-icon">💡</div>
                        <h3>Inovação Constante</h3>
                        <p>
                            A área está em constante evolução, avec novas técnicas, ferramentas 
                            e metodologias surgindo regularmente, garantindo aprendizado contínuo 
                            e desafios estimulantes.
                        </p>
                    </div>
                    <div class="reason-card">
                        <div class="reason-icon">📈</div>
                        <h3>Impacto Mensurável</h3>
                        <p>
                            Os resultados da ciência de dados são tangíveis e mensuráveis, 
                            permitindo ver diretamente o impacto do trabalho realizado 
                            nas organizações e na sociedade.
                        </p>
                    </div>
                </div>
            </div>
        </section>

        <section class="content-section">
            <div class="container">
                <div class="section-header">
                    <h2 class="section-title">Áreas de Especialização</h2>
                </div>
                <div class="specializations">
                    <div class="spec-category">
                        <h3>Machine Learning & IA</h3>
                        <div class="spec-items">
                            <span class="spec-tag">Aprendizado Supervisionado</span>
                            <span class="spec-tag">Redes Neurais</span>
                            <span class="spec-tag">Deep Learning</span>
                            <span class="spec-tag">Processamento de Linguagem Natural</span>
                            <span class="spec-tag">Computer Vision</span>
                        </div>
                    </div>
                    <div class="spec-category">
                        <h3>Análise de Dados</h3>
                        <div class="spec-items">
                            <span class="spec-tag">Estatística Aplicada</span>
                            <span class="spec-tag">Visualização de Dados</span>
                            <span class="spec-tag">Big Data Analytics</span>
                            <span class="spec-tag">Business Intelligence</span>
                            <span class="spec-tag">Análise Preditiva</span>
                        </div>
                    </div>
                    <div class="spec-category">
                        <h3>Tecnologias</h3>
                        <div class="spec-items">
                            <span class="spec-tag">Python</span>
                            <span class="spec-tag">R</span>
                            <span class="spec-tag">SQL</span>
                            <span class="spec-tag">TensorFlow</span>
                            <span class="spec-tag">Tableau</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section class="content-section">
            <div class="container">
                <div class="section-header">
                    <h2 class="section-title">Setores de Aplicação</h2>
                    <p class="section-subtitle">
                        Áreas onde pretendo aplicar conhecimentos em ciência de dados
                    </p>
                </div>
                <div class="sectors-grid">
                    <div class="sector-card">
                        <div class="sector-icon">🏥</div>
                        <h3>Saúde</h3>
                        <p>Análise de dados médicos, diagnósticos assistidos por IA, e otimização de tratamentos</p>
                    </div>
                    <div class="sector-card">
                        <div class="sector-icon">💰</div>
                        <h3>Finanças</h3>
                        <p>Análise de riscos, detecção de fraudes, algoritmos de trading e fintechs</p>
                    </div>
                    <div class="sector-card">
                        <div class="sector-icon">🛒</div>
                        <h3>E-commerce</h3>
                        <p>Sistemas de recomendação, análise de comportamento do consumidor e otimização de vendas</p>
                    </div>
                    <div class="sector-card">
                        <div class="sector-icon">🎓</div>
                        <h3>Educação</h3>
                        <p>Personalização do aprendizado, análise de desempenho e tecnologias educacionais</p>
                    </div>
                    <div class="sector-card">
                        <div class="sector-icon">🌱</div>
                        <h3>Sustentabilidade</h3>
                        <p>Análise ambiental, otimização de recursos e soluções para mudanças climáticas</p>
                    </div>
                    <div class="sector-card">
                        <div class="sector-icon">🚗</div>
                        <h3>Mobilidade</h3>
                        <p>Veículos autônomos, otimização de rotas e sistemas de transporte inteligentes</p>
                    </div>
                </div>
            </div>
        </section>

        <section class="content-section">
            <div class="container">
                <div class="section-header">
                    <h2 class="section-title">Interesses Complementares</h2>
                </div>
                <div class="complementary-interests">
                    <div class="interest-item">
                        <div class="interest-icon">🚀</div>
                        <div class="interest-content">
                            <h3>Empreendedorismo</h3>
                            <p>
                                Interesse em transformar soluções técnicas em negócios viáveis, 
                                sempre focando na criação de valor e impacto positivo.
                            </p>
                        </div>
                    </div>
                    <div class="interest-item">
                        <div class="interest-icon">🤝</div>
                        <div class="interest-content">
                            <h3>Liderança e Trabalho Social</h3>
                            <p>
                                Experiência em liderar grupos solidários, demonstrando interesse 
                                em causas sociais e desenvolvimento de habilidades de liderança.
                            </p>
                        </div>
                    </div>
                    <div class="interest-item">
                        <div class="interest-icon">📚</div>
                        <div class="interest-content">
                            <h3>Aprendizado Contínuo</h3>
                            <p>
                                Paixão pelo conhecimento e pela constante atualização em 
                                tecnologias emergentes e tendências do mercado.
                            </p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section class="content-section">
            <div class="container">
                <div class="quote-section">
                    <blockquote class="personal-quote">
                        <p>
                            "Os dados são o novo petróleo, mas somente quando refinados adequadamente 
                            se transformam em combustível para a inovação e o progresso."
                        </p>
                        <footer>
                            <cite>— Reflexão pessoal sobre o poder dos dados</cite>
                        </footer>
                    </blockquote>
                </div>
            </div>
        </section>
    </div>

    <!-- PROJETOS PAGE -->
    <div id="projetos" class="page">
        <section class="page-banner">
            <div class="container">
                <div class="banner-content">
                    <h1 class="page-title">Projetos & Experiências</h1>
                    <p class="page-subtitle">Jornada acadêmica, liderança social e desenvolvimento pessoal</p>
                </div>
            </div>
        </section>

        <section class="content-section">
            <div class="container">
                <div class="section-header">
                    <h2 class="section-title">Experiências Acadêmicas</h2>
                </div>
                
                <div class="project-highlight">
                    <div class="project-content">
                        <div class="project-header">
                            <div class="project-icon">⚡</div>
                            <div class="project-info">
                                <h3>Liga Acadêmica IBTech</h3>
                                <span class="project-institution">IBMEC Faria Lima</span>
                                <span class="project-status active">Membro Ativo</span>
                            </div>
                        </div>
                        <div class="project-description">
                            <p>
                                Participação ativa na Liga Acadêmica IBTech, organização estudantil focada 
                                no desenvolvimento de conhecimentos em tecnologia e inovação. A liga promove 
                                workshops, hackathons, palestras e projetos práticos relacionados à 
                                ciência de dados e inteligência artificial.
                            </p>
                        </div>
                        <div class="project-skills">
                            <h4>Competências Desenvolvidas:</h4>
                            <div class="skills-tags">
                                <span class="skill-tag">Trabalho em Equipe</span>
                                <span class="skill-tag">Gestão de Projetos</span>
                                <span class="skill-tag">Networking</span>
                                <span class="skill-tag">Tecnologias Emergentes</span>
                                <span class="skill-tag">Apresentações Técnicas</span>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="experience-grid">
                    <div class="experience-card">
                        <div class="exp-header">
                            <div class="exp-icon">🎓</div>
                            <h3>Universidade Mackenzie</h3>
                        </div>
                        <div class="exp-content">
                            <p>
                                Experiência acadêmica que contribuiu para o desenvolvimento de uma 
                                base sólida em conhecimentos fundamentais e amadurecimento da 
                                escolha profissional.
                            </p>
                            <div class="exp-learnings">
                                <h4>Principais Aprendizados:</h4>
                                <ul>
                                    <li>Metodologias de estudo eficazes</li>
                                    <li>Pensamento crítico e analítico</li>
                                    <li>Adaptabilidade acadêmica</li>
                                </ul>
                            </div>
                        </div>
                    </div>

                    <div class="experience-card">
                        <div class="exp-header">
                            <div class="exp-icon">🏛️</div>
                            <h3>Morumbi</h3>
                        </div>
                        <div class="exp-content">
                            <p>
                                Experiência complementar que enriqueceu a formação acadêmica 
                                e proporcionou diferentes perspectivas sobre o ensino superior 
                                e desenvolvimento profissional.
                            </p>
                            <div class="exp-learnings">
                                <h4>Contribuições:</h4>
                                <ul>
                                    <li>Diversidade de abordagens pedagógicas</li>
                                    <li>Networking acadêmico ampliado</li>
                                    <li>Comparação de metodologias</li>
                                </ul>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section class="content-section">
            <div class="container">
                <div class="section-header">
                    <h2 class="section-title">Projetos Sociais & Liderança</h2>
                </div>

                <div class="social-project-highlight">
                    <div class="social-content">
                        <div class="social-header">
                            <div class="social-icon">🤝</div>
                            <div class="social-info">
                                <h3>Liderança em Grupos Solidários</h3>
                                <span class="social-org">Amigos do Bem</span>
                                <span class="social-role">Líder de Grupo</span>
                            </div>
                        </div>
                        
                        <div class="social-description">
                            <p>
                                Experiência significativa liderando grupos solidários da instituição 
                                Amigos do Bem, desenvolvendo projetos sociais voltados para 
                                comunidades em situação de vulnerabilidade social.
                            </p>
                        </div>

                        <div class="leadership-details">
                            <div class="leadership-grid">
                                <div class="leadership-item">
                                    <div class="leadership-icon">👥</div>
                                    <h4>Gestão de Equipes</h4>
                                    <p>Coordenação de voluntários em ações solidárias</p>
                                </div>
                                <div class="leadership-item">
                                    <div class="leadership-icon">📋</div>
                                    <h4>Planejamento</h4>
                                    <p>Organização e execução de campanhas beneficentes</p>
                                </div>
                                <div class="leadership-item">
                                    <div class="leadership-icon">💡</div>
                                    <h4>Inovação Social</h4>
                                    <p>Desenvolvimento de soluções criativas para problemas sociais</p>
                                </div>
                                <div class="leadership-item">
                                    <div class="leadership-icon">🎯</div>
                                    <h4>Resultados</h4>
                                    <p>Alcance de metas e impacto mensurável nas comunidades</p>
                                </div>
                            </div>
                        </div>

                        <div class="impact-metrics">
                            <h4>Impacto Gerado:</h4>
                            <div class="metrics-grid">
                                <div class="metric-item">
                                    <span class="metric-icon">🏠</span>
                                    <div class="metric-content">
                                        <h5>Comunidades Atendidas</h5>
                                        <p>Múltiplas famílias beneficiadas com ações coordenadas</p>
                                    </div>
                                </div>
                                <div class="metric-item">
                                    <span class="metric-icon">👨‍👩‍👧‍👦</span>
                                    <div class="metric-content">
                                        <h5>Voluntários Mobilizados</h5>
                                        <p>Liderança de equipes dedicadas ao trabalho social</p>
                                    </div>
                                </div>
                                <div class="metric-item">
                                    <span class="metric-icon">📦</span>
                                    <div class="metric-content">
                                        <h5>Recursos Arrecadados</h5>
                                        <p>Coordenação de campanhas de arrecadação eficazes</p>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- CONTATO PAGE -->
    <div id="contato" class="page">
        <section class="page-banner">
            <div class="container">
                <div class="banner-content">
                    <h1 class="page-title">Contato</h1>
                    <p class="page-subtitle">Entre em contato para oportunidades e colaborações</p>
                </div>
            </div>
        </section>

        <section class="content-section">
            <div class="container">
                <div class="section-header">
                    <h2 class="section-title">Meios de Contato</h2>
                    <p class="section-subtitle">
                        Estou sempre aberto a novas oportunidades, projetos interessantes e conversas sobre tecnologia
                    </p>
                </div>

                <div class="contact-grid">
                    <div class="contact-card">
                        <div class="contact-icon">📧</div>
                        <div class="contact-info">
                            <h3>Email</h3>
                            <p class="contact-detail">
                                <a href="mailto:henriqueperezzz.contato@gmail.com" class="contact-link">
                                    henriqueperezzz.contato@gmail.com
                                </a>
                            </p>
                            <p>Resposta em até 24 horas</p>
                        </div>
                    </div>

                    <div class="contact-card">
                        <div class="contact-icon">💼</div>
                        <div class="contact-info">
                            <h3>LinkedIn</h3>
                            <p class="contact-detail">
                                <a href="https://linkedin.com/in/henriqueperez" target="_blank" class="contact-link">
                                    linkedin.com/in/henriqueperez
                                </a>
                            </p>
                            <p>Conecte-se para networking</p>
                        </div>
                    </div>

                    <div class="contact-card">
                        <div class="contact-icon">📱</div>
                        <div class="contact-info">
                            <h3>Telefone</h3>
                            <p class="contact-detail">
                                <a href="tel:+5511933805108" class="contact-link">
                                    (11) 93380-5108
                                </a>
                            </p>
                            <p>Disponível para chamadas e WhatsApp</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section class="content-section">
            <div class="container">
                <div class="quote-section">
                    <blockquote class="personal-quote">
                        <p>
                            "A tecnologia só tem valor real quando conecta pessoas, resolve problemas 
                            e cria oportunidades para um futuro melhor."
                        </p>
                        <footer>
                            <cite>— Henrique Perez</cite>
                        </footer>
                    </blockquote>
                </div>
            </div>
        </section>
    </div>

    <!-- Footer -->
    <footer class="footer">
        <div class="container">
            <p>&copy; 2024 Henrique Perez. Desenvolvido com dedicação e inovação.</p>
        </div>
    </footer>

    <script>
        // =================== NAVEGAÇÃO ENTRE PÁGINAS =================== 
        document.addEventListener('DOMContentLoaded', function() {
            const navLinks = document.querySelectorAll('.nav-link, .btn[data-page]');
            const pages = document.querySelectorAll('.page');
            const navMenu = document.getElementById('nav-menu');
            const navToggle = document.getElementById('nav-toggle');

            // Função para mostrar página
            function showPage(pageId) {
                // Esconder todas as páginas
                pages.forEach(page => {
                    page.classList.remove('active');
                });

                // Mostrar página selecionada
                const targetPage = document.getElementById(pageId);
                if (targetPage) {
                    targetPage.classList.add('active');
                }

                // Atualizar links ativos
                navLinks.forEach(link => {
                    link.classList.remove('active');
                });

                // Marcar link ativo
                const activeLink = document.querySelector(`[data-page="${pageId}"]`);
                if (activeLink && activeLink.classList.contains('nav-link')) {
                    activeLink.classList.add('active');
                }

                // Fechar menu mobile se estiver aberto
                navMenu.classList.remove('active');
                navToggle.classList.remove('active');
                resetHamburger();

                // Scroll para o topo
                window.scrollTo(0, 0);
            }

            // Event listeners para navegação
            navLinks.forEach(link => {
                link.addEventListener('click', function(e) {
                    e.preventDefault();
                    const pageId = this.getAttribute('data-page');
                    if (pageId) {
                        showPage(pageId);
                    }
                });
            });

            // =================== MENU MOBILE =================== 
            function resetHamburger() {
                const bars = navToggle.querySelectorAll('.bar');
                bars.forEach(bar => {
                    bar.style.transform = 'none';
                    bar.style.opacity = '1';
                });
            }

            if (navToggle) {
                navToggle.addEventListener('click', function() {
                    navMenu.classList.toggle('active');
                    navToggle.classList.toggle('active');
                    
                    const bars = navToggle.querySelectorAll('.bar');
                    bars.forEach((bar, index) => {
                        if (navToggle.classList.contains('active')) {
                            if (index === 0) bar.style.transform = 'rotate(-45deg) translate(-5px, 6px)';
                            if (index === 1) bar.style.opacity = '0';
                            if (index === 2) bar.style.transform = 'rotate(45deg) translate(-5px, -6px)';
                        } else {
                            resetHamburger();
                        }
                    });
                });
            }

            // =================== HEADER DINÂMICO =================== 
            window.addEventListener('scroll', function() {
                const header = document.querySelector('.header');
                if (window.scrollY > 50) {
                    header.style.boxShadow = 'var(--shadow-md)';
                    header.style.background = 'var(--surface-color)';
                } else {
                    header.style.boxShadow = 'var(--shadow-sm)';
                    header.style.background = 'var(--surface-color)';
                }
            });

            // Mostrar a página inicial por padrão
            showPage('home');
        });
    </script>
</body>
</html>
