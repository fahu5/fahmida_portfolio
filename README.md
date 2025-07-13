<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mst. Fahmida Akter - CSE Student & Frontend Designer</title>
    
    <!-- Google Fonts: Poppins -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;700&display=swap" rel="stylesheet">

    <!-- Font Awesome for icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.1.1/css/all.min.css">

    <style>
        /* --- CSS Variables --- */
        :root {
            --powder-blue: #B0E0E6;
            --ash-gray: #f0f2f5; /* Lighter ash for background */
            --black: #000000;
            --white: #ffffff;
            --text-color: #333;
            --light-shadow: 0 4px 15px rgba(0, 0, 0, 0.05);
        }

        /* --- Base & Reset --- */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Poppins', Arial, sans-serif;
            background-color: var(--white);
            color: var(--text-color);
            line-height: 1.6;
        }

        .download-resume {
            position: fixed;
            top: 20px;
            right: 30px;
            color: var(--text-color);
            text-decoration: none;
            z-index: 1001;
            transition: color 0.3s ease, transform 0.3s ease, background-color 0.3s ease, border-color 0.3s ease;
            display: flex;
            align-items: center;
            gap: 8px;
            font-size: 1rem;
            font-weight: 500;
            background-color: var(--white);
            padding: 8px 15px;
            border-radius: 25px;
            border: 1px solid #ddd;
            box-shadow: var(--light-shadow);
            background-color: #c2f1fa;
        }

        .download-resume i {
            font-size: 1.6rem;
        }

        .download-resume:hover {
            color: var(--text-color);
            transform: scale(1.05);
            background-color: var(--powder-blue);
            border-color: var(--powder-blue);
        }

        .container {
            max-width: 1140px;
            margin: 0 auto;
            padding: 0 20px;
        }

        section {
            padding: 100px 0;
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.6s ease-out, transform 0.6s ease-out;
        }

        section.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .section-title {
            text-align: center;
            margin-bottom: 60px;
            
        }

        .section-title h2 {
            font-size: 2.5rem;
            font-weight: 700;
            position: relative;
            display: inline-block;
            padding-bottom: 10px;
        }

        .section-title h2::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 3px;
            background-color: var(--powder-blue);
        }

        /* --- Merged Intro Section --- */
        #intro {
            background-color: var(--ash-gray);
            display: flex;
            align-items: center;
            padding: 80px 0;
        }

        .intro-container {
            display: flex;
            align-items: center;
            gap: 60px;
            width: 100%;
        }

        .intro-image img {
            width: 280px;
            height: 280px;
            border-radius: 50%;
            object-fit: cover;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            border: 5px solid var(--white);
        }

        .intro-text h2 {
            font-size: 1.5rem;
            font-weight: 400;
        }

        .intro-text h1 {
            font-size: 3.5rem;
            font-weight: 700;
            margin: 5px 0;
            color: var(--black);
        }

        .intro-text .animated-text {
            font-size: 2rem;
            color: var(--powder-blue);
            font-weight: 500;
            height: 2.5rem;
            margin-bottom: 15px;
        }
        
        .intro-text p {
            max-width: 600px;
        }

        .intro-social {
            margin-top: 25px;
        }

        .intro-social a {
            color: var(--black);
            font-size: 1.5rem;
            margin-right: 20px;
            transition: color 0.3s ease;
        }

        .intro-social a:hover {
            color: var(--powder-blue);
        }

        /* --- Skills Section --- */
        .skills-container {
            display: flex;
            gap: 50px;
        }

        .skills-column {
            flex: 1;
        }

        .skills-column h3 {
            font-size: 1.8rem;
            margin-bottom: 20px;
        }

        .skill-tag {
            display: inline-block;
            background-color: #e0f7fa;
            color: #007c91;
            padding: 8px 18px;
            margin: 5px;
            border-radius: 20px;
            font-weight: 500;
        }

        /* --- Resume Section --- */
        #resume { background-color: #fafafa; }
        .resume-timeline {
            position: relative;
            max-width: 800px;
            margin: 0 auto;
        }
        /*.resume-timeline::before {
            content: '';
            position: absolute;
            width: 2px;
            background: #ce4949;
            top: 0;
            bottom: 0;
            left: 15px;
        }*/
        .timeline-block { margin-bottom: 50px; }
        .timeline-block h3 { margin-bottom: 30px; font-size: 1.8rem; }
        .timeline-item {
            position: relative;
            padding-left: 50px;
            margin-bottom: 30px;
        }
        .timeline-icon {
            position: absolute;
            left: 0;
            top: 0;
            width: 32px;
            height: 32px;
            background: var(--powder-blue);
            color: var(--black);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        .timeline-content h4 { font-size: 1.2rem; }
        .timeline-content p { margin: 5px 0; }
        .timeline-content span { color: #777; font-size: 0.9rem; }

        /* --- Projects, Achievements, Certifications --- */
        .card-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 30px;
        }
        .card {
            background: var(--white);
            border-radius: 8px;
            box-shadow: var(--light-shadow);
            overflow: hidden;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(0,0,0,0.08);
        }
        .card-image img {
            width: 100%;
            height: 220px;
            object-fit: cover;
        }
        .card-content { padding: 25px; }
        .card-content h3 { font-size: 1.3rem; margin-bottom: 10px; }
        .card-content .tech-stack { margin: 15px 0; }
        .card-content .tech-stack span {
            background: #eee;
            padding: 4px 10px;
            border-radius: 4px;
            font-size: 0.8rem;
            margin-right: 5px;
        }
        .card-links a { margin-right: 15px; font-weight: 500; }

        /* --- Contact Section --- */
        #contact { background-color: #fafafa; }
        .contact-items {
            display: flex;
            justify-content: space-around;
            text-align: center;
            flex-wrap: wrap;
        }
        .contact-item i {
            font-size: 2rem;
            color: var(--powder-blue);
            margin-bottom: 15px;
        }

        /* --- Footer --- */
        footer {
            background: var(--black);
            color: var(--ash-gray);
            text-align: center;
            padding: 20px 0;
        }

        /* --- Responsive Design --- */
        @media (max-width: 768px) {
            .intro-container, .skills-container { flex-direction: column; text-align: center; }
            .intro-text h1 { font-size: 2.8rem; }
            .intro-text .animated-text { font-size: 1.5rem; }
        }
    </style>
</head>
<body>
    <a href="Fahmida_Akter_Resume.pdf" class="download-resume" download aria-label="Download Resume">
        <span>Resume</span>
        <i class="fas fa-download"></i>
    </a>

    <main>
        <section id="intro">
            <div class="container intro-container">
                <div class="intro-image">
                    <img src="pp.JPG" alt="Profile photo of Mst. Fahmida Akter">
                </div>
                <div class="intro-text">
                    <h2>Hello!</h2>
                    <h1>I'm Mst. Fahmida Akter</h1>
                    <div class="animated-text"><span></span></div>
                    <p>I’m a Computer Science & Engineering student with a strong passion for frontend design, UI/UX, and research. I bring a solid foundation in leadership, dedicated to inspiring and guiding teams toward meaningful goals. Through my academic and professional experiences, I strive to make a positive impact by fostering collaboration and innovation.</p>
                    <div class="intro-social">
                        <a href="https://www.linkedin.com/in/mst-fahmida-akter/" target="_blank" aria-label="LinkedIn"><i class="fab fa-linkedin"></i></a>
                        <a href="https://github.com/fahu5" target="_blank" aria-label="GitHub"><i class="fab fa-github"></i></a>
                    </div>
                </div>
            </div>
        </section>

        <section id="skills">
            <div class="container">
                <div class="section-title">
                    <h2>Skills & Technologies</h2>
                </div>
                <div class="skills-container">
                    <div class="skills-column">
                        <h3>Skills</h3>
                        <div class="skill-tag">C & C++</div>
                        <div class="skill-tag">Python</div>
                        <div class="skill-tag">HTML</div>
                        <div class="skill-tag">CSS</div>
                        <div class="skill-tag">JavaScript</div>
                        <div class="skill-tag">Web Programming</div>
                        <div class="skill-tag">UI/UX Design</div>
                        <div class="skill-tag">Public Speaking</div>
                        <div class="skill-tag">Communication</div>
                        <div class="skill-tag">Leadership</div>
                        <div class="skill-tag">Teamwork</div>
                        <div class="skill-tag">Problem Solving</div>
                        <div class="skill-tag">Research Analysis</div>
                    </div>
                    <div class="skills-column">
                        <h3>Technologies</h3>
                        <div class="skill-tag">C & C++</div>
                        <div class="skill-tag">Python</div>
                        <div class="skill-tag">HTML</div>
                        <div class="skill-tag">CSS</div>
                        <div class="skill-tag">JavaScript</div>
                        <div class="skill-tag">Web Programming</div>
                        <div class="skill-tag">UI/UX Design</div>
                    </div>
                </div>
            </div>
        </section>

       

        <section id="projects">
            <div class="container">
                <div class="section-title">
                    <h2>My Projects</h2>
                </div>
                <div class="card-grid">
                    <div class="card">
                        <div class="card-content">
                            <h3>Aqua Explorer</h3>
                            <p>A game-based water education platform for students.</p>
                            <div class="tech-stack"><span>HTML</span><span>CSS</span><span>JS</span></div>
                            <p><strong>Role:</strong> Research & UI Lead</p>
                        </div>
                    </div>
                    <div class="card">
                        <div class="card-content">
                            <h3>ScholarlyWay</h3>
                            <p>A Django-powered scholarship platform to connect students with opportunities.</p>
                            <div class="tech-stack"><span>Django</span><span>SQLite</span><span>HTML/CSS</span></div>
                            <p><strong>Role:</strong> Full Stack Developer</p>
                        </div>
                    </div>
                    <div class="card">
                        <div class="card-content">
                            <h3>NASA Space App Project</h3>
                            <p>A global winning solution for the NASA Space Apps Challenge.</p>
                            <div class="tech-stack"><span>Research</span><span>Team-Lead</span></div>
                            <p><strong>Role:</strong> Team Lead & Researcher</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

         <section id="resume">
            <div class="container">
                <div class="section-title">
                    <h2>Resume</h2>
                </div>
                <div class="resume-timeline">
                    <div class="timeline-block">
                        <h3>Education</h3>
                        <div class="timeline-item">
                            <div class="timeline-icon"><i class="fas fa-graduation-cap"></i></div>
                            <div class="timeline-content">
                                <h4>B.Sc. in Computer Science & Engineering</h4>
                                <p>Varendra University</p>
                                <span>2022–Present | CGPA: 3.92</span>
                            </div>
                        </div>
                        <div class="timeline-item">
                            <div class="timeline-icon"><i class="fas fa-graduation-cap"></i></div>
                            <div class="timeline-content">
                                <h4>Higher Secondary Certificate (HSC)</h4>
                                <p>Rajshahi Govt. Women’s College</p>
                                <span>GPA: 5.00</span>
                            </div>
                        </div>
                        <div class="timeline-item">
                            <div class="timeline-icon"><i class="fas fa-graduation-cap"></i></div>
                            <div class="timeline-content">
                                <h4>Secondary School Certificate (SSC)</h4>
                                <p>Rajshahi Cantonment Board School</p>
                                <span>GPA: 5.00</span>
                            </div>
                        </div>
                    </div>
                    <div class="timeline-block">
                        <h3>Co-Curricular Activities</h3>
                        <div class="timeline-item">
                            <div class="timeline-icon"><i class="fas fa-star"></i></div>
                            <div class="timeline-content">
                                <h4>Co-Convenor</h4>
                                <p>BASIS Students’ Forum - Varendra University Chapter</p>
                            </div>
                        </div>
                        <div class="timeline-item">
                            <div class="timeline-icon"><i class="fas fa-star"></i></div>
                            <div class="timeline-content">
                                <h4>SheSquad Leader</h4>
                                <p>BDApps</p>
                            </div>
                        </div>
                        <div class="timeline-item">
                            <div class="timeline-icon"><i class="fas fa-star"></i></div>
                            <div class="timeline-content">
                                <h4>Experts & Judges Support Head</h4>
                                <p>Hult Prize at Varendra University</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section id="achievements">
            <div class="container">
                <div class="section-title">
                    <h2>Achievements</h2>
                </div>
                <div class="card-grid">
                    <div class="card">
                        <div class="card-image"><img src="nasagolbal.jpg" alt="NASA Space Apps Winner"></div>
                        <div class="card-content">
                            <h3>Global Winner</h3>
                            <p>NASA Space Apps Challenge 2023 (Team Voyagers)</p>
                        </div>
                    </div>
                    <div class="card">
                        <div class="card-image"><img src="blockchain.jpg" alt="Blockchain Olympiad"></div>
                        <div class="card-content">
                            <h3>Finalist & Honorable Mention</h3>
                            <p>Blockchain Olympiad 2024 (Team Innovator 4.0)</p>
                        </div>
                    </div>
                    <div class="card">
                        <div class="card-image"><img src="hult-23.jpg" alt="Hult Prize"></div>
                        <div class="card-content">
                            <h3>Campus Champion & NY Semi-Finalist</h3>
                            <p>Hult Prize 2023 (Team Salvage)</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section id="certifications">
            <div class="container">
                <div class="section-title">
                    <h2>Certifications</h2>
                </div>
                <div class="card-grid">
                    <div class="card">
                        <div class="card-content">
                            <h3>Data Science Math Skills</h3>
                            <p>Issued by: Coursera (Duke University)</p>
                        </div>
                    </div>
                    <div class="card">
                        <div class="card-content">
                            <h3>AI for Everyone</h3>
                            <p>Issued by: Coursera (Andrew Ng)</p>
                        </div>
                    </div>
                    <div class="card">
                        <div class="card-content">
                            <h3>Frontend Development Basics</h3>
                            <p>Issued by: Programming Hero</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section id="contact">
            <div class="container">
                <div class="section-title">
                    <h2>Get In Touch</h2>
                </div>
                <div class="contact-items">
                    <div class="contact-item">
                        <i class="fas fa-map-marker-alt"></i>
                        <h3>Location</h3>
                        <p>Rajshahi, Bangladesh</p>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-envelope"></i>
                        <h3>Email</h3>
                        <p>222311003@vu.edu.bd</p>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-phone"></i>
                        <h3>Phone</h3>
                        <p>+880 1551-806324</p>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <footer>
        <div class="container">
            <p>© 2024 Mst. Fahmida Akter</p>
        </div>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            // --- Animated Text ---
            const animatedTextEl = document.querySelector('.animated-text span');
            const titles = ["CSE Student", "Frontend Designer", "Research Enthusiast"];
            let titleIndex = 0;
            let charIndex = 0;
            let isDeleting = false;

            function type() {
                const currentTitle = titles[titleIndex];
                let typeSpeed = isDeleting ? 75 : 150;

                if (isDeleting) {
                    animatedTextEl.textContent = currentTitle.substring(0, charIndex - 1);
                    charIndex--;
                } else {
                    animatedTextEl.textContent = currentTitle.substring(0, charIndex + 1);
                    charIndex++;
                }

                if (!isDeleting && charIndex === currentTitle.length) {
                    typeSpeed = 2000;
                    isDeleting = true;
                } else if (isDeleting && charIndex === 0) {
                    isDeleting = false;
                    titleIndex = (titleIndex + 1) % titles.length;
                    typeSpeed = 500;
                }
                
                setTimeout(type, typeSpeed);
            }
            type();

            // --- Scroll Animations ---
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('visible');
                    }
                });
            }, { threshold: 0.1 });

            document.querySelectorAll('section').forEach(section => {
                observer.observe(section);
            });
        });
    </script>
</body>
</html>
