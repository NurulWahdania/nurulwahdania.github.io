---
title: Behind the Scenes
icon: fas fa-cube
order: 4
layout: page
---

<style>
.about-container {
  max-width: 1000px;
  margin: 0 auto;
  padding: 2rem;
}

.hero-section {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  border-radius: 20px;
  padding: 4rem 2rem;
  text-align: center;
  color: white;
  margin-bottom: 3rem;
  box-shadow: 0 20px 60px rgba(102, 126, 234, 0.3);
  position: relative;
  overflow: hidden;
}

.hero-section::before {
  content: '';
  position: absolute;
  top: -50%;
  right: -50%;
  width: 200%;
  height: 200%;
  background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, transparent 70%);
  animation: pulse 15s ease-in-out infinite;
}

@keyframes pulse {
  0%, 100% { transform: translate(0, 0); }
  50% { transform: translate(-20px, -20px); }
}

.hero-section h1 {
  font-size: 2.5rem;
  margin-bottom: 0.5rem;
  font-weight: 700;
  position: relative;
  z-index: 1;
  animation: fadeInDown 0.8s ease-out;
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

.hero-section p {
  font-size: 1.3rem;
  opacity: 0.95;
  position: relative;
  z-index: 1;
  animation: fadeInUp 0.8s ease-out 0.2s both;
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

.stats-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  gap: 1.5rem;
  margin: 3rem 0;
}

.stat-card {
  background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
  padding: 2rem 1rem;
  border-radius: 15px;
  text-align: center;
  color: white;
  box-shadow: 0 10px 30px rgba(245, 87, 108, 0.3);
  transform: translateY(0);
  transition: all 0.3s ease;
  animation: slideIn 0.6s ease-out both;
}

.stat-card:nth-child(1) { animation-delay: 0.1s; }
.stat-card:nth-child(2) { animation-delay: 0.2s; }
.stat-card:nth-child(3) { animation-delay: 0.3s; }
.stat-card:nth-child(4) { animation-delay: 0.4s; }
.stat-card:nth-child(5) { animation-delay: 0.5s; }

@keyframes slideIn {
  from {
    opacity: 0;
    transform: translateY(50px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.stat-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 40px rgba(245, 87, 108, 0.4);
}

.stat-number {
  font-size: 2.5rem;
  font-weight: 700;
  margin-bottom: 0.5rem;
}

.stat-label {
  font-size: 0.9rem;
  opacity: 0.9;
}

.content-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin: 2rem 0;
}

.content-card {
  background: white;
  border-radius: 15px;
  padding: 2rem;
  box-shadow: 0 10px 30px rgba(0,0,0,0.1);
  transition: all 0.3s ease;
  border: 2px solid transparent;
}

.content-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 15px 40px rgba(0,0,0,0.15);
  border-color: #667eea;
}

.content-card h2 {
  font-size: 1.5rem;
  color: #2c3e50;
  margin-bottom: 1.5rem;
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.content-card h2 .icon {
  font-size: 1.8rem;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.fancy-list {
  list-style: none;
  padding: 0;
}

.fancy-list li {
  padding: 0.8rem 0;
  color: #555;
  display: flex;
  align-items: center;
  gap: 1rem;
  border-bottom: 1px solid #f0f0f0;
  transition: all 0.3s ease;
}

.fancy-list li:last-child {
  border-bottom: none;
}

.fancy-list li:hover {
  padding-left: 0.5rem;
  color: #667eea;
}

.fancy-list li::before {
  content: '▸';
  color: #667eea;
  font-weight: bold;
  font-size: 1.2rem;
}

.timeline {
  position: relative;
  padding-left: 2rem;
}

.timeline::before {
  content: '';
  position: absolute;
  left: 0;
  top: 0;
  bottom: 0;
  width: 3px;
  background: linear-gradient(to bottom, #667eea, #764ba2);
}

.timeline-item {
  position: relative;
  margin-bottom: 1.5rem;
  padding-left: 1rem;
}

.timeline-item::before {
  content: '';
  position: absolute;
  left: -2.3rem;
  top: 0.5rem;
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background: #667eea;
  box-shadow: 0 0 0 4px white, 0 0 0 6px #667eea;
}

.timeline-item:hover::before {
  transform: scale(1.3);
  transition: transform 0.3s ease;
}

.contact-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1.5rem;
  margin-top: 1.5rem;
}

.contact-card {
  background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
  padding: 1.5rem;
  border-radius: 15px;
  text-align: center;
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
}

.contact-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  opacity: 0;
  transition: opacity 0.3s ease;
}

.contact-card:hover::before {
  opacity: 1;
}

.contact-card:hover {
  transform: translateY(-5px) scale(1.05);
  box-shadow: 0 15px 40px rgba(102, 126, 234, 0.3);
}

.contact-card a {
  color: #2c3e50;
  text-decoration: none;
  font-weight: 600;
  position: relative;
  z-index: 1;
  transition: color 0.3s ease;
}

.contact-card:hover a {
  color: white;
}

.contact-icon {
  font-size: 2rem;
  margin-bottom: 0.5rem;
  display: block;
}

.hobbies-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1.5rem;
}

.hobby-card {
  background: linear-gradient(135deg, #ffecd2 0%, #fcb69f 100%);
  padding: 2rem;
  border-radius: 15px;
  text-align: center;
  box-shadow: 0 10px 30px rgba(252, 182, 159, 0.3);
  transition: all 0.3s ease;
}

.hobby-card:hover {
  transform: rotate(-2deg) scale(1.05);
}

.hobby-icon {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.hobby-card p {
  color: #5a3e2b;
  font-weight: 600;
  margin: 0;
}

.footer-cta {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  border-radius: 20px;
  padding: 3rem 2rem;
  text-align: center;
  color: white;
  margin-top: 3rem;
  box-shadow: 0 20px 60px rgba(102, 126, 234, 0.3);
}

.footer-cta h2 {
  margin-bottom: 1rem;
  font-size: 2rem;
}

.footer-cta p {
  margin-bottom: 1.5rem;
  opacity: 0.95;
  font-size: 1.1rem;
}

.cta-button {
  display: inline-block;
  background: white;
  color: #667eea;
  padding: 1rem 2rem;
  border-radius: 50px;
  text-decoration: none;
  font-weight: 700;
  transition: all 0.3s ease;
  box-shadow: 0 5px 15px rgba(0,0,0,0.2);
}

.cta-button:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 25px rgba(0,0,0,0.3);
}

.minecraft-section {
  background: linear-gradient(135deg, #8BC34A 0%, #4CAF50 100%);
  border-radius: 20px;
  padding: 3rem 2rem;
  margin: 3rem 0;
  box-shadow: 0 20px 60px rgba(76, 175, 80, 0.3);
  position: relative;
  overflow: hidden;
}

.minecraft-section::before {
  content: '⛏️';
  position: absolute;
  font-size: 15rem;
  opacity: 0.1;
  right: -50px;
  top: -50px;
  animation: float 6s ease-in-out infinite;
}

@keyframes float {
  0%, 100% { transform: translateY(0px); }
  50% { transform: translateY(-20px); }
}

.minecraft-section h2 {
  color: white;
  font-size: 2rem;
  margin-bottom: 2rem;
  text-align: center;
  text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 1rem;
}

.minecraft-builds {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1.5rem;
}

.build-card {
  background: rgba(255, 255, 255, 0.95);
  border-radius: 15px;
  padding: 2rem;
  text-align: center;
  transition: all 0.3s ease;
  box-shadow: 0 5px 15px rgba(0,0,0,0.2);
  border: 3px solid #795548;
}

.build-card:hover {
  transform: translateY(-10px) scale(1.05);
  box-shadow: 0 15px 30px rgba(0,0,0,0.3);
}

.build-icon {
  font-size: 4rem;
  margin-bottom: 1rem;
  display: block;
  animation: bounce 2s ease-in-out infinite;
}

@keyframes bounce {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-10px); }
}

.build-card h3 {
  color: #2c3e50;
  margin-bottom: 0.5rem;
  font-size: 1.3rem;
}

.build-card p {
  color: #555;
  font-size: 0.9rem;
}

.minecraft-quote {
  background: rgba(255, 255, 255, 0.2);
  border-left: 5px solid white;
  padding: 1.5rem;
  margin-top: 2rem;
  border-radius: 10px;
  color: white;
  font-style: italic;
  text-align: center;
  font-size: 1.2rem;
}

@media (max-width: 768px) {
  .hero-section h1 {
    font-size: 2rem;
  }
  
  .stats-grid {
    grid-template-columns: repeat(2, 1fr);
  }
  
  .content-grid {
    grid-template-columns: 1fr;
  }
  
  .minecraft-builds {
    grid-template-columns: 1fr;
  }
}
</style>

<div class="about-container">
  <div class="hero-section">
    <h1>👋 Hi, I'm Nurul Wahdania</h1>
    <p>Information Systems Student | Tech Enthusiast | Creative Builder</p>
  </div>

  <div class="stats-grid">
    <div class="stat-card">
      <div class="stat-number">🎓</div>
      <div class="stat-label">Student</div>
    </div>
    <div class="stat-card">
      <div class="stat-number">💻</div>
      <div class="stat-label">Developer</div>
    </div>
    <div class="stat-card">
      <div class="stat-number">🎨</div>
      <div class="stat-label">Designer</div>
    </div>
    <div class="stat-card">
      <div class="stat-number">🍮</div>
      <div class="stat-label">Pudding Maker</div>
    </div>
    <div class="stat-card">
      <div class="stat-number">⛏️</div>
      <div class="stat-label">Minecraft Builder</div>
    </div>
  </div>

  <div class="content-grid">
    <div class="content-card">
      <h2><span class="icon">🎓</span> Education Journey</h2>
      <div class="timeline">
        <div class="timeline-item">
          <strong>Hasanuddin University</strong><br>
          <small>Information Systems (Current)</small>
        </div>
        <div class="timeline-item">
          <strong>SMA Negeri 13 Sinjai</strong><br>
          <small>High School</small>
        </div>
        <div class="timeline-item">
          <strong>MTS Nurul Hidayah Gantarang</strong><br>
          <small>Junior High School</small>
        </div>
        <div class="timeline-item">
          <strong>MI Miftahul Jannah Gantaran</strong><br>
          <small>Elementary School</small>
        </div>
      </div>
    </div>

    <div class="content-card">
      <h2><span class="icon">💻</span> What I Do</h2>
      <ul class="fancy-list">
        <li>Write about tech and student life</li>
        <li>Build and document projects</li>
        <li>Create digital content</li>
        <li>Connect with fellow learners</li>
        <li>Explore new technologies</li>
      </ul>
    </div>
  </div>

  <div class="minecraft-section">
    <h2><span>⛏️</span> My Minecraft Adventures <span>🏰</span></h2>
    <div class="minecraft-builds">
      <div class="build-card">
        <span class="build-icon">🏡</span>
        <h3>Creative Building</h3>
        <p>Designing unique houses and structures in creative mode</p>
      </div>
      <div class="build-card">
        <span class="build-icon">⚔️</span>
        <h3>Survival Expert</h3>
        <p>Surviving and thriving in challenging worlds</p>
      </div>
      <div class="build-card">
        <span class="build-icon">🌍</span>
        <h3>World Explorer</h3>
        <p>Discovering new biomes and hidden treasures</p>
      </div>
      <div class="build-card">
        <span class="build-icon">🔨</span>
        <h3>Redstone Engineer</h3>
        <p>Creating automated systems and contraptions</p>
      </div>
    </div>
    <div class="minecraft-quote">
      "In Minecraft, just like in coding, creativity has no limits! 🎮✨"
    </div>
  </div>

  <div class="content-card" style="margin: 2rem 0;">
    <h2><span class="icon">🎨</span> My Hobbies & Interests</h2>
    <div class="hobbies-grid">
      <div class="hobby-card">
        <div class="hobby-icon">🍮</div>
        <p>Making puddings for "Nichi" brand</p>
      </div>
      <div class="hobby-card">
        <div class="hobby-icon">🎨</div>
        <p>Design & visual content creation</p>
      </div>
      <div class="hobby-card">
        <div class="hobby-icon">⛏️</div>
        <p>Minecraft building & exploring</p>
      </div>
      <div class="hobby-card">
        <div class="hobby-icon">🎮</div>
        <p>Gaming & creative building</p>
      </div>
    </div>
  </div>

  <div class="content-card">
    <h2><span class="icon">📫</span> Let's Connect</h2>
    <div class="contact-grid">
      <div class="contact-card">
        <span class="contact-icon">📧</span>
        <a href="mailto:nurulwahdania182@gmail.com">Email Me</a>
      </div>
      <div class="contact-card">
        <span class="contact-icon">💼</span>
        <a href="https://github.com/NurulWahdania" target="_blank">GitHub</a>
      </div>
      <div class="contact-card">
        <span class="contact-icon">📷</span>
        <a href="https://www.instagram.com/nurulwahdania_82" target="_blank">Instagram</a>
      </div>
      <div class="contact-card">
        <span class="contact-icon">🔗</span>
        <a href="https://www.linkedin.com/in/nurul-wahdania" target="_blank">LinkedIn</a>
      </div>
    </div>
  </div>

  <div class="footer-cta">
    <h2>✨ Thanks for Visiting!</h2>
    <p>Interested in my work? Check out my latest posts and projects.</p>
    <a href="{{ site.baseurl }}/" class="cta-button">Explore My Blog</a>
  </div>
</div>
