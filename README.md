# Marco
<!doctype html>
<html lang="es" class="h-full">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>¿Quieres ser mi San Valentín?</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="/_sdk/element_sdk.js"></script>
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,600;1,400&amp;family=Inter:wght@300;400;500&amp;display=swap" rel="stylesheet">
  <style>
    body {
      box-sizing: border-box;
    }
    
    .font-cormorant {
      font-family: 'Cormorant Garamond', serif;
    }
    
    .font-inter {
      font-family: 'Inter', sans-serif;
    }
    
    @keyframes float {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-15px); }
    }
    
    @keyframes gentle-pulse {
      0%, 100% { transform: scale(1); opacity: 0.6; }
      50% { transform: scale(1.05); opacity: 0.8; }
    }
    
    @keyframes fade-in {
      0% { opacity: 0; transform: translateY(20px); }
      100% { opacity: 1; transform: translateY(0); }
    }
    
    @keyframes petal-fall {
      0% { transform: translateY(-20%) rotate(0deg); opacity: 0.8; }
      100% { transform: translateY(120%) rotate(180deg); opacity: 0; }
    }
    
    @keyframes soft-bounce {
      0% { transform: scale(0.95); opacity: 0; }
      60% { transform: scale(1.02); }
      100% { transform: scale(1); opacity: 1; }
    }
    
    @keyframes subtle-wiggle {
      0%, 100% { transform: translateX(0); }
      25% { transform: translateX(-2px); }
      75% { transform: translateX(2px); }
    }
    
    .float-animation {
      animation: float 6s ease-in-out infinite;
    }
    
    .gentle-pulse {
      animation: gentle-pulse 3s ease-in-out infinite;
    }
    
    .fade-in {
      animation: fade-in 1.2s ease-out forwards;
    }
    
    .soft-bounce {
      animation: soft-bounce 0.8s cubic-bezier(0.34, 1.56, 0.64, 1);
    }
    
    .subtle-wiggle {
      animation: subtle-wiggle 0.4s ease-in-out;
    }
    
    .no-button {
      transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
      cursor: pointer;
    }
    
    .yes-button {
      transition: all 0.3s ease;
    }
    
    .yes-button:hover {
      transform: translateY(-2px);
      box-shadow: 0 8px 20px rgba(199, 161, 122, 0.25);
    }
    
    .heart-bg {
      position: absolute;
      opacity: 0.06;
      pointer-events: none;
    }
    
    .petal {
      position: fixed;
      pointer-events: none;
      z-index: 100;
    }
    
    .success-overlay {
      backdrop-filter: blur(15px);
    }
    
    .organic-line {
      stroke: currentColor;
      fill: none;
      stroke-width: 1.5;
      stroke-linecap: round;
      opacity: 0.15;
    }
  </style>
  <style>@view-transition { navigation: auto; }</style>
  <script src="/_sdk/data_sdk.js" type="text/javascript"></script>
 </head>
 <body class="h-full font-inter overflow-hidden">
  <div id="app" class="relative h-full w-full overflow-hidden flex flex-col items-center justify-center p-6" style="background: linear-gradient(180deg, #F5EFE6 0%, #F9F5F0 50%, #F5EFE6 100%);"><!-- Organic Lines Background -->
   <svg class="absolute inset-0 w-full h-full pointer-events-none" style="opacity: 0.08;"><path class="organic-line" d="M 0,150 Q 200,100 400,150 T 800,150" stroke="#C7A17A" /> <path class="organic-line" d="M 0,400 Q 150,350 300,400 T 600,400" stroke="#D4A373" /> <path class="organic-line" d="M 0,600 Q 250,550 500,600 T 1000,600" stroke="#C7A17A" />
   </svg><!-- Delicate Hearts Background -->
   <div id="hearts-container" class="absolute inset-0 overflow-hidden pointer-events-none">
    <svg class="heart-bg float-animation" style="top: 8%; left: 10%; width: 45px;" viewbox="0 0 24 24" fill="#D4A373"><path d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z" />
    </svg>
    <svg class="heart-bg float-animation" style="top: 20%; right: 12%; width: 35px; animation-delay: 1s;" viewbox="0 0 24 24" fill="#C7A17A"><path d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z" />
    </svg>
    <svg class="heart-bg float-animation" style="top: 65%; left: 8%; width: 40px; animation-delay: 2s;" viewbox="0 0 24 24" fill="#E3D5CA"><path d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z" />
    </svg>
    <svg class="heart-bg float-animation" style="top: 78%; right: 10%; width: 32px; animation-delay: 1.5s;" viewbox="0 0 24 24" fill="#D4A373"><path d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z" />
    </svg>
   </div><!-- Main Content -->
   <div id="main-content" class="relative z-10 flex flex-col items-center text-center max-w-sm fade-in"><!-- Simple Heart -->
    <div class="gentle-pulse mb-8">
     <svg width="80" height="80" viewbox="0 0 24 24" fill="none" stroke="#C7A17A" stroke-width="1.5"><path d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z" />
     </svg>
    </div><!-- Question -->
    <h1 id="main-question" class="font-cormorant text-4xl md:text-5xl italic leading-relaxed mb-6" style="color: #6B4F3F; font-weight: 400;">¿Quieres ser mi San Valentín?</h1><!-- Subtitle -->
    <p class="font-inter text-base mb-12 tracking-wide" style="color: #8D7461; font-weight: 300;">Solo hay una respuesta correcta…</p><!-- Buttons Container -->
    <div id="buttons-container" class="relative w-full h-48 flex flex-col items-center gap-6"><!-- YES Button --> <button id="yes-button" class="yes-button px-14 py-4 rounded-full shadow-md focus:outline-none focus:ring-2 focus:ring-offset-2 font-inter tracking-wide" style="background-color: #C7A17A; color: #FFFFFF; font-size: 18px; font-weight: 500; letter-spacing: 0.5px;"> SÍ </button> <!-- NO Button --> <button id="no-button" class="no-button absolute px-12 py-3.5 rounded-full shadow-sm focus:outline-none font-inter tracking-wide" style="background-color: #E3D5CA; color: #8D7461; font-size: 16px; font-weight: 400; bottom: 0; left: 50%; transform: translateX(-50%);"> NO </button>
    </div><!-- Hint -->
    <p id="hint-text" class="font-inter text-sm mt-8 tracking-wide" style="color: #B8A394; font-weight: 300;"></p>
   </div><!-- Success Overlay -->
   <div id="success-overlay" class="fixed inset-0 success-overlay flex flex-col items-center justify-center z-50 hidden" style="background-color: rgba(245, 239, 230, 0.95);">
    <div id="success-content" class="text-center p-8">
     <div class="gentle-pulse mb-8">
      <svg width="100" height="100" viewbox="0 0 24 24" fill="#C7A17A"><path d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z" />
      </svg>
     </div>
     <h2 id="success-message" class="font-cormorant text-4xl italic mb-4 soft-bounce" style="color: #6B4F3F; font-weight: 400; animation-delay: 0.2s;">Sabía que dirías que sí.</h2>
     <p class="text-3xl soft-bounce" style="animation-delay: 0.4s;">🤍</p>
    </div>
   </div>
  </div>
  <script>
    const defaultConfig = {
      main_question: '¿Quieres ser mi San Valentín?',
      yes_button_text: 'SÍ',
      no_button_text: 'NO',
      success_message: 'Sabía que dirías que sí.',
      primary_color: '#F5EFE6',
      secondary_color: '#C7A17A',
      text_color: '#6B4F3F',
      button_color: '#C7A17A',
      accent_color: '#E3D5CA',
      font_family: 'Inter',
      font_size: 16
    };
    
    let escapeCount = 0;
    const messages = [
      '',
      '',
      '',
      '',
      '',
      ''
    ];
    
    function getRandomPosition(button, container) {
      const containerRect = container.getBoundingClientRect();
      const buttonRect = button.getBoundingClientRect();
      
      const maxX = containerRect.width - buttonRect.width - 20;
      const maxY = containerRect.height - buttonRect.height - 20;
      
      const randomX = Math.max(10, Math.random() * maxX);
      const randomY = Math.max(10, Math.random() * maxY);
      
      return { x: randomX, y: randomY };
    }
    
    function moveNoButton() {
      const noButton = document.getElementById('no-button');
      const container = document.getElementById('buttons-container');
      
      if (!noButton || !container) return;
      
      const pos = getRandomPosition(noButton, container);
      
      noButton.style.position = 'absolute';
      noButton.style.left = pos.x + 'px';
      noButton.style.top = pos.y + 'px';
      noButton.style.transform = 'none';
      
      // Add subtle wiggle animation
      noButton.classList.add('subtle-wiggle');
      setTimeout(() => {
        noButton.classList.remove('subtle-wiggle');
      }, 400);
      
      // Update hint text (kept minimal/empty for elegant design)
      escapeCount++;
      
      // Make NO button slightly smaller after many attempts
      if (escapeCount > 6) {
        const scale = Math.max(0.7, 1 - (escapeCount - 6) * 0.04);
        noButton.style.transform = `scale(${scale})`;
      }
    }
    
    function createPetals() {
      const colors = ['#D4A373', '#C7A17A', '#E3D5CA', '#F5EFE6'];
      const container = document.body;
      
      for (let i = 0; i < 30; i++) {
        setTimeout(() => {
          const petal = document.createElement('div');
          petal.className = 'petal';
          petal.style.left = Math.random() * 100 + '%';
          petal.style.top = '-10px';
          
          // Create simple heart shape
          const heart = document.createElementNS('http://www.w3.org/2000/svg', 'svg');
          heart.setAttribute('width', '12');
          heart.setAttribute('height', '12');
          heart.setAttribute('viewBox', '0 0 24 24');
          heart.style.opacity = '0.6';
          
          const path = document.createElementNS('http://www.w3.org/2000/svg', 'path');
          path.setAttribute('d', 'M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z');
          path.setAttribute('fill', colors[Math.floor(Math.random() * colors.length)]);
          
          heart.appendChild(path);
          petal.appendChild(heart);
          
          petal.style.animation = `petal-fall ${Math.random() * 2 + 3}s linear forwards`;
          
          container.appendChild(petal);
          
          setTimeout(() => petal.remove(), 5000);
        }, i * 100);
      }
    }
    
    function showSuccess() {
      const overlay = document.getElementById('success-overlay');
      if (overlay) {
        overlay.classList.remove('hidden');
        createPetals();
        
        // Add gentle falling petals periodically
        setInterval(createPetals, 4000);
      }
    }
    
    function initializeButtons() {
      const noButton = document.getElementById('no-button');
      const yesButton = document.getElementById('yes-button');
      
      if (noButton) {
        noButton.addEventListener('mouseenter', moveNoButton);
        noButton.addEventListener('touchstart', (e) => {
          e.preventDefault();
          moveNoButton();
        });
        noButton.addEventListener('click', (e) => {
          e.preventDefault();
          moveNoButton();
        });
      }
      
      if (yesButton) {
        yesButton.addEventListener('click', showSuccess);
      }
    }
    
    async function onConfigChange(config) {
      const customFont = config.font_family || defaultConfig.font_family;
      const baseFontStack = 'Inter, sans-serif';
      const serifFontStack = 'Cormorant Garamond, serif';
      const baseSize = config.font_size || defaultConfig.font_size;
      
      // Update main question
      const questionEl = document.getElementById('main-question');
      if (questionEl) {
        questionEl.textContent = config.main_question || defaultConfig.main_question;
        questionEl.style.fontFamily = `${serifFontStack}, ${customFont}`;
        questionEl.style.fontSize = `${baseSize * 2.5}px`;
        questionEl.style.color = config.text_color || defaultConfig.text_color;
      }
      
      // Update YES button
      const yesBtn = document.getElementById('yes-button');
      if (yesBtn) {
        yesBtn.textContent = config.yes_button_text || defaultConfig.yes_button_text;
        yesBtn.style.fontFamily = `${customFont}, ${baseFontStack}`;
        yesBtn.style.fontSize = `${baseSize * 1.125}px`;
        yesBtn.style.backgroundColor = config.button_color || defaultConfig.button_color;
      }
      
      // Update NO button
      const noBtn = document.getElementById('no-button');
      if (noBtn) {
        noBtn.textContent = config.no_button_text || defaultConfig.no_button_text;
        noBtn.style.fontFamily = `${customFont}, ${baseFontStack}`;
        noBtn.style.fontSize = `${baseSize}px`;
        noBtn.style.backgroundColor = config.accent_color || defaultConfig.accent_color;
      }
      
      // Update success message
      const successMsg = document.getElementById('success-message');
      if (successMsg) {
        successMsg.textContent = config.success_message || defaultConfig.success_message;
        successMsg.style.fontFamily = `${serifFontStack}, ${customFont}`;
        successMsg.style.fontSize = `${baseSize * 2.5}px`;
        successMsg.style.color = config.text_color || defaultConfig.text_color;
      }
      
      // Update hint text font
      const hintText = document.getElementById('hint-text');
      if (hintText) {
        hintText.style.fontFamily = `${customFont}, ${baseFontStack}`;
        hintText.style.fontSize = `${baseSize * 0.875}px`;
      }
      
      // Update background
      const app = document.getElementById('app');
      if (app) {
        const bgColor = config.primary_color || defaultConfig.primary_color;
        app.style.background = `linear-gradient(180deg, ${bgColor} 0%, ${bgColor}dd 50%, ${bgColor} 100%)`;
      }
    }
    
    // Initialize SDK
    if (window.elementSdk) {
      window.elementSdk.init({
        defaultConfig,
        onConfigChange,
        mapToCapabilities: (config) => ({
          recolorables: [
            {
              get: () => config.primary_color || defaultConfig.primary_color,
              set: (value) => window.elementSdk.setConfig({ primary_color: value })
            },
            {
              get: () => config.secondary_color || defaultConfig.secondary_color,
              set: (value) => window.elementSdk.setConfig({ secondary_color: value })
            },
            {
              get: () => config.text_color || defaultConfig.text_color,
              set: (value) => window.elementSdk.setConfig({ text_color: value })
            },
            {
              get: () => config.button_color || defaultConfig.button_color,
              set: (value) => window.elementSdk.setConfig({ button_color: value })
            },
            {
              get: () => config.accent_color || defaultConfig.accent_color,
              set: (value) => window.elementSdk.setConfig({ accent_color: value })
            }
          ],
          borderables: [],
          fontEditable: {
            get: () => config.font_family || defaultConfig.font_family,
            set: (value) => window.elementSdk.setConfig({ font_family: value })
          },
          fontSizeable: {
            get: () => config.font_size || defaultConfig.font_size,
            set: (value) => window.elementSdk.setConfig({ font_size: value })
          }
        }),
        mapToEditPanelValues: (config) => new Map([
          ['main_question', config.main_question || defaultConfig.main_question],
          ['yes_button_text', config.yes_button_text || defaultConfig.yes_button_text],
          ['no_button_text', config.no_button_text || defaultConfig.no_button_text],
          ['success_message', config.success_message || defaultConfig.success_message]
        ])
      });
    }
    
    // Initialize buttons
    initializeButtons();
  </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9c8c5323a5924e2f',t:'MTc3MDIzMDcyMy4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
