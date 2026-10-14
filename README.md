<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Amar Kumar Das - Software Developer Portfolio</title>
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary-glow: rgba(99, 102, 241, 0.4);
            --secondary-glow: rgba(236, 72, 153, 0.3);
            --glass-bg: rgba(255, 255, 255, 0.05);
            --glass-border: rgba(255, 255, 255, 0.12);
            --glass-hover: rgba(255, 255, 255, 0.08);
            --text-main: #f8fafc;
            --text-muted: #94a3b8;
            --accent: #818cf8;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Plus Jakarta Sans', sans-serif;
            background-color: #030712;
            color: var(--text-main);
            min-height: 100vh;
            overflow-x: hidden;
            position: relative;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 40px 20px;
        }

        /* Ambient Background Blobs */
        .ambient-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            overflow: hidden;
            z-index: -1;
            background: radial-gradient(circle at 50% 50%, #0f172a 0%, #030712 100%);
        }

        .blob {
            position: absolute;
            border-radius: 50%;
            filter: blur(80px);
            opacity: 0.6;
            animation: float 20s infinite alternate ease-in-out;
        }

        .blob-1 {
            width: 450px;
            height: 450px;
            background: #4f46e5;
            top: -10%;
            left: -10%;
        }

        .blob-2 {
            width: 400px;
            height: 400px;
            background: #db2777;
            bottom: -10%;
            right: -10%;
            animation-delay: -5s;
        }

        .blob-3 {
            width: 350px;
            height: 350px;
            background: #0ea5e9;
            top: 40%;
            left: 50%;
            transform: translate(-50%, -50%);
            animation-delay: -10s;
        }

        @keyframes float {
            0% { transform: translate(0, 0) scale(1); }
            50% { transform: translate(30px, 50px) scale(1.1); }
            100% { transform: translate(-20px, -30px) scale(0.9); }
        }

        /* Main Glass Container */
        .glass-container {
            width: 100%;
            max-width: 900px;
            background: var(--glass-bg);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            border-radius: 24px;
            box-shadow: 0 30px 60px rgba(0, 0, 0, 0.4), inset 0 1px 0 rgba(255, 255, 255, 0.1);
            padding: 40px;
            z-index: 1;
        }

        /* Header Section */
        header {
            text-align: center;
            margin-bottom: 35px;
            border-bottom: 1px solid var(--glass-border);
            padding-bottom: 30px;
        }

        h1 {
            font-size: 2.5rem;
            font-weight: 700;
            letter-spacing: -0.025em;
            margin-bottom: 8px;
            background: linear-gradient(135deg, #ffffff 30%, #94a3b8 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .subtitle {
            font-size: 1.15rem;
            font-weight: 600;
            color: var(--accent);
            letter-spacing: 0.05em;
            text-transform: uppercase;
            margin-bottom: 15px;
        }

        .contact-info {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 16px;
            font-size: 0.95rem;
            color: var(--text-muted);
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 6px;
            background: rgba(255, 255, 255, 0.03);
            border: 1px solid var(--glass-border);
            padding: 6px 14px;
            border-radius: 50px;
            transition: all 0.3s ease;
            text-decoration: none;
            color: var(--text-muted);
        }

        .contact-item:hover {
            background: var(--glass-hover);
            color: var(--text-main);
            border-color: rgba(255, 255, 255, 0.25);
            transform: translateY(-2px);
        }

        .contact-item i {
            color: var(--accent);
        }

        /* Section Styling */
        section {
            margin-bottom: 35px;
        }

        section:last-child {
            margin-bottom: 0;
        }

        h2 {
            font-size: 1.25rem;
            font-weight: 600;
            letter-spacing: -0.01em;
            margin-bottom: 16px;
            display: flex;
            align-items: center;
            gap: 10px;
            color: #ffffff;
            border-left: 3px solid var(--accent);
            padding-left: 12px;
        }

        p {
            font-size: 0.95rem;
            line-height: 1.6;
            color: var(--text-muted);
        }

        /* Skills Grid */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 16px;
        }

        .skill-card {
            background: rgba(255, 255, 255, 0.02);
            border: 1px solid var(--glass-border);
            border-radius: 14px;
            padding: 16px;
            transition: all 0.3s ease;
        }

        .skill-card:hover {
            background: var(--glass-hover);
            border-color: rgba(255, 255, 255, 0.2);
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
        }

        .skill-card h3 {
            font-size: 0.9rem;
            font-weight: 600;
            color: var(--accent);
            margin-bottom: 8px;
            text-transform: uppercase;
            letter-spacing: 0.05em;
        }

        .tag-list {
            display: flex;
            flex-wrap: wrap;
            gap: 6px;
        }

        .tag {
            font-size: 0.8rem;
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(255, 255, 255, 0.08);
            padding: 4px 10px;
            border-radius: 6px;
            color: var(--text-main);
        }

        /* Experience & Projects List */
        .timeline-item, .project-card {
            background: rgba(255, 255, 255, 0.02);
            border: 1px solid var(--glass-border);
            border-radius: 16px;
            padding: 20px;
            margin-bottom: 16px;
            transition: all 0.3s ease;
        }

        .timeline-item:hover, .project-card:hover {
            background: var(--glass-hover);
            border-color: rgba(255, 255, 255, 0.2);
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }

        .item-header {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            flex-wrap: wrap;
            gap: 8px;
            margin-bottom: 8px;
        }

        .item-title {
            font-size: 1.05rem;
            font-weight: 600;
            color: #ffffff;
        }

        .item-subtitle {
            font-size: 0.9rem;
            color: var(--accent);
            font-weight: 500;
        }

        .item-date {
            font-size: 0.85rem;
            background: rgba(255, 255, 255, 0.05);
            padding: 4px 10px;
            border-radius: 20px;
            color: var(--text-muted);
            border: 1px solid var(--glass-border);
        }

        ul.bullet-list {
            margin-top: 10px;
            padding-left: 18px;
            color: var(--text-muted);
            font-size: 0.92rem;
            line-height: 1.5;
        }

        ul.bullet-list li {
            margin-bottom: 6px;
        }

        /* Projects Grid */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 16px;
        }

        .project-card {
            margin-bottom: 0;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .project-desc {
            font-size: 0.9rem;
            margin-bottom: 14px;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 6px;
            margin-top: auto;
        }

        .project-tech span {
            font-size: 0.75rem;
            background: rgba(129, 140, 248, 0.1);
            color: #a5b4fc;
            border: 1px solid rgba(129, 140, 248, 0.2);
            padding: 3px 8px;
            border-radius: 4px;
        }

        /* Education */
        .edu-list {
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        .edu-item {
            background: rgba(255, 255, 255, 0.02);
            border: 1px solid var(--glass-border);
            border-radius: 12px;
            padding: 14px 18px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 10px;
        }

        .edu-details h3 {
            font-size: 0.95rem;
            color: #ffffff;
            font-weight: 600;
        }

        .edu-details p {
            font-size: 0.85rem;
        }

        .edu-score {
            font-size: 0.9rem;
            font-weight: 600;
            color: #34d399;
            background: rgba(52, 211, 153, 0.1);
            border: 1px solid rgba(52, 211, 153, 0.2);
            padding: 4px 10px;
            border-radius: 8px;
        }

        /* Responsive */
        @media (max-width: 768px) {
            body {
                padding: 20px 10px;
            }
            .glass-container {
                padding: 24px;
            }
            h1 {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>

    <div class="ambient-bg">
        <div class="blob blob-1"></div>
        <div class="blob-2 blob"></div>
        <div class="blob-3 blob"></div>
    </div>

    <div class="glass-container">
        <!-- Header -->
        <header>
            <h1>AMAR KUMAR DAS</h1>
            <div class="subtitle">Software Developer</div>
            <div class="contact-info">
                <a href="tel:+917481099770" class="contact-item"><i class="fas fa-phone"></i> +91 7481099770</a>
                <a href="mailto:amarkrdas1905@gmail.com" class="contact-item"><i class="fas fa-envelope"></i> amarkrdas1905@gmail.com</a>
                <span class="contact-item"><i class="fas fa-map-marker-alt"></i> Ranchi, Jharkhand</span>
                <a href="https://linkedin.com" target="_blank" class="contact-item"><i class="fab fa-linkedin"></i> LinkedIn</a>
                <a href="https://github.com" target="_blank" class="contact-item"><i class="fab fa-github"></i> GitHub</a>
                <a href="https://portfolio-link.com" target="_blank" class="contact-item"><i class="fas fa-globe"></i> Portfolio</a>
            </div>
        </header>

        <!-- Profile / About -->
        <section>
            <h2><i class="fas fa-user-astronaut"></i> Profile</h2>
            <p>Software Developer with 3+ years of experience in developing, maintaining, and enhancing enterprise web applications, REST APIs, and database-driven software solutions. Proficient in PHP, MySQL, JavaScript, HTML, CSS, and Slim Framework, with experience in Android application development using Java. Skilled in API integration, database synchronization, reporting, system troubleshooting, and developing responsive, user-friendly applications.</p>
        </section>

        <!-- Technical Skills -->
        <section>
            <h2><i class="fas fa-code"></i> Technical Skills</h2>
            <div class="skills-grid">
                <div class="skill-card">
                    <h3>Programming Languages</h3>
                    <div class="tag-list">
                        <span class="tag">PHP</span>
                        <span class="tag">Java</span>
                        <span class="tag">JavaScript</span>
                        <span class="tag">SQL</span>
                        <span class="tag">HTML5</span>
                        <span class="tag">CSS3</span>
                    </div>
                </div>
                <div class="skill-card">
                    <h3>Frameworks & Libraries</h3>
                    <div class="tag-list">
                        <span class="tag">Slim Framework</span>
                        <span class="tag">jQuery</span>
                        <span class="tag">Bootstrap</span>
                        <span class="tag">TCPDF</span>
                    </div>
                </div>
                <div class="skill-card">
                    <h3>Databases & Web Tech</h3>
                    <div class="tag-list">
                        <span class="tag">MySQL</span>
                        <span class="tag">MariaDB</span>
                        <span class="tag">REST APIs</span>
                        <span class="tag">JSON</span>
                        <span class="tag">AJAX</span>
                        <span class="tag">DataTables</span>
                    </div>
                </div>
                <div class="skill-card">
                    <h3>Tools & Platforms</h3>
                    <div class="tag-list">
                        <span class="tag">Git</span>
                        <span class="tag">XAMPP</span>
                        <span class="tag">Apache</span>
                        <span class="tag">Windows Server</span>
                        <span class="tag">Linux</span>
                        <span class="tag">Postman</span>
                    </div>
                </div>
            </div>
        </section>

        <!-- Experience -->
        <section>
            <h2><i class="fas fa-briefcase"></i> Professional Experience</h2>
            
            <div class="timeline-item">
                <div class="item-header">
                    <div>
                        <div class="item-title">Software Developer</div>
                        <div class="item-subtitle">Sigma eSolution Pvt. Ltd. • Ranchi, Jharkhand</div>
                    </div>
                    <div class="item-date">2023 – Present</div>
                </div>
                <ul class="bullet-list">
                    <li>Develop, maintain, and enhance enterprise web applications for visitor management, access control, and administrative operations using PHP, MySQL, JavaScript, and Slim Framework.</li>
                    <li>Design and integrate REST APIs to enable communication between server databases, local controllers, and external systems.</li>
                    <li>Implement database synchronization, business workflows, and reporting modules to ensure reliable data processing and monitoring.</li>
                    <li>Integrate RFID/UHF and ANPR-based vehicle entry systems, including vehicle verification, transaction monitoring, and boom barrier control.</li>
                    <li>Develop Android-based attendance solutions for the Jharkhand High Court, incorporating face detection, employee profile synchronization, local data storage, and geofencing.</li>
                    <li>Troubleshoot production issues, optimize application performance, and improve responsive user interfaces.</li>
                </ul>
            </div>

            <div class="timeline-item">
                <div class="item-header">
                    <div>
                        <div class="item-title">Intern</div>
                        <div class="item-subtitle">Tata Steel – SNTI • Jamshedpur</div>
                    </div>
                    <div class="item-date">May 2023</div>
                </div>
            </div>
        </section>

        <!-- Projects -->
        <section>
            <h2><i class="fas fa-rocket"></i> Key Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <div>
                        <div class="item-title" style="margin-bottom: 6px;">Visitor Management System (VMS)</div>
                        <p class="project-desc">Modules for visitor registration, approval workflows, pass & ID card generation, reporting, OTP authentication, and multi-location access control.</p>
                    </div>
                    <div class="project-tech">
                        <span>PHP</span>
                        <span>Slim</span>
                        <span>MySQL</span>
                        <span>REST APIs</span>
                    </div>
                </div>

                <div class="project-card">
                    <div>
                        <div class="item-title" style="margin-bottom: 6px;">ANPR Vehicle Entry System</div>
                        <p class="project-desc">Automatic Number Plate Recognition system performing PASS/FAIL server validation to trigger boom barriers and monitor transactions.</p>
                    </div>
                    <div class="project-tech">
                        <span>PHP</span>
                        <span>MySQL</span>
                        <span>ANPR</span>
                        <span>Hardware Integration</span>
                    </div>
                </div>

                <div class="project-card">
                    <div>
                        <div class="item-title" style="margin-bottom: 6px;">Jharkhand High Court Attendance App</div>
                        <p class="project-desc">Android application featuring facial recognition, admin approval workflows, profile sync, geofencing restrictions, and server punch-in/out.</p>
                    </div>
                    <div class="project-tech">
                        <span>Java</span>
                        <span>Android SDK</span>
                        <span>MySQL</span>
                        <span>REST APIs</span>
                    </div>
                </div>

                <div class="project-card">
                    <div>
                        <div class="item-title" style="margin-bottom: 6px;">AG(A&E) Bihar GE Software Upgrades</div>
                        <p class="project-desc">Enhanced legacy software with service history tracking, pay slip generation, event logging, and digital signatures adhering to judicial regulations.</p>
                    </div>
                    <div class="project-tech">
                        <span>PHP</span>
                        <span>MySQL</span>
                        <span>JavaScript</span>
                    </div>
                </div>
            </div>
        </section>

        <!-- Education -->
        <section>
            <h2><i class="fas fa-graduation-cap"></i> Education</h2>
            <div class="edu-list">
                <div class="edu-item">
                    <div class="edu-details">
                        <h3>B.Tech (Computer Science)</h3>
                        <p>JUTRTC Institute of Technology, Ranchi, Jharkhand (2019 – 2023)</p>
                    </div>
                    <div class="edu-score">83.20%</div>
                </div>
                <div class="edu-item">
                    <div class="edu-details">
                        <h3>Intermediate (CBSE)</h3>
                        <p>D.A.V. Public School Kedla, Ramgarh, Jharkhand (2017 – 2019)</p>
                    </div>
                    <div class="edu-score">84.00%</div>
                </div>
                <div class="edu-item">
                    <div class="edu-details">
                        <h3>Matriculation (CBSE)</h3>
                        <p>D.A.V. Public School Kedla, Ramgarh, Jharkhand (2015 – 2017)</p>
                    </div>
                    <div class="edu-score">86.00%</div>
                </div>
            </div>
        </section>
    </div>

</body>
</html>
