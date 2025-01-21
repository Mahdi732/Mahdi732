<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 200">
  <defs>
    <!-- Futuristic gradient -->
    <linearGradient id="cyberGrad" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#000000">
        <animate attributeName="stop-color" values="#000000;#1a1a1a;#000000" dur="10s" repeatCount="indefinite"/>
      </stop>
      <stop offset="50%" style="stop-color:#0f0f0f">
        <animate attributeName="stop-color" values="#0f0f0f;#000000;#0f0f0f" dur="10s" repeatCount="indefinite"/>
      </stop>
      <stop offset="100%" style="stop-color:#000000">
        <animate attributeName="stop-color" values="#000000;#1a1a1a;#000000" dur="10s" repeatCount="indefinite"/>
      </stop>
    </linearGradient>
    
    <!-- Neon glow effects -->
    <filter id="neonGlow">
      <feGaussianBlur stdDeviation="2" result="coloredBlur"/>
      <feFlood flood-color="#00ff99" flood-opacity="0.5" result="glowColor"/>
      <feComposite in="glowColor" in2="coloredBlur" operator="in" result="softGlow"/>
      <feMerge>
        <feMergeNode in="softGlow"/>
        <feMergeNode in="SourceGraphic"/>
      </feMerge>
    </filter>
    
    <!-- Circuit pattern -->
    <pattern id="circuit" x="0" y="0" width="50" height="50" patternUnits="userSpaceOnUse">
      <path d="M10 10 h30 v30 h-30 z" fill="none" stroke="#00ff99" stroke-width="0.5" opacity="0.1"/>
      <circle cx="25" cy="25" r="2" fill="#00ff99" opacity="0.2"/>
    </pattern>
  </defs>
  
  <!-- Background -->
  <rect width="100%" height="100%" fill="url(#cyberGrad)"/>
  <rect width="100%" height="100%" fill="url(#circuit)">
    <animate attributeName="opacity" values="0.1;0.3;0.1" dur="5s" repeatCount="indefinite"/>
  </rect>
  
  <!-- Animated grid lines -->
  <g stroke="#00ff99" stroke-width="0.5" opacity="0.2">
    <path d="M0 100 h800">
      <animate attributeName="transform" type="translate" values="0 0; 0 20; 0 0" dur="10s" repeatCount="indefinite"/>
    </path>
    <path d="M200 0 v200">
      <animate attributeName="transform" type="translate" values="0 0; 20 0; 0 0" dur="8s" repeatCount="indefinite"/>
    </path>
    <path d="M600 0 v200">
      <animate attributeName="transform" type="translate" values="0 0; -20 0; 0 0" dur="12s" repeatCount="indefinite"/>
    </path>
  </g>
  
  <!-- Floating particles -->
  <g filter="url(#neonGlow)">
    <circle cx="50" cy="50" r="1.5" fill="#00ff99">
      <animate attributeName="cx" values="50;750;50" dur="15s" repeatCount="indefinite"/>
      <animate attributeName="cy" values="50;150;50" dur="10s" repeatCount="indefinite"/>
      <animate attributeName="opacity" values="0;1;0" dur="15s" repeatCount="indefinite"/>
    </circle>
    <circle cx="150" cy="150" r="2" fill="#00ffff">
      <animate attributeName="cx" values="150;650;150" dur="12s" repeatCount="indefinite"/>
      <animate attributeName="cy" values="150;50;150" dur="8s" repeatCount="indefinite"/>
      <animate attributeName="opacity" values="0;1;0" dur="12s" repeatCount="indefinite"/>
    </circle>
    <circle cx="750" cy="100" r="1" fill="#ff00ff">
      <animate attributeName="cx" values="750;50;750" dur="20s" repeatCount="indefinite"/>
      <animate attributeName="cy" values="100;180;100" dur="15s" repeatCount="indefinite"/>
      <animate attributeName="opacity" values="0;1;0" dur="20s" repeatCount="indefinite"/>
    </circle>
  </g>
  
  <!-- Main text with cyber effect -->
  <text x="400" y="80" text-anchor="middle" fill="#00ff99" font-family="Arial" font-size="32" font-weight="bold" filter="url(#neonGlow)">
    CYBER DEVELOPER
    <animate attributeName="opacity" values="0.8;1;0.8" dur="4s" repeatCount="indefinite"/>
  </text>
  
  <!-- Dynamic subtitle -->
  <text x="400" y="120" text-anchor="middle" fill="#00ffff" font-family="Arial" font-size="20">
    [ FULL STACK ENGINEER | DIGITAL ARCHITECT ]
    <animate attributeName="opacity" values="0.7;1;0.7" dur="6s" repeatCount="indefinite"/>
  </text>
  
  <!-- Decorative cyber lines -->
  <path d="M50,180 Q400,140 750,180" stroke="#00ff99" stroke-width="0.5" fill="none" opacity="0.3">
    <animate attributeName="d" 
             values="M50,180 Q400,140 750,180;M50,180 Q400,160 750,180;M50,180 Q400,140 750,180" 
             dur="15s" 
             repeatCount="indefinite"/>
  </path>
</svg>
