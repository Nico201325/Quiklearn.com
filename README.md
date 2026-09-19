# Quiklearn.com
an website that uses ai to help you understand your lessons, quizzes, and assignments
<!doctype html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Lantern — Study AI</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Source+Serif+4:wght@400;600;700&family=IBM+Plex+Sans:wght@400;500;600;700&display=swap" rel="stylesheet" />
  <link rel="stylesheet" href="/styles.css" />
</head>
<body>
  <div id="auth-screen" class="auth-screen">
    <div class="auth-card">
      <div class="brand">
        <div class="brand-mark">L</div>
        <div>
          <h1>Lantern</h1>
          <p>Study with AI, keep your notes, and save your progress.</p>
        </div>
      </div>

      <div class="auth-toggle">
        <button class="tab active" data-mode="login" type="button">Login</button>
        <button class="tab" data-mode="register" type="button">Create account</button>
      </div>

      <form id="login-form" class="auth-form active">
        <label>
          Username
          <input type="text" name="username" autocomplete="username" required />
        </label>
        <label>
          Password
          <input type="password" name="password" autocomplete="current-password" required />
        </label>
        <button type="submit">Login</button>
      </form>

      <form id="register-form" class="auth-form">
        <label>
          Username
          <input type="text" name="username" autocomplete="username" required />
        </label>
        <label>
          Password
          <input type="password" name="password" autocomplete="new-password" required />
        </label>
        <button type="submit">Create account</button>
      </form>

      <div id="auth-message" class="auth-message"></div>
    </div>
  </div>

  <div id="app-shell" class="app-shell hidden">
    <aside class="sidebar">
      <div class="sidebar-header">
        <div class="brand">
          <div class="brand-mark">L</div>
          <div>
            <h2>Lantern</h2>
          </div>
        </div>
        <button id="logout-button" class="secondary-btn" type="button">Logout</button>
      </div>

      <div class="section">
        <div class="section-top">
          <h3>Study sessions</h3>
          <button id="new-session-button" type="button">New</button>
        </div>
        <div id="session-list" class="session-list"></div>
      </div>
    </aside>

    <main class="workspace">
      <header class="topbar">
        <div>
          <p class="topbar-label">Signed in as</p>
          <h3 id="user-name">User</h3>
        </div>
        <div class="top-actions">
          <button id="save-session-button" class="primary-btn" type="button">Save session</button>
        </div>
      </header>

      <div class="layout">
        <section class="panel">
          <div>
            <h2>What are you working on?</h2>
            <p class="hint">Paste notes, assignment instructions, or quiz questions.</p>
          </div>

          <div class="mode-group" id="mode-group">
            <label class="mode-option active" data-mode="lesson">
              <input type="radio" name="mode" value="lesson" checked />
              <span>
                <span class="m-title">Understand a lesson</span>
                <span class="m-desc">Break down concepts and explain examples.</span>
              </span>
            </label>

            <label class="mode-option" data-mode="assignment">
              <input type="radio" name="mode" value="assignment" />
              <span>
                <span class="m-title">Work through an assignment</span>
                <span class="m-desc">Get hints and guidance without finished answers.</span>
              </span>
            </label>

            <label class="mode-option" data-mode="quiz">
              <input type="radio" name="mode" value="quiz" />
              <span>
                <span class="m-title">Practice for a quiz</span>
                <span class="m-desc">Check reasoning and practice one question at a time.</span>
              </span>
            </label>
          </div>

          <textarea id="material" placeholder="Paste your lesson notes, assignment prompt, or quiz question here…"></textarea>
          <div class="char-count" id="char-count">0 characters</div>
        </section>

        <section class="chat">
          <div class="error-banner" id="error-banner" style="display:none;"></div>
          <div class="thread" id="thread">
            <div class="empty-state" id="empty-state">
              <div class="lamp">◐</div>
              <h3>Ask your first question</h3>
              <p>Drop your material on the left, then ask what needs explaining.</p>
              <div class="suggestions">
                <button class="suggestion-chip" type="button" data-fill="Can you explain this in simpler terms?">Explain simply</button>
                <button class="suggestion-chip" type="button" data-fill="What is the key idea I should remember here?">Key idea</button>
                <button class="suggestion-chip" type="button" data-fill="Can you walk me through this step by step?">Step by step</button>
              </div>
            </div>
          </div>

          <form id="composer">
            <textarea id="question" rows="1" placeholder="Ask a question about your lesson, assignment, or quiz…"></textarea>
            <button id="send" type="submit">Ask</button>
          </form>
        </section>
      </div>
    </main>
  </div>

  <script src="/app.js"></script>
</body>
</html>
