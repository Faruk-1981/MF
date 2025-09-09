<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width,initial-scale=1.0">
  <title>Student Portfolio</title>
  <style>
    * {margin:0;padding:0;box-sizing:border-box;font-family:Arial,sans-serif;}
    body {line-height:1.6;background:#f9f9f9;color:#333;}
    header {background:#333;color:#fff;padding:1rem;position:sticky;top:0;z-index:1000;}
    nav {display:flex;justify-content:space-between;align-items:center;}
    .nav-links {list-style:none;display:flex;gap:1rem;}
    .nav-links a {color:white;text-decoration:none;}
    .nav-links a:hover {text-decoration:underline;}
    .hero {height:100vh;display:flex;justify-content:center;align-items:center;background:#444;color:white;text-align:center;}
    .about, .projects, .contact {padding:2rem;}
    .about img {max-width:200px;border-radius:50%;margin:1rem;}
    .project-card, .blog-post, .responsive-demo {background:white;padding:1rem;margin:1rem 0;border-radius:8px;box-shadow:0 0 5px rgba(0,0,0,0.1);}
    form input, form textarea {width:100%;padding:10px;margin:10px 0;border:1px solid #ccc;border-radius:5px;}
    form button {background:#333;color:white;padding:10px;border:none;border-radius:5px;cursor:pointer;}
    form button:hover {background:#555;}
    footer {text-align:center;padding:1rem;background:#333;color:white;}
    /* Quiz styles */
    .quiz-container {background:white;padding:20px;border-radius:10px;max-width:500px;margin:auto;box-shadow:0 0 10px rgba(0,0,0,0.2);}
    .quiz-container ul {list-style:none;margin:15px 0;}
    .quiz-container li {margin:10px 0;}
    .quiz-container button {background:#333;color:white;padding:10px;border:none;border-radius:5px;cursor:pointer;}
    .quiz-container button:hover {background:#555;}
    .result {font-size:18px;font-weight:bold;text-align:center;margin-top:10px;}
  </style>
</head>
<body>

  <!-- Navbar -->
  <header>
    <nav>
      <div class="logo">MyPortfolio</div>
      <ul class="nav-links">
        <li><a href="#home">Home</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#projects">Projects</a></li>
        <li><a href="#quiz">Quiz</a></li>
        <li><a href="#blog">Blog</a></li>
        <li><a href="#responsive">Responsive Demo</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </nav>
  </header>

  <!-- Hero -->
  <section id="home" class="hero">
    <div>
      <h1>Hello, I'm <span>MR__MOHAMMED FARUK</span></h1>
      <p>I am the student</p>
      <a href="#projects" class="btn">View My Work</a>
    </div>
  </section>

  <!-- About -->
  <section id="about" class="about">
    <h2>About Me</h2>
    <div>
      <img src="IMG_20250908_191144_1.jpg" alt="Profile Photo">
      <p>
        I am a student enthusiastic about technology and design. 
        I love building interactive, user-friendly web applications 
        and exploring new tools in the tech world.
      </p>
    </div>
  </section>

  <!-- Projects -->
  <section id="projects" class="projects">
    <h2>My Projects</h2>
    <div class="project-card">
      <h3>Project 1</h3>
      <p>A simple responsive website.</p>
    </div>
    <div class="project-card">
      <h3>Project 2</h3>
      <p>JavaScript-based quiz app (see <a href="#quiz">Quiz Section</a>).</p>
    </div>
    <div class="project-card">
      <h3>Project 3</h3>
      <p>Personal blog (see <a href="#blog">Blog Section</a>).</p>
    </div>
  </section>

  <!-- Quiz Section -->
  <section id="quiz" class="projects">
    <h2>Quiz App</h2>
    <div class="quiz-container" id="quizBox">
      <h3 id="question">Question text</h3>
      <ul>
        <li><label><input type="radio" name="answer" class="answer" id="a"><span id="a_text">A</span></label></li>
        <li><label><input type="radio" name="answer" class="answer" id="b"><span id="b_text">B</span></label></li>
        <li><label><input type="radio" name="answer" class="answer" id="c"><span id="c_text">C</span></label></li>
        <li><label><input type="radio" name="answer" class="answer" id="d"><span id="d_text">D</span></label></li>
      </ul>
      <button id="submit">Submit</button>
      <div class="result" id="result"></div>
    </div>
  </section>

  <!-- Blog Section -->
  <section id="blog" class="projects">
    <h2>My Blog</h2>
    <div class="blog-post">
      <h3>Sample Post</h3>
      <small>2025-09-08</small>
      <p>Welcome to my blog! Posts will appear here dynamically.</p>
    </div>
    <div id="postsContainer"></div>
  </section>

  <!-- Responsive Layout Demo -->
  <section id="responsive" class="projects">
    <h2>Responsive Layout Demo</h2>
    <div class="responsive-demo">
      <h3>Main Content</h3>
      <p>This is the main content area. Resize the window to see the responsive effect.</p>
    </div>
    <div class="responsive-demo">
      <h3>Sidebar</h3>
      <p>This is a sidebar with some extra information.</p>
    </div>
  </section>

  <!-- Contact -->
  <section id="contact" class="contact">
    <h2>Contact Me</h2>
    <form id="contact-form">
      <input type="text" name="user_name" placeholder="Your Name" required>
      <input type="email" name="user_email" placeholder="Your Email" required>
      <textarea name="message" placeholder="Your Message" required></textarea>
      <button type="submit">Send</button>
    </form>
    <p id="form-status"></p>
  </section>

  <!-- Footer -->
  <footer>
    <p>&copy; 2025 MOHAMMED FARUK| All Rights Reserved</p>
  </footer>

  <!-- JS -->
  <script>
    // QUIZ APP
    const quizData = [
      {question:"Which HTML attribute is used to define inline styles?",a:"font",b:"class",c:"styles",d:"style",correct:"d"},
      {question:"Which language is used for styling web pages?",a:"HTML",b:"JQuery",c:"CSS",d:"XML",correct:"c"},
      {question:"Which is not a JavaScript Framework?",a:"React",b:"Angular",c:"Vue",d:"Django",correct:"d"},
      {question:"Which is used for database?",a:"PHP",b:"MySQL",c:"HTML",d:"CSS",correct:"b"}
    ];
    const quiz=document.getElementById("quizBox");
    const answerEls=document.querySelectorAll(".answer");
    const questionEl=document.getElementById("question");
    const a_text=document.getElementById("a_text");
    const b_text=document.getElementById("b_text");
    const c_text=document.getElementById("c_text");
    const d_text=document.getElementById("d_text");
    const submitBtn=document.getElementById("submit");
    const resultEl=document.getElementById("result");
    let currentQuiz=0,score=0;
    loadQuiz();
    function loadQuiz(){deselect();let data=quizData[currentQuiz];
      questionEl.innerText=data.question;a_text.innerText=data.a;b_text.innerText=data.b;c_text.innerText=data.c;d_text.innerText=data.d;}
    function deselect(){answerEls.forEach(el=>el.checked=false);}
    function getSelected(){let ans;answerEls.forEach(el=>{if(el.checked){ans=el.id}});return ans;}
    submitBtn.addEventListener("click",()=>{let ans=getSelected();if(ans){if(ans===quizData[currentQuiz].correct){score++;}currentQuiz++;
      if(currentQuiz<quizData.length){loadQuiz();}else{quiz.innerHTML=`<h2>You scored ${score}/${quizData.length}</h2><button onclick="location.reload()">Restart</button>`}}});
    
    // BLOG POSTS DEMO
    function loadPosts(){
      const postsContainer=document.getElementById("postsContainer");
      const posts=JSON.parse(localStorage.getItem("blogPosts"))||[];
      postsContainer.innerHTML="";
      posts.reverse().forEach(post=>{
        const div=document.createElement("div");
        div.classList.add("blog-post");
        div.innerHTML=`<h3>${post.title}</h3><small>${new Date(post.date).toLocaleString()}</small><p>${post.content}</p>`;
        postsContainer.appendChild(div);
      });
    }
    loadPosts();
  </script>
</body>
</html>
