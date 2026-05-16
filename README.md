<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Maria | Full Stack Developer</title>

  <!-- Google Font -->
  <link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;500;600;700;800&display=swap" rel="stylesheet"/>

  <!-- Icons -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.2/css/all.min.css"/>

  <!-- AOS -->
  <link href="https://unpkg.com/aos@2.3.4/dist/aos.css" rel="stylesheet">

  <style>
    *{
      margin:0;
      padding:0;
      box-sizing:border-box;
      scroll-behavior:smooth;
    }

    body{
      font-family:'Outfit',sans-serif;
      background:#050816;
      color:#fff;
      overflow-x:hidden;
    }

    :root{
      --primary:#7f5af0;
      --secondary:#00f7ff;
      --dark:#050816;
      --card:rgba(255,255,255,0.06);
      --glass:rgba(255,255,255,0.08);
      --border:rgba(255,255,255,0.12);
    }

    /* Scrollbar */
    ::-webkit-scrollbar{
      width:8px;
    }

    ::-webkit-scrollbar-track{
      background:#050816;
    }

    ::-webkit-scrollbar-thumb{
      background:linear-gradient(var(--primary),var(--secondary));
      border-radius:20px;
    }

    /* Background Glow */
    .bg-blur{
      position:fixed;
      width:500px;
      height:500px;
      background:radial-gradient(circle,var(--primary),transparent 70%);
      filter:blur(120px);
      opacity:.3;
      z-index:-1;
    }

    .bg1{
      top:-100px;
      left:-100px;
    }

    .bg2{
      bottom:-100px;
      right:-100px;
      background:radial-gradient(circle,var(--secondary),transparent 70%);
    }

    /* Navbar */

    header{
      position:fixed;
      width:100%;
      top:0;
      left:0;
      z-index:999;
      backdrop-filter:blur(15px);
      background:rgba(5,8,22,0.6);
      border-bottom:1px solid rgba(255,255,255,0.05);
    }

    nav{
      width:90%;
      margin:auto;
      display:flex;
      align-items:center;
      justify-content:space-between;
      padding:20px 0;
    }

    .logo{
      font-size:28px;
      font-weight:800;
      background:linear-gradient(to right,var(--secondary),var(--primary));
      -webkit-background-clip:text;
      -webkit-text-fill-color:transparent;
    }

    nav ul{
      display:flex;
      gap:30px;
      list-style:none;
    }

    nav ul li a{
      text-decoration:none;
      color:#fff;
      transition:.3s;
      font-weight:500;
    }

    nav ul li a:hover{
      color:var(--secondary);
    }

    /* Hero */

    .hero{
      min-height:100vh;
      display:flex;
      align-items:center;
      justify-content:center;
      padding:120px 10%;
      gap:60px;
      flex-wrap:wrap;
      position:relative;
    }

    .hero-text{
      flex:1;
      min-width:300px;
    }

    .hero-text h3{
      color:var(--secondary);
      margin-bottom:15px;
      font-size:22px;
    }

    .hero-text h1{
      font-size:65px;
      line-height:1.1;
      margin-bottom:20px;
      font-weight:800;
    }

    .gradient-text{
      background:linear-gradient(to right,#00f7ff,#7f5af0,#ff00ff);
      -webkit-background-clip:text;
      -webkit-text-fill-color:transparent;
    }

    .typing{
      font-size:28px;
      color:#ccc;
      margin-bottom:25px;
      height:40px;
    }

    .hero-text p{
      color:#b7b7b7;
      line-height:1.8;
      margin-bottom:35px;
      max-width:650px;
    }

    .btn-group{
      display:flex;
      gap:20px;
      flex-wrap:wrap;
    }

    .btn{
      padding:15px 30px;
      border-radius:14px;
      text-decoration:none;
      color:#fff;
      font-weight:600;
      transition:.4s;
      border:1px solid transparent;
    }

    .btn-primary{
      background:linear-gradient(to right,var(--primary),var(--secondary));
    }

    .btn-secondary{
      border:1px solid var(--secondary);
      background:transparent;
    }

    .btn:hover{
      transform:translateY(-5px);
      box-shadow:0 10px 30px rgba(0,247,255,.3);
    }

    .socials{
      margin-top:35px;
      display:flex;
      gap:18px;
    }

    .socials a{
      width:50px;
      height:50px;
      display:flex;
      align-items:center;
      justify-content:center;
      border-radius:50%;
      background:var(--glass);
      backdrop-filter:blur(10px);
      border:1px solid var(--border);
      color:#fff;
      text-decoration:none;
      transition:.4s;
      font-size:20px;
    }

    .socials a:hover{
      transform:translateY(-8px);
      background:linear-gradient(to right,var(--primary),var(--secondary));
    }

    .hero-image{
      flex:1;
      min-width:300px;
      text-align:center;
      position:relative;
    }

    .hero-image img{
      width:100%;
      max-width:450px;
      border-radius:30px;
      animation:float 5s ease-in-out infinite;
      filter:drop-shadow(0 0 40px rgba(127,90,240,.4));
    }

    @keyframes float{
      0%,100%{
        transform:translateY(0);
      }
      50%{
        transform:translateY(-20px);
      }
    }

    /* Sections */

    section{
      padding:100px 10%;
    }

    .section-title{
      text-align:center;
      margin-bottom:70px;
    }

    .section-title h2{
      font-size:45px;
      margin-bottom:15px;
    }

    .section-title p{
      color:#aaa;
    }

    /* Glass Card */

    .glass-card{
      background:var(--glass);
      border:1px solid var(--border);
      backdrop-filter:blur(12px);
      border-radius:24px;
      transition:.4s;
    }

    .glass-card:hover{
      transform:translateY(-10px);
      border-color:var(--secondary);
      box-shadow:0 20px 40px rgba(0,247,255,.15);
    }

    /* About */

    .about-grid{
      display:grid;
      grid-template-columns:repeat(auto-fit,minmax(280px,1fr));
      gap:30px;
    }

    .about-card{
      padding:35px;
    }

    .about-card h3{
      margin-bottom:15px;
      color:var(--secondary);
    }

    .about-card p{
      color:#c5c5c5;
      line-height:1.8;
    }

    /* Skills */

    .skills-grid{
      display:grid;
      grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
      gap:25px;
    }

    .skill-card{
      padding:30px;
    }

    .skill-card h3{
      margin-bottom:20px;
    }

    .skill{
      margin-bottom:18px;
    }

    .skill span{
      display:block;
      margin-bottom:8px;
    }

    .bar{
      height:10px;
      background:#111;
      border-radius:20px;
      overflow:hidden;
    }

    .bar div{
      height:100%;
      border-radius:20px;
      background:linear-gradient(to right,var(--primary),var(--secondary));
    }

    /* Services */

    .services-grid{
      display:grid;
      grid-template-columns:repeat(auto-fit,minmax(260px,1fr));
      gap:25px;
    }

    .service-card{
      padding:35px;
      text-align:center;
    }

    .service-card i{
      font-size:45px;
      margin-bottom:20px;
      color:var(--secondary);
    }

    /* Projects */

    .projects-grid{
      display:grid;
      grid-template-columns:repeat(auto-fit,minmax(320px,1fr));
      gap:30px;
    }

    .project-card{
      overflow:hidden;
    }

    .project-card img{
      width:100%;
      height:220px;
      object-fit:cover;
    }

    .project-content{
      padding:25px;
    }

    .project-content h3{
      margin-bottom:15px;
    }

    .project-content p{
      color:#c4c4c4;
      margin-bottom:20px;
      line-height:1.7;
    }

    .project-buttons{
      display:flex;
      gap:15px;
    }

    /* Timeline */

    .timeline{
      position:relative;
      max-width:900px;
      margin:auto;
    }

    .timeline::before{
      content:'';
      position:absolute;
      left:50%;
      width:3px;
      height:100%;
      background:linear-gradient(var(--primary),var(--secondary));
    }

    .timeline-item{
      width:50%;
      padding:30px;
      position:relative;
    }

    .timeline-item:nth-child(odd){
      left:0;
      text-align:right;
    }

    .timeline-item:nth-child(even){
      left:50%;
    }

    .timeline-content{
      padding:25px;
    }

    /* Testimonials */

    .testimonial-grid{
      display:grid;
      grid-template-columns:repeat(auto-fit,minmax(280px,1fr));
      gap:25px;
    }

    .testimonial-card{
      padding:30px;
    }

    .testimonial-card p{
      color:#ccc;
      line-height:1.8;
      margin-bottom:20px;
    }

    /* Contact */

    .contact-grid{
      display:grid;
      grid-template-columns:repeat(auto-fit,minmax(320px,1fr));
      gap:30px;
    }

    .contact-form{
      padding:35px;
    }

    .contact-form input,
    .contact-form textarea{
      width:100%;
      padding:15px;
      margin-bottom:20px;
      background:#0d1229;
      border:none;
      border-radius:14px;
      color:#fff;
      outline:none;
    }

    .contact-form textarea{
      resize:none;
      height:150px;
    }

    iframe{
      width:100%;
      border:none;
      border-radius:24px;
      min-height:400px;
    }

    /* Footer */

    footer{
      padding:40px 10%;
      border-top:1px solid rgba(255,255,255,0.08);
      text-align:center;
      color:#aaa;
    }

    /* Responsive */

    @media(max-width:900px){

      .hero-text h1{
        font-size:45px;
      }

      .timeline::before{
        left:20px;
      }

      .timeline-item{
        width:100%;
        left:0 !important;
        text-align:left !important;
        padding-left:60px;
      }

      nav ul{
        display:none;
      }
    }

  </style>
</head>
<body>

  <div class="bg-blur bg1"></div>
  <div class="bg-blur bg2"></div>

  <!-- Navbar -->

  <header>
    <nav>
      <div class="logo">Maria.dev</div>

      <ul>
        <li><a href="#about">About</a></li>
        <li><a href="#skills">Skills</a></li>
        <li><a href="#services">Services</a></li>
        <li><a href="#projects">Projects</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </nav>
  </header>

  <!-- Hero -->

  <section class="hero">

    <div class="hero-text" data-aos="fade-right">

      <h3>Hello, I'm</h3>

      <h1>
        <span class="gradient-text">
          Mariya Dewan
        </span>
      </h1>

      <div class="typing">
        <span id="typed"></span>
      </div>

      <p>
        Passionate Full Stack Developer, Software Engineer,
        Mobile App Developer, and Machine Learning Research Student
        creating premium modern digital experiences with futuristic UI,
        scalable systems, and intelligent solutions.
      </p>

      <div class="btn-group">
        <a href="#" class="btn btn-primary">Hire Me</a>
        <a href="#projects" class="btn btn-secondary">View Projects</a>
        <a href="#" class="btn btn-secondary">Download CV</a>
      </div>

      <div class="socials">
        <a href="#"><i class="fab fa-github"></i></a>
        <a href="#"><i class="fab fa-linkedin"></i></a>
        <a href="#"><i class="fab fa-facebook"></i></a>
        <a href="#"><i class="fas fa-envelope"></i></a>
      </div>

    </div>

    <div class="hero-image" data-aos="fade-left">
      <img src="https://i.ibb.co/zrWcG0V/developer.png" alt="">
    </div>

  </section>

  <!-- About -->

  <section id="about">

    <div class="section-title">
      <h2>About Me</h2>
      <p>Professional summary and research interests</p>
    </div>

    <div class="about-grid">

      <div class="glass-card about-card">
        <h3>Professional Summary</h3>
        <p>
          I specialize in creating high-performance websites,
          scalable applications, modern UI/UX systems,
          and AI-powered digital products.
        </p>
      </div>

      <div class="glass-card about-card">
        <h3>Experience</h3>
        <p>
          Working with modern technologies including React,
          Next.js, Node.js, Flutter, Laravel, and Machine Learning.
        </p>
      </div>

      <div class="glass-card about-card">
        <h3>Research Interest</h3>
        <p>
          Machine Learning, Artificial Intelligence,
          Automation Systems, Deep Learning, and Smart Applications.
        </p>
      </div>

    </div>

  </section>

  <!-- Skills -->

  <section id="skills">

    <div class="section-title">
      <h2>Skills & Technologies</h2>
      <p>Modern technologies and frameworks</p>
    </div>

    <div class="skills-grid">

      <div class="glass-card skill-card">

        <h3>Frontend</h3>

        <div class="skill">
          <span>React.js</span>
          <div class="bar"><div style="width:95%"></div></div>
        </div>

        <div class="skill">
          <span>Next.js</span>
          <div class="bar"><div style="width:90%"></div></div>
        </div>

        <div class="skill">
          <span>JavaScript</span>
          <div class="bar"><div style="width:92%"></div></div>
        </div>

      </div>

      <div class="glass-card skill-card">

        <h3>Backend</h3>

        <div class="skill">
          <span>Node.js</span>
          <div class="bar"><div style="width:88%"></div></div>
        </div>

        <div class="skill">
          <span>Laravel</span>
          <div class="bar"><div style="width:85%"></div></div>
        </div>

        <div class="skill">
          <span>PHP</span>
          <div class="bar"><div style="width:82%"></div></div>
        </div>

      </div>

      <div class="glass-card skill-card">

        <h3>AI & Mobile</h3>

        <div class="skill">
          <span>Flutter</span>
          <div class="bar"><div style="width:90%"></div></div>
        </div>

        <div class="skill">
          <span>Machine Learning</span>
          <div class="bar"><div style="width:84%"></div></div>
        </div>

        <div class="skill">
          <span>MongoDB</span>
          <div class="bar"><div style="width:80%"></div></div>
        </div>

      </div>

    </div>

  </section>

  <!-- Services -->

  <section id="services">

    <div class="section-title">
      <h2>Services</h2>
      <p>Premium development solutions</p>
    </div>

    <div class="services-grid">

      <div class="glass-card service-card">
        <i class="fas fa-code"></i>
        <h3>Full Stack Development</h3>
      </div>

      <div class="glass-card service-card">
        <i class="fas fa-mobile-screen"></i>
        <h3>Mobile App Development</h3>
      </div>

      <div class="glass-card service-card">
        <i class="fas fa-palette"></i>
        <h3>UI/UX Design</h3>
      </div>

      <div class="glass-card service-card">
        <i class="fas fa-brain"></i>
        <h3>Machine Learning</h3>
      </div>

      <div class="glass-card service-card">
        <i class="fas fa-robot"></i>
        <h3>AI Automation</h3>
      </div>

      <div class="glass-card service-card">
        <i class="fas fa-chart-line"></i>
        <h3>SEO Optimization</h3>
      </div>

    </div>

  </section>

  <!-- Projects -->

  <section id="projects">

    <div class="section-title">
      <h2>Projects Showcase</h2>
      <p>Modern premium projects</p>
    </div>

    <div class="projects-grid">

      <div class="glass-card project-card">

        <img src="https://images.unsplash.com/photo-1555066931-4365d14bab8c?q=80&w=1470&auto=format&fit=crop" alt="">

        <div class="project-content">

          <h3>AI Dashboard</h3>

          <p>
            Modern AI analytics dashboard with React,
            Node.js, Machine Learning integration,
            and futuristic UI design.
          </p>

          <div class="project-buttons">
            <a href="#" class="btn btn-primary">Live Demo</a>
            <a href="#" class="btn btn-secondary">GitHub</a>
          </div>

        </div>

      </div>

      <div class="glass-card project-card">

        <img src="https://images.unsplash.com/photo-1498050108023-c5249f4df085?q=80&w=1472&auto=format&fit=crop" alt="">

        <div class="project-content">

          <h3>Portfolio Website</h3>

          <p>
            Premium animated developer portfolio
            using modern UI/UX trends and glassmorphism.
          </p>

          <div class="project-buttons">
            <a href="#" class="btn btn-primary">Live Demo</a>
            <a href="#" class="btn btn-secondary">GitHub</a>
          </div>

        </div>

      </div>

    </div>

  </section>

  <!-- Timeline -->

  <section>

    <div class="section-title">
      <h2>Experience & Education</h2>
      <p>Professional journey</p>
    </div>

    <div class="timeline">

      <div class="timeline-item">
        <div class="glass-card timeline-content">
          <h3>Software Engineer</h3>
          <p>2024 - Present</p>
        </div>
      </div>

      <div class="timeline-item">
        <div class="glass-card timeline-content">
          <h3>Machine Learning Research</h3>
          <p>AI & Deep Learning Research Projects</p>
        </div>
      </div>

    </div>

  </section>

  <!-- Testimonials -->

  <section>

    <div class="section-title">
      <h2>Testimonials</h2>
      <p>What clients say</p>
    </div>

    <div class="testimonial-grid">

      <div class="glass-card testimonial-card">
        <p>
          “Amazing developer with premium UI/UX skills.
          Delivered exceptional work.”
        </p>
        <h4>— Client Review</h4>
      </div>

      <div class="glass-card testimonial-card">
        <p>
          “Professional, creative, and highly skilled in
          modern web technologies.”
        </p>
        <h4>— Startup Founder</h4>
      </div>

    </div>

  </section>

  <!-- Contact -->

  <section id="contact">

    <div class="section-title">
      <h2>Contact Me</h2>
      <p>Let’s build something amazing together</p>
    </div>

    <div class="contact-grid">

      <div class="glass-card contact-form">

        <input type="text" placeholder="Your Name">
        <input type="email" placeholder="Your Email">
        <textarea placeholder="Your Message"></textarea>

        <button class="btn btn-primary">
          Send Message
        </button>

      </div>

      <iframe
      src="https://maps.google.com/maps?q=Dhaka&t=&z=13&ie=UTF8&iwloc=&output=embed">
      </iframe>

    </div>

  </section>

  <!-- Footer -->

  <footer>
    <p>
      © 2026 Mariya Dewan | Full Stack Developer & ML Research Student
    </p>
  </footer>

  <!-- Typed JS -->

  <script src="https://cdn.jsdelivr.net/npm/typed.js@2.0.12"></script>

  <!-- AOS -->

  <script src="https://unpkg.com/aos@2.3.4/dist/aos.js"></script>

  <script>

    AOS.init({
      duration:1000,
      once:true
    });

    var typed = new Typed("#typed",{
      strings:[
        "Full Stack Developer",
        "Software Engineer",
        "Mobile App Developer",
        "Machine Learning Researcher"
      ],
      typeSpeed:60,
      backSpeed:40,
      loop:true
    });

  </script>

</body>
</html>
