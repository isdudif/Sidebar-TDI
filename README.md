# Sidebar-TDI
<!DOCTYPE html>
<html lang="en">
<head> 
  <meta charset="UTF-8"> 
  <meta name="viewport" content="width=device-width, initial-scale=1.0"> 
  <title>The Dragon's Imperium - Master Sidebar Engine</title> 
  <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Barlow+Condensed:wght@400;600;700;800;900&family=Nunito:wght@700;800&display=swap" rel="stylesheet"> 
  <style> 
    /* ══════════════════════ UNIFIED DESIGN TOKENS ══════════════════════ */ 
    :root { 
      --bg0: #000000; 
      --bg1: #0a0a0a; 
      --bg2: #121212; 
      --bg3: #1a1a1a; 
      --border-dim: rgba(0,242,254,.1); 
      --border-mid: rgba(0,242,254,.25); 
      --border-hot: rgba(191,85,236,.85); 
      --c-deep: #000000; 
      --c-board: #080808; 
      --c-main: #00f2fe; 
      --c-cyan: #bf55ec; 
      --c-light: #a1c4fd; 
      --c-pale: #eef2ff; 
      --c-crimson: #ef5350; 
      --text-muted: rgba(0,242,254,.55); 
      --text-dim: rgba(255,255,255,.7); 
      --text-bright: #ffffff; 
      --grad-primary: linear-gradient(135deg, #00f2fe 0%, #bf55ec 100%); 
      --grad-primary-dark: linear-gradient(135deg, #008fa8 0%, #6d22ab 100%); 
    }
    
    * { box-sizing: border-box; margin: 0; padding: 0; }
    
    body { 
      background: var(--bg0); 
      padding: 20px 10px; 
      display: flex; 
      justify-content: center; 
      align-items: flex-start; 
      min-height: 100vh; 
    }
    
    /* ══════════════════════ UNIFIED MASTER CONTAINER ══════════════════════ */ 
    .imperium-sidebar-deck { 
      width: 100%; 
      max-width: 420px; 
      margin: 0 auto; 
      display: flex; 
      flex-direction: column; 
      gap: 0; 
    }
    
    /* Global Webkit Scrollbars Custom Standardization */
    .matches-list::-webkit-scrollbar,
    .bday-list::-webkit-scrollbar,
    .music-search-dropdown::-webkit-scrollbar,
    .music-playlist-scroll::-webkit-scrollbar,
    .titled-list-stack::-webkit-scrollbar {
      width: 4px;
    }
    .matches-list::-webkit-scrollbar-track,
    .bday-list::-webkit-scrollbar-track,
    .music-search-dropdown::-webkit-scrollbar-track,
    .music-playlist-scroll::-webkit-scrollbar-track,
    .titled-list-stack::-webkit-scrollbar-track {
      background: var(--bg0);
      border-radius: 3px;
    }
    .matches-list::-webkit-scrollbar-thumb,
    .bday-list::-webkit-scrollbar-thumb,
    .music-search-dropdown::-webkit-scrollbar-thumb,
    .music-playlist-scroll::-webkit-scrollbar-thumb,
    .titled-list-stack::-webkit-scrollbar-thumb {
      background: var(--bg3);
      border-radius: 3px;
    }
    .imperium-sidebar-deck:hover ::-webkit-scrollbar-thumb {
      background: rgba(0, 242, 254, 0.25);
    }
    
    /* High-Tech Loading Skeleton Shimmer Framework */
    .shimmer-wave {
      background: linear-gradient(90deg, #121212 25%, #1a1a1a 50%, #121212 75%);
      background-size: 200% 100%;
      animation: shimmerLoop 1.6s infinite linear;
      border-radius: 6px;
    }
    @keyframes shimmerLoop {
      0% { background-position: 200% 0; }
      100% { background-position: -200% 0; }
    }
    
    /* ══════════════════════ HIGH-TECH SEPARATOR COMPONENT ══════════════════════ */ 
    .imperium-separator { 
      position: relative; 
      width: 100%; 
      height: 60px; /* Increased overall height to make it less congested */
      padding: 16px 0; /* Creates comfortable, even spacing between sections and separator line */
      display: flex; 
      align-items: center; 
      justify-content: center; 
      overflow: hidden; 
      user-select: none; 
      pointer-events: none; 
    }
    .imperium-separator::before { 
      content: ''; 
      position: absolute; 
      width: 100%; 
      height: 1px; 
      background: linear-gradient(90deg, transparent, rgba(0, 242, 254, 0.25) 30%, rgba(191, 85, 236, 0.25) 70%, transparent); 
    }
    .imperium-separator-laser { 
      position: absolute; 
      width: 60px; 
      height: 2px; 
      background: var(--grad-primary); 
      filter: drop-shadow(0 0 4px var(--c-main)); 
      animation: moveLaser 3.5s linear infinite; 
    }
    .imperium-separator-node { 
      width: 6px; 
      height: 6px; 
      background: var(--bg0); 
      border: 1.5px solid var(--c-main); 
      border-radius: 50%; 
      z-index: 2; 
      box-shadow: 0 0 6px var(--c-main); 
      transform: rotate(45deg); 
    }
    @keyframes moveLaser { 
      0% { left: -15%; opacity: 0; } 
      10% { opacity: 1; } 
      90% { opacity: 1; } 
      100% { left: 115%; opacity: 0; } 
    }
    
    /* ══════════════════════ INDIVIDUAL MODULE OVERRIDES ══════════════════════ */ 
    .sb-top-banner, .owner-box, .members-box, .matches-box, .countdown-box, .podium-box, .gauges-box, .puzzle-box, .bday-box, .books-section, .music-card, .alliances-box, .titled-box { 
      width: 100% !important; 
      max-width: 100% !important; 
      margin: 0 !important; 
    }
    
    /* Universal Section Header Configuration Sync */ 
    .sec-hd { display: flex; align-items: stretch; gap: 0; margin-bottom: 14px; position: relative; z-index: 2; } 
    .sec-hd-bar { width: 5px; background: var(--grad-primary); border-radius: 2px 0 0 2px; flex-shrink: 0; box-shadow: 0 0 12px rgba(0,242,254,.6); } 
    .sec-hd-text { background: linear-gradient(90deg, rgba(18,18,18,0.9), transparent); padding: 4px 14px 4px 10px; clip-path: polygon(0 0, calc(100% - 10px) 0, 100% 100%, 0 100%); flex-shrink: 0; } 
    .sec-hd-title { font-family: 'Bebas Neue', cursive; font-size: 20px; letter-spacing: 2px; color: var(--text-bright); line-height: 1; text-shadow: 0 0 10px rgba(0, 242, 254, 0.3); } 
    .sec-hd-sub { font-size: 9px; font-weight: 800; letter-spacing: 1.5px; text-transform: uppercase; color: var(--c-cyan); margin-top: 2px; } 
    .sec-hd-line { flex: 1; height: 1px; align-self: center; margin-left: 8px; background: linear-gradient(90deg, var(--border-mid), transparent); opacity: .4; } 
    .sec-hd-icon { font-size: 16px; margin-left: 6px; align-self: center; opacity: .85; color: var(--text-bright); }
    
    /* Module Specific CSS Declarations Combined */ 
    /* Section 01 */ 
    .sb-top-banner { background: linear-gradient(135deg, var(--bg0) 0%, var(--bg2) 50%, #151515 100%); border-radius: 16px; padding: 24px 16px 22px; text-align: center; position: relative; overflow: hidden; border: 1px solid rgba(255, 255, 255, 0.05); border-bottom: 3px solid var(--c-main); box-shadow: 0 12px 40px rgba(0, 0, 0, 0.8); } 
    .sb-top-banner::after { content: ''; position: absolute; inset: 0; background: repeating-linear-gradient(45deg, transparent, transparent 15px, rgba(0,242,254,.02) 15px, rgba(0,242,254,.02) 30px); pointer-events: none; z-index: 1; } 
    .crest-wrap { position: relative; width: 54px; height: 54px; margin: 0 auto 12px; display: flex; align-items: center; justify-content: center; z-index: 2; } 
    .crest-glow { position: absolute; inset: 0; border-radius: 50%; background: radial-gradient(circle, rgba(0,242,254,.2) 0%, transparent 70%); animation: pulseGlow 2.5s ease-in-out infinite alternate; } 
    .crest-svg { width: 100%; height: 100%; filter: drop-shadow(0 0 8px rgba(0,242,254,0.6)); animation: floatCrest 4s ease-in-out infinite; } 
    @keyframes pulseGlow { 0% { transform: scale(0.9); opacity: 0.5; } 100% { transform: scale(1.3); opacity: 1; } } 
    @keyframes floatCrest { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-3px); } } 
    .club-title { font-family: 'Bebas Neue', cursive; font-size: 34px; letter-spacing: 3px; color: var(--text-bright); text-shadow: 0 0 15px rgba(0,242,254,.4), 0 2px 4px rgba(0,0,0,0.9); position: relative; z-index: 2; line-height: 1; } 
    .club-sub { font-family: 'Barlow Condensed', sans-serif; font-size: 11px; font-weight: 800; color: var(--text-dim); letter-spacing: 4px; text-transform: uppercase; margin-top: 8px; position: relative; z-index: 2; opacity: 0.75; transition: opacity 0.3s; } 
    .club-sub span { background: var(--grad-primary); -webkit-background-clip: text; -webkit-text-fill-color: transparent; font-weight: 900; } 
    .sb-top-banner:hover .club-sub { opacity: 1; } 
    .banner-designer { font-family: 'Barlow Condensed', sans-serif; font-size: 8px; font-weight: 900; letter-spacing: 2px; color: #444; text-transform: uppercase; margin-top: 14px; position: relative; z-index: 2; transition: color 0.3s; } 
    .sb-top-banner:hover .banner-designer { color: var(--text-muted); }
    
    /* Section 02 */ 
    .owner-box { background: linear-gradient(145deg, var(--bg2), var(--bg1)); border-radius: 16px; border: 1px solid rgba(255, 255, 255, 0.05); border-top: 3px solid var(--c-main); padding: 16px; font-family: 'Barlow Condensed', 'Nunito', sans-serif; box-shadow: 0 12px 40px rgba(0, 0, 0, 0.8); text-align: center; position: relative; overflow: hidden; } 
    .owner-box::before { content: ''; position: absolute; inset: 0; background: repeating-linear-gradient(-55deg, transparent, transparent 12px, rgba(0,242,254,0.01) 12px, rgba(0,242,254,0.01) 24px); pointer-events: none; } 
    .owner-label { font-family: 'Bebas Neue', cursive; font-size: 13px; letter-spacing: 3px; color: var(--c-main); text-transform: uppercase; margin-bottom: 12px; display: inline-block; background: rgba(0, 242, 254, 0.05); padding: 2px 10px; border-radius: 4px; border: 1px solid var(--border-dim); } 
    .owner-avatar-wrapper { position: relative; width: 90px; height: 90px; margin: 0 auto 12px; } 
    .owner-photo { width: 100%; height: 100%; border-radius: 50%; object-fit: cover; border: 2px solid var(--c-main); background: var(--bg3); box-shadow: 0 0 15px rgba(0, 242, 254, 0.25); transition: transform 0.3s ease, border-color 0.3s ease; } 
    .owner-badge { position: absolute; bottom: -2px; right: -2px; background: var(--grad-primary); width: 26px; height: 26px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 13px; border: 2px solid var(--bg1); box-shadow: 0 2px 5px rgba(0,0,0,0.5); } 
    .owner-name { font-family: 'Barlow Condensed', sans-serif; font-size: 22px; font-weight: 900; color: var(--text-bright); letter-spacing: 1px; text-shadow: 0 2px 4px rgba(0,0,0,0.8); margin-bottom: 6px; } 
    .owner-divider { width: 40px; height: 2px; background: var(--grad-primary); margin: 8px auto 10px; border-radius: 2px; } 
    .owner-punchline { font-family: 'Barlow Condensed', sans-serif; font-size: 14px; font-weight: 700; font-style: italic; color: var(--text-dim); line-height: 1.4; letter-spacing: 0.5px; padding: 0 10px; } 
    .owner-box:hover .owner-photo { transform: scale(1.04); border-color: var(--c-cyan); box-shadow: 0 0 20px rgba(191, 85, 236, 0.4); }
    
    /* Section 03 Layout Modules */ 
    .roster-container { width: 100%; display: flex; flex-direction: column; gap: 14px; } 
    .count-box { background: var(--grad-primary); border-radius: 14px; padding: 1px; box-shadow: 0 8px 24px rgba(0,0,0,0.6); } 
    .count-display { display: flex; align-items: center; gap: 14px; background: linear-gradient(145deg, var(--bg2), var(--bg1)); border-radius: 13px; padding: 12px 16px; min-height: 54px; position: relative; overflow: hidden; } 
    .count-icon { font-size: 24px; filter: drop-shadow(0 0 6px var(--c-main)); user-select: none; } 
    .count-info { display: flex; flex-direction: column; } 
    .count-value { font-family: 'Bebas Neue', cursive; font-size: 28px; letter-spacing: 1px; line-height: 1; color: var(--text-bright); text-shadow: 0 0 12px rgba(0,242,254,.4); } 
    .count-label { font-family: 'Barlow Condensed', sans-serif; font-size: 11px; font-weight: 800; text-transform: uppercase; letter-spacing: .8px; color: var(--text-dim); margin-top: 2px; opacity: 0.8; } 
    .live-pulse-container { position: absolute; right: 16px; top: 50%; transform: translateY(-50%); width: 12px; height: 12px; display: flex; align-items: center; justify-content: center; } 
    .pulse-dot { width: 6px; height: 6px; background: var(--c-main); border-radius: 50%; z-index: 2; box-shadow: 0 0 8px var(--c-main);} 
    .pulse-ring { position: absolute; width: 12px; height: 12px; border: 2px solid var(--c-main); border-radius: 50%; opacity: 0; animation: countPulse 2s cubic-bezier(0.24, 0, 0.38, 1) infinite; z-index: 1; } 
    @keyframes countPulse { 0% { transform: scale(0.6); opacity: 0.9; } 100% { transform: scale(2.4); opacity: 0; } } 
    .members-box { background: linear-gradient(145deg, var(--bg2), var(--bg1)); border-radius: 14px; border: 1px solid rgba(255, 255, 255, 0.05); border-top: 3px solid var(--c-cyan); padding: 12px; box-shadow: 0 12px 40px rgba(0, 0, 0, 0.8); } 
    .members-title { font-family: 'Bebas Neue', cursive; font-size: 18px; letter-spacing: 1.5px; color: var(--text-bright); margin-bottom: 10px; padding-left: 2px; display: flex; align-items: center; gap: 6px; } 
    .members-list { display: flex; flex-direction: column; gap: 8px; min-height: 130px;} 
    .member-item { display: flex; align-items: center; gap: 12px; padding: 10px 14px; border-radius: 8px; background: var(--bg3); border: 1px solid rgba(255,255,255,0.03); border-left: 4px solid var(--bg0); text-decoration: none; transition: all .22s cubic-bezier(0.25, 1, 0.5, 1); min-height: 48px; position: relative; overflow: hidden; } 
    .member-item::after { content: ''; position: absolute; inset: 0; background: linear-gradient(90deg, rgba(0,242,254,.03), transparent); opacity: 0; transition: opacity .2s; } 
    .member-item:hover { background: rgba(30,30,30,0.7); border-left-color: var(--c-main); border-color: rgba(255,255,255,0.08); transform: translateX(4px); box-shadow: 0 4px 10px rgba(0,0,0,0.5); } 
    .member-item:hover::after { opacity: 1; } 
    .member-avatar { width: 36px; height: 36px; border-radius: 8px; border: 1px solid rgba(255,255,255,0.1); object-fit: cover; flex-shrink: 0; transition: border-color 0.2s; } 
    .member-item:hover .member-avatar { border-color: var(--c-main); } 
    .member-info { display: flex; flex-direction: column; flex: 1; min-width: 0; } 
    .member-name { font-family: 'Barlow Condensed', sans-serif; font-size: 14px; font-weight: 800; letter-spacing: .4px; color: var(--text-bright); white-space: nowrap; overflow: hidden; text-overflow: ellipsis; } 
    .member-meta { display: flex; align-items: center; width: 100%; margin-top: 3px; font-size: 11px; font-weight: 700; } 
    .member-rating { color: #888; } 
    .member-joined { margin-left: auto; color: var(--c-main); font-weight: 750; white-space: nowrap; } 
    .error-msg { text-align: center; color: #555; font-family: 'Barlow Condensed', sans-serif; font-size: 14px; padding: 20px 0; font-weight: bold; }
    
    /* Section 04 */ 
    .matches-box { background: linear-gradient(145deg, var(--bg2), var(--bg1)); border-radius: 14px; border: 1px solid rgba(255, 255, 255, 0.05); border-top: 3px solid var(--c-main); padding: 14px; font-family: 'Barlow Condensed', sans-serif; box-shadow: 0 12px 40px rgba(0, 0, 0, 0.8); } 
    .matches-header { font-family: 'Bebas Neue', cursive; font-size: 20px; letter-spacing: 1.5px; color: var(--text-bright); margin-bottom: 12px; display: flex; align-items: center; gap: 6px; } 
    .matches-tabs { display: flex; gap: 4px; margin-bottom: 12px; background: var(--bg0); padding: 4px; border-radius: 10px; border: 1px solid rgba(255,255,255,0.05); } 
    .matches-tab { flex: 1; padding: 8px 4px; border-radius: 8px; border: none; background: transparent; color: #666; font-family: 'Barlow Condensed', sans-serif; font-size: 12px; font-weight: 800; cursor: pointer; text-transform: uppercase; letter-spacing: .8px; transition: all .2s ease; display: flex; align-items: center; justify-content: center; gap: 5px; } 
    .matches-tab:hover { background: var(--bg3); color: #aaa; } 
    .matches-tab.active { background: rgba(0, 242, 254, 0.15); color: #fff; border: 1px solid var(--c-main); box-shadow: 0 0 10px rgba(0, 242, 254, 0.2);} 
    .matches-tab .tab-count { font-size: 10px; background: #151515; padding: 1px 6px; border-radius: 999px; font-weight: 800; color: #888; border: 1px solid rgba(255,255,255,0.03); } 
    .matches-tab.active .tab-count { background: var(--c-main); color: var(--bg0); border-color: transparent; } 
    .live-dot { width: 8px; height: 8px; border-radius: 50%; background: var(--c-cyan); display: inline-block; animation: livePulse 2s ease-in-out infinite; box-shadow: 0 0 6px var(--c-cyan); } 
    @keyframes livePulse { 0%,100% { opacity:1; transform:scale(1); } 50% { opacity:.3; transform:scale(.8); } } 
    .matches-list { display: flex; flex-direction: column; gap: 8px; min-height: 80px; max-height: 380px; overflow-y: auto; padding-right: 3px; } 
    .match-item { display: flex; align-items: center; gap: 12px; padding: 10px 14px; border-radius: 8px; background: var(--bg3); border: 1px solid rgba(255,255,255,0.03); border-left: 4px solid #333; text-decoration: none; transition: all 0.25s ease; position: relative; overflow: hidden; } 
    .match-item::after { content: ''; position: absolute; inset: 0; background: linear-gradient(90deg, rgba(0,242,254,.03), transparent); opacity: 0; transition: opacity .2s; } 
    .match-item:hover { background: rgba(30,30,30,0.7); border-left-color: var(--c-main); border-color: rgba(255,255,255,0.08); transform: translateX(3px); box-shadow: 0 4px 10px rgba(0,0,0,0.5); } 
    .match-item:hover::after { opacity: 1; } 
    .match-item.live { border-left-color: var(--c-cyan); background: linear-gradient(135deg, rgba(191,85,236,.05), var(--bg3)); } 
    .match-result-badge { width: 28px; height: 28px; border-radius: 6px; display: flex; align-items: center; justify-content: center; font-size: 13px; font-weight: 900; color: #fff; flex-shrink: 0; box-shadow: 0 2px 4px rgba(0,0,0,.5); border: 1px solid rgba(255,255,255,0.05); } 
    .match-result-badge.win { background: var(--grad-primary); color: var(--bg0); } 
    .match-result-badge.draw { background: #333; color: #aaa; } 
    .match-result-badge.lose { background: linear-gradient(135deg, #400a20, #73123b); color: #ff8fa3; } 
    .match-result-badge.live { background: linear-gradient(135deg, #7e22ce, var(--c-cyan)); box-shadow: 0 0 8px rgba(191,85,236,0.3); } 
    .match-result-badge.upcoming { background: #222; color: #888; } 
    .match-info { flex: 1; min-width: 0; } 
    .match-name { font-size: 14px; font-weight: 800; color: var(--text-bright); white-space: nowrap; overflow: hidden; text-overflow: ellipsis; margin-bottom: 2px; } 
    .match-meta { display: flex; align-items: center; gap: 8px; font-size: 11px; font-weight: 700; color: #888; flex-wrap: wrap; } 
    .match-vs { color: var(--text-dim); } 
    .match-time-class { font-size: 9px; text-transform: uppercase; letter-spacing: .5px; background: var(--bg0); color: var(--c-main); padding: 1px 6px; border-radius: 999px; border: 1px solid rgba(255,255,255,0.05); font-weight: 900; } 
    .match-time { margin-left: auto; color: #555; font-size: 10px; white-space: nowrap; } 
    .matches-empty { text-align: center; padding: 30px 0; font-size: 13px; font-weight: 800; color: #444; display: flex; flex-direction: column; gap: 8px; align-items: center; width: 100%;} 
    .matches-empty span { font-size: 24px; }
    
    /* Section 05 Layout Configurations */ 
    .countdown-box { background: linear-gradient(145deg, var(--bg2), var(--bg1)); border-radius: 14px; border: 1px solid rgba(255, 255, 255, 0.05); border-top: 3px solid var(--c-main); padding: 14px; font-family: 'Barlow Condensed', sans-serif; box-shadow: 0 12px 40px rgba(0, 0, 0, 0.8); position: relative; overflow: hidden; text-align: center; } 
    .countdown-box::before { content: ''; position: absolute; inset: 0; background: repeating-linear-gradient(-55deg, transparent, transparent 12px, rgba(0,242,254,0.01) 12px, rgba(0,242,254,0.01) 24px); pointer-events: none; } 
    .match-target-panel { background: var(--bg3); border: 1px solid rgba(255, 255, 255, 0.03); border-radius: 8px; padding: 10px 14px; margin-bottom: 14px; position: relative; z-index: 2; } 
    .match-target-title { font-size: 14px; font-weight: 800; color: var(--text-bright); white-space: nowrap; overflow: hidden; text-overflow: ellipsis; margin-bottom: 2px; } 
    .match-target-opp { font-size: 11px; font-weight: 700; color: #888; text-transform: uppercase; letter-spacing: 0.5px; } 
    .match-target-opp span { color: var(--c-main); } 
    .ticker-display-row { display: flex; align-items: center; justify-content: center; gap: 8px; margin: 16px 0 12px; position: relative; z-index: 2; } 
    .ticker-block { display: flex; flex-direction: column; align-items: center; } 
    .ticker-value { font-family: 'Bebas Neue', cursive; font-size: 38px; line-height: 1; color: var(--text-bright); letter-spacing: 1px; text-shadow: 0 0 15px rgba(0, 242, 254, 0.4); background: var(--bg0); padding: 4px 10px; border-radius: 6px; border: 1px solid rgba(255, 255, 255, 0.03); min-width: 64px; } 
    .ticker-label { font-size: 9px; font-weight: 900; text-transform: uppercase; letter-spacing: 1px; color: #555; margin-top: 4px; } 
    .ticker-colon { font-family: 'Bebas Neue', cursive; font-size: 32px; line-height: 1; color: var(--c-main); padding-bottom: 12px; animation: flashColon 1s steps(2, start) infinite; } 
    @keyframes flashColon { to { opacity: 0; } } 
    .ticker-action-btn { display: inline-flex; align-items: center; justify-content: center; width: 100%; background: var(--grad-primary-dark); border: none; border-radius: 8px; color: #fff; font-family: 'Bebas Neue', cursive; font-size: 15px; letter-spacing: 1.5px; padding: 10px; cursor: pointer; text-decoration: none; box-shadow: 0 3px 0 #06404d; transition: all 0.15s ease; position: relative; z-index: 2; } 
    .ticker-action-btn:hover { transform: translateY(-1px); box-shadow: 0 4px 0 #06404d, 0 4px 10px rgba(0,242,254,0.2); background: var(--grad-primary); } 
    .ticker-action-btn:active { transform: translateY(1px); box-shadow: 0 1px 0 #06404d; } 
    .ticker-status-msg { font-size: 13px; font-weight: 800; color: #555; padding: 24px 0; }
    
    /* Section 06 */ 
    .podium-box { background: linear-gradient(145deg, var(--bg2), var(--bg1)); border-radius: 16px; border: 1px solid rgba(255, 255, 255, 0.05); border-top: 3px solid var(--c-cyan); padding: 14px; font-family: 'Barlow Condensed', sans-serif; box-shadow: 0 12px 40px rgba(0, 0, 0, 0.8); position: relative; overflow: hidden; } 
    .podium-box::before { content: ''; position: absolute; inset: 0; background: repeating-linear-gradient(-55deg, transparent, transparent 12px, rgba(191,85,236,0.01) 12px, rgba(191,85,236,0.01) 24px); pointer-events: none; } 
    .podium-tabs-row { display: flex; gap: 4px; margin-bottom: 16px; background: var(--bg0); padding: 4px; border-radius: 10px; border: 1px solid rgba(255,255,255,0.05); position: relative; z-index: 2; } 
    .podium-tab-btn { flex: 1; padding: 8px 4px; border-radius: 8px; border: none; background: transparent; color: #666; font-family: 'Barlow Condensed', sans-serif; font-size: 11px; font-weight: 800; cursor: pointer; text-transform: uppercase; letter-spacing: 1px; transition: all .2s cubic-bezier(0.25, 1, 0.5, 1); } 
    .podium-tab-btn:hover { background: var(--bg3); color: #aaa; } 
    .podium-tab-btn.active { background: var(--grad-primary-dark); color: #fff; border: 1px solid rgba(255,255,255,0.08); box-shadow: 0 2px 4px rgba(0,0,0,0.3); } 
    .podium-display-stage { display: flex; justify-content: space-between; align-items: flex-end; padding: 10px 4px 0; margin-bottom: 4px; position: relative; z-index: 2; height: 185px; border-bottom: 2px solid #222; } 
    .podium-pillar-wrap { display: flex; flex-direction: column; align-items: center; width: 32%; text-decoration: none; opacity: 0; transform: translateY(12px); animation: showSmoothPillar 0.6s cubic-bezier(0.34, 1.56, 0.64, 1) forwards; } 
    .podium-pillar-wrap.rank-2 { animation-delay: 0.06s; } 
    .podium-pillar-wrap.rank-1 { animation-delay: 0s; } 
    .podium-pillar-wrap.rank-3 { animation-delay: 0.12s; } 
    @keyframes showSmoothPillar { to { opacity: 1; transform: translateY(0); } } 
    .podium-avatar-frame { position: relative; width: 52px; height: 52px; margin-bottom: 8px; display: block; min-height: 52px; } 
    .podium-pillar-wrap.rank-1 .podium-avatar-frame { width: 64px; height: 64px; min-height: 64px; } 
    .podium-img { width: 100%; height: 100%; border-radius: 50%; object-fit: cover; background: var(--bg3); border: 2px solid #333; display: block; } 
    .podium-crown-medal { position: absolute; top: -12px; left: 50%; transform: translateX(-50%); font-size: 16px; filter: drop-shadow(0 2px 4px rgba(0,0,0,0.5)); z-index: 3; } 
    .podium-pillar-wrap.rank-1 .podium-crown-medal { font-size: 20px; animation: bounceCrown 2s ease-in-out infinite alternate; } 
    .podium-base-pillar { width: 100%; background: linear-gradient(180deg, var(--bg3), var(--bg2)); border: 1px solid rgba(255, 255, 255, 0.03); border-bottom: none; border-radius: 8px 8px 0 0; display: flex; flex-direction: column; align-items: center; justify-content: flex-start; padding: 8px 2px 0; text-align: center; box-shadow: inset 0 1px 0 rgba(255,255,255,0.02); transition: background 0.3s ease; } 
    .podium-pillar-wrap:hover .podium-base-pillar { background: rgba(35, 35, 35, 0.9); } 
    .podium-pillar-wrap.rank-1 .podium-base-pillar { height: 105px; border-top: 2px solid #ffd700; } 
    .podium-pillar-wrap.rank-2 .podium-base-pillar { height: 80px; border-top: 2px solid #c0c0c0; } 
    .podium-pillar-wrap.rank-3 .podium-base-pillar { height: 60px; border-top: 2px solid #cd7f32; } 
    .podium-pillar-wrap.rank-1 .podium-img { border-color: #ffd700; box-shadow: 0 0 12px rgba(255,215,0,0.25); } 
    .podium-pillar-wrap.rank-2 .podium-img { border-color: #c0c0c0; } 
    .podium-pillar-wrap.rank-3 .podium-img { border-color: #cd7f32; } 
    .p-name { font-size: 11px; font-weight: 800; color: var(--text-bright); width: 100%; max-width: 92%; text-align: center; display: block; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; padding: 0 1px; min-height: 14px; } 
    .podium-pillar-wrap.rank-1 .p-name { font-size: 13px; } 
    .p-score { font-family: 'Bebas Neue', cursive; font-size: 13px; color: var(--c-main); letter-spacing: 0.5px; margin-top: 1px; } 
    .podium-pillar-wrap.rank-1 .p-score { font-size: 16px; color: #ffd700; } 
    .p-rank-num { font-family: 'Bebas Neue', cursive; font-size: 20px; color: rgba(255, 255, 255, 0.03); line-height: 1; margin-top: auto; padding-bottom: 2px; user-select: none; } 
    .podium-loading-fallback { text-align: center; font-size: 13px; font-weight: 800; color: #444; padding: 55px 0; width: 100%; } 
    @keyframes bounceCrown { 0% { transform: translate(-50%, 0); } 100% { transform: translate(-50%, -4px); } }
    
    /* Section 07 Layout Containers */ 
    .gauges-box { background: linear-gradient(145deg, var(--bg2), var(--bg1)); border-radius: 16px; border: 1px solid rgba(255, 255, 255, 0.05); border-top: 3px solid var(--c-main); padding: 14px; font-family: 'Barlow Condensed', sans-serif; box-shadow: 0 12px 40px rgba(0, 0, 0, 0.8); position: relative; overflow: hidden; } 
    .gauges-box::before { content: ''; position: absolute; inset: 0; background: repeating-linear-gradient(-55deg, transparent, transparent 12px, rgba(0,242,254,0.01) 12px, rgba(0,242,254,0.01) 24px); pointer-events: none; } 
    .gauge-matrix-stack { display: flex; flex-direction: column; gap: 12px; position: relative; z-index: 2; } 
    .gauge-row { background: var(--bg3); border: 1px solid rgba(255, 255, 255, 0.02); border-radius: 8px; padding: 10px 12px; } 
    .gauge-label-strip { display: flex; justify-content: space-between; align-items: center; margin-bottom: 6px; } 
    .gauge-name { font-size: 13px; font-weight: 800; text-transform: uppercase; letter-spacing: 1px; color: var(--text-bright); } 
    .gauge-count-tag { font-family: 'Bebas Neue', cursive; font-size: 16px; letter-spacing: 0.5px; color: #888; } 
    .gauge-count-tag span { color: var(--text-bright); } 
    .gauge-track-bar { width: 100%; height: 6px; background: var(--bg0); border-radius: 999px; border: 1px solid rgba(255,255,255,0.04); overflow: hidden; position: relative; box-shadow: inset 0 2px 4px rgba(0,0,0,0.8); } 
    .gauge-fill { height: 100%; width: 0%; border-radius: 999px; transition: width 1.2s cubic-bezier(0.4, 0, 0.2, 1); } 
    .fill-cyan { background: linear-gradient(90deg, #008fa8, var(--c-main)); box-shadow: 0 0 8px rgba(0,242,254,0.4); } 
    .fill-purple { background: linear-gradient(90deg, #6d22ab, var(--c-cyan)); box-shadow: 0 0 8px rgba(191,85,236,0.4); } 
    .fill-charcoal { background: linear-gradient(90deg, #222, #555); box-shadow: 0 0 6px rgba(255,255,255,0.1); } 
    .gauge-loading-fallback { text-align: center; font-size: 13px; font-weight: 800; color: #444; padding: 24px 0; width: 100%; }
    
    /* Section 08 */ 
    .puzzle-box { background: linear-gradient(145deg, var(--bg2), var(--bg1)); border-radius: 16px; border: 1px solid rgba(255, 255, 255, 0.05); border-top: 3px solid var(--c-main); padding: 14px; font-family: 'Barlow Condensed', sans-serif; box-shadow: 0 12px 40px rgba(0, 0, 0, 0.8); position: relative; overflow: hidden; } 
    .puzzle-box::before { content: ''; position: absolute; inset: 0; background: repeating-linear-gradient(-55deg, transparent, transparent 12px, rgba(0,242,254,0.01) 12px, rgba(0,242,254,0.01) 24px); pointer-events: none; } 
    .puzzle-display-card { width: 85%; margin: 0 auto; display: flex; flex-direction: column; gap: 12px; position: relative; z-index: 2; } 
    .puzzle-board-frame { width: 100%; aspect-ratio: 1 / 1; border-radius: 8px; border: 1px solid rgba(255, 255, 255, 0.05); background: var(--bg0); overflow: hidden; box-shadow: 0 6px 20px rgba(0,0,0,0.6); position: relative; } 
    .puzzle-img { width: 100%; height: 100%; object-fit: cover; filter: brightness(0.85); transition: filter 0.3s ease; } 
    .puzzle-board-frame:hover .puzzle-img { filter: brightness(1); } 
    .puzzle-meta-panel { background: var(--bg3); border: 1px solid rgba(255, 255, 255, 0.03); border-radius: 8px; padding: 10px 12px; text-align: left; } 
    .puzzle-title { font-size: 14px; font-weight: 800; color: var(--text-bright); white-space: nowrap; overflow: hidden; text-overflow: ellipsis; margin-bottom: 2px; } 
    .puzzle-desc { font-size: 11px; font-weight: 700; color: #777; text-transform: uppercase; letter-spacing: 0.5px; } 
    .puzzle-desc span { color: var(--c-main); } 
    .puzzle-action-btn { display: inline-flex; align-items: center; justify-content: center; width: 100%; background: var(--grad-primary-dark); border: none; border-radius: 8px; color: #fff; font-family: 'Bebas Neue', cursive; font-size: 16px; letter-spacing: 1.5px; padding: 10px; cursor: pointer; text-decoration: none; box-shadow: 0 3px 0 #06404d; transition: all 0.15s ease; } 
    .puzzle-action-btn:hover { transform: translateY(-1px); box-shadow: 0 4px 0 #06404d, 0 4px 10px rgba(0,242,254,0.2); background: var(--grad-primary); } 
    .puzzle-action-btn:active { transform: translateY(1px); box-shadow: 0 1px 0 #06404d; } 
    .puzzle-loading-msg { text-align: center; font-size: 13px; font-weight: 800; color: #444; padding: 30px 0; }
    
    /* Section 09 Layout Subsystems */ 
    .bday-box { background: linear-gradient(145deg, var(--bg2), var(--bg1)); border-radius: 14px; border: 1px solid rgba(255, 255, 255, 0.05); border-top: 3px solid var(--c-main); padding: 14px; font-family: 'Barlow Condensed', 'Nunito', sans-serif; box-shadow: 0 12px 40px rgba(0, 0, 0, 0.8); position: relative; overflow: hidden; } 
    .bday-box::before { content: ''; position: absolute; inset: 0; background: repeating-linear-gradient(-55deg, transparent, transparent 12px, rgba(0,242,254,0.01) 12px, rgba(0,242,254,0.01) 24px); pointer-events: none; } 
    .bday-form { display: flex; flex-direction: column; gap: 8px; margin-bottom: 14px; position: relative; z-index: 2; } 
    .bday-row { display: flex; gap: 6px; } 
    .bday-input, .bday-select, .bday-textarea { background: var(--bg0); border: 1px solid rgba(255, 255, 255, 0.1); border-radius: 8px; color: var(--text-bright); font-family: 'Barlow Condensed', sans-serif; font-size: 14px; padding: 8px 12px; outline: none; transition: all 0.2s; box-shadow: inset 0 2px 4px rgba(0,0,0,0.6); } 
    .bday-input:focus, .bday-select:focus, .bday-textarea:focus { border-color: var(--c-main); box-shadow: inset 0 2px 4px rgba(0,0,0,0.6), 0 0 8px rgba(0,242,254,0.15); } 
    .bday-input::placeholder, .bday-textarea::placeholder { color: #444; font-weight: 600; } 
    .bday-input { flex: 1; } 
    .bday-select { width: 50%; cursor: pointer; } 
    .bday-select option { background: var(--bg2); color: var(--text-bright); } 
    .bday-textarea { resize: none; height: 46px; font-size: 13px; padding: 6px 10px; } 
    .bday-btn { background: var(--grad-primary-dark); border: none; border-radius: 8px; color: #fff; font-family: 'Bebas Neue', cursive; font-size: 16px; letter-spacing: 1.5px; padding: 9px; cursor: pointer; box-shadow: 0 3px 0 #06404d; transition: all 0.15s ease; } 
    .bday-btn:hover { transform: translateY(-1px); box-shadow: 0 4px 0 #06404d, 0 4px 10px rgba(0,242,254,0.2); background: var(--grad-primary); } 
    .bday-btn:active { transform: translateY(1px); box-shadow: 0 1px 0 #06404d; } 
    
    /* ENHANCED: Fixed height constraint and forced overflow mechanics for strict scrollbox mode */
    .bday-list { display: flex; flex-direction: column; gap: 7px; height: 210px; max-height: 210px; overflow-y: auto; padding-right: 4px; position: relative; z-index: 2; } 
    
    .bday-item { display: flex; align-items: center; gap: 12px; padding: 10px 12px; border-radius: 0 8px 8px 0; background: var(--bg3); border: 1px solid rgba(255,255,255,0.03); border-left: 4px solid var(--c-main); position: relative; } 
    .bday-item.highlight-today { border-left-color: var(--c-cyan); background: linear-gradient(90deg, rgba(191,85,236,0.1), var(--bg3)); border-color: rgba(191,85,236,0.15); } 
    .bday-avatar { font-size: 18px; display: flex; align-items: center; justify-content: center; user-select: none; } 
    .bday-info { flex: 1; min-width: 0; display: flex; flex-direction: column; padding-right: 14px; } 
    .bday-name-row { display: flex; align-items: center; gap: 6px; flex-wrap: wrap; } 
    .bday-name { font-family: 'Barlow Condensed', sans-serif; font-size: 14px; font-weight: 800; color: var(--text-bright); overflow: hidden; text-overflow: ellipsis; white-space: nowrap; } 
    .bday-celebration { font-size: 11px; font-weight: 900; color: #fff; background: var(--grad-primary); padding: 2px 7px; border-radius: 5px; letter-spacing: 0.5px; animation: pulseBday 1.5s ease-in-out infinite alternate; } 
    @keyframes pulseBday { 0% { transform: scale(1); filter: drop-shadow(0 0 2px rgba(0,242,254,.4)); } 100% { transform: scale(1.04); filter: drop-shadow(0 0 10px rgba(191,85,236,.6)); } } 
    .bday-note { font-size: 12px; color: var(--text-dim); overflow: hidden; text-overflow: ellipsis; white-space: nowrap; font-style: italic; margin-top: 2px; opacity: 0.8; } 
    .bday-date-badge { font-family: 'Barlow Condensed', sans-serif; font-size: 12px; font-weight: 800; color: #ffffff; background: #222222; padding: 4px 10px; border-radius: 6px; border: 1px solid rgba(255,255,255,0.1); flex-shrink: 0; text-shadow: 0 1px 2px rgba(0,0,0,0.5); } 
    .bday-delete { font-size: 11px; color: #555; cursor: pointer; padding: 4px; transition: color 0.15s; line-height: 1; user-select: none; margin-left: 4px; } 
    .bday-delete:hover { color: #ff4444; } 
    .bday-empty { text-align: center; font-size: 13px; font-family: 'Barlow Condensed', sans-serif; color: #444; padding: 24px 0; font-weight: bold; width: 100%; }
    
    /* Section 10 Grid Components */ 
    .books-section { background: linear-gradient(145deg, var(--bg2), var(--bg1)); border-radius: 16px; border: 1px solid rgba(255, 255, 255, 0.05); border-top: 3px solid var(--c-main); padding: 16px; font-family: 'Barlow Condensed', sans-serif; position: relative; overflow: hidden; } 
    .books-section::before { content: ''; position: absolute; inset: 0; background: repeating-linear-gradient(-55deg, transparent, transparent 12px, rgba(0,242,254,0.01) 12px, rgba(0,242,254,0.01) 24px); pointer-events: none; } 
    .books-grid { display: grid; grid-template-columns: repeat(2, minmax(0, 1fr)); gap: 12px; width: 85%; margin: 0 auto; } 
    .book-card { border-radius: 8px; overflow: hidden; border: 1px solid rgba(255, 255, 255, 0.05); background: var(--bg3); transition: all .25s cubic-bezier(0.4, 0, 0.2, 1); text-decoration: none; display: block; position: relative; box-shadow: 0 4px 15px rgba(0,0,0,0.4); aspect-ratio: 3 / 4; } 
    .book-card:hover { border-color: var(--c-main); transform: translateY(-4px); box-shadow: 0 12px 24px rgba(0,242,254,0.15); } 
    .book-card img { width: 100%; height: 100%; display: block; object-fit: cover; filter: brightness(.80); transition: filter 0.25s; } 
    .book-card:hover img { filter: brightness(0.95); } 
    .book-label { position: absolute; bottom: 0; left: 0; right: 0; padding: 8px 4px; background: linear-gradient(0deg, rgba(0,0,0,0.95) 75%, transparent); font-size: 9px; font-weight: 900; letter-spacing: 1px; text-transform: uppercase; color: var(--c-main); text-align: center; border-top: 1px solid rgba(255, 255, 255, 0.03); transition: all 0.25s; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; } 
    .book-card:hover .book-label { color: #ffffff; background: var(--grad-primary); }
    
    /* Section 11 */ 
    .music-card { background: linear-gradient(145deg, var(--bg2), var(--bg1)); border-radius: 16px; border: 1px solid rgba(255, 255, 255, 0.05); border-top: 3px solid var(--c-main); padding: 14px; font-family: 'Barlow Condensed', 'Nunito', sans-serif; position: relative; overflow: hidden; box-shadow: 0 12px 40px rgba(0, 0, 0, 0.8); } 
    .now-playing-banner { background: linear-gradient(135deg, var(--bg0) 0%, var(--bg2) 60%, #151515 100%); border-radius: 12px; padding: 12px 14px; display: flex; align-items: center; gap: 12px; margin-bottom: 12px; position: relative; overflow: hidden; border: 1px solid rgba(255, 255, 255, 0.05); box-shadow: inset 0 1px 4px rgba(255,255,255,0.02), 0 4px 10px rgba(0,0,0,0.5); } 
    .now-playing-banner::before { content: ''; position: absolute; inset: 0; background: repeating-linear-gradient(-55deg, transparent, transparent 12px, rgba(255,255,255,0.01) 12px, rgba(255,255,255,0.01) 24px); pointer-events: none; } 
    .disc-wrap { width: 38px; height: 38px; border-radius: 50%; background: var(--bg3); border: 2px solid var(--c-main); display: flex; align-items: center; justify-content: center; flex-shrink: 0; position: relative; z-index: 1; font-size: 16px; box-shadow: 0 0 8px rgba(0,242,254,0.2); } 
    .disc-wrap.spinning { animation: spinDisc 4s linear infinite; } 
    @keyframes spinDisc { from { transform: rotate(0); } to { transform: rotate(360deg); } } 
    .track-info { flex: 1; min-width: 0; position: relative; z-index: 1; } 
    .track-label { font-size: 10px; font-weight: 900; color: #888; text-transform: uppercase; letter-spacing: 1.5px; margin-bottom: 3px; } 
    .track-name { font-size: 13px; font-weight: 900; color: #fff; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; text-shadow: 0 2px 4px rgba(0,0,0,0.8); } 
    .eq-bars { display: flex; align-items: flex-end; gap: 3px; height: 18px; position: relative; z-index: 1; flex-shrink: 0; } 
    .eq-bar { width: 4px; border-radius: 2px 2px 0 0; background: var(--c-main); animation: eqBounce 0.8s ease-in-out infinite alternate; } 
    .eq-bar:nth-child(1) { height: 6px; animation-delay: 0s; } 
    .eq-bar:nth-child(2) { height: 14px; animation-delay: .15s; } 
    .eq-bar:nth-child(3) { height: 9px; animation-delay: .3s; } 
    .eq-bar.paused { animation-play-state: paused; height: 4px; background: #444; } 
    @keyframes eqBounce { to { height: 18px; background: var(--c-cyan); filter: drop-shadow(0 0 4px var(--c-cyan)); } } 
    .music-progress-section { margin-bottom: 12px; } 
    .music-progress-track { width: 100%; height: 6px; background: var(--bg0); border-radius: 999px; border: 1px solid rgba(255,255,255,0.05); cursor: pointer; position: relative; overflow: visible; box-shadow: inset 0 2px 4px rgba(0,0,0,0.8); } 
    .music-progress-fill { height: 100%; background: var(--grad-primary); border-radius: 999px; width: 0%; position: relative; transition: width .1s linear; } 
    .music-progress-knob { position: absolute; right: -6px; top: 50%; transform: translateY(-50%); width: 12px; height: 12px; border-radius: 50%; background: #fff; border: 2.5px solid var(--c-main); box-shadow: 0 2px 6px rgba(0,0,0,0.8); cursor: pointer; z-index: 3; transition: transform .15s; } 
    .music-progress-knob:hover { transform: translateY(-50%) scale(1.3); background: var(--c-cyan); border-color: #fff; } 
    .music-time-row { display: flex; justify-content: space-between; font-family: 'Barlow Condensed', sans-serif; font-size: 11px; font-weight: 700; letter-spacing: .5px; color: #666; margin-top: 6px; padding: 0 2px; } 
    .music-controls-row { display: flex; align-items: center; gap: 8px; margin-bottom: 12px; } 
    .mcbtn { display: flex; align-items: center; justify-content: center; border-radius: 50%; cursor: pointer; border: 1px solid rgba(255,255,255,0.08); background: var(--bg3); box-shadow: 0 3px 0 rgba(0,0,0,0.6); transition: all .15s ease; user-select: none; flex-shrink: 0; } 
    .mcbtn:hover { background: var(--bg2); border-color: var(--c-main); transform: translateY(-2px); box-shadow: 0 5px 0 rgba(0,0,0,0.7); } 
    .mcbtn:active { transform: translateY(1px); box-shadow: 0 1px 0 rgba(0,0,0,0.6); } 
    .mcbtn svg { display: block; flex-shrink: 0; } 
    .mcbtn.sm { width: 26px; height: 26px; } 
    .mcbtn.sm svg { width: 11px; height: 11px; stroke: var(--c-main) !important; } 
    .mcbtn.play { width: 34px; height: 34px; background: var(--grad-primary); border: none; box-shadow: 0 4px 0 #06404d; } 
    .mcbtn.play svg { width: 12px; height: 12px; fill: var(--bg0) !important; } 
    .mcbtn.play:hover { transform: translateY(-2px); box-shadow: 0 6px 0 #06404d; background: var(--grad-primary); } 
    .mcbtn.play:active { transform: translateY(2px); box-shadow: 0 1px 0 #06404d; } 
    .mcbtn.loop-on { background: linear-gradient(135deg, var(--bg0), var(--bg3)); border: 1px solid var(--c-main); box-shadow: 0 3px 0 rgba(0,0,0,0.6); } 
    .mcbtn.loop-on svg { stroke: #fff !important; } 
    .music-vol-row { display: flex; align-items: center; gap: 8px; margin-left: auto; } 
    .music-vol-icon { width: 26px; height: 26px; border-radius: 50%; border: 1px solid rgba(255,255,255,0.05); background: var(--bg0); display: flex; align-items: center; justify-content: center; cursor: pointer; box-shadow: 0 2px 3px rgba(0,0,0,0.5); transition: all .15s; flex-shrink: 0; } 
    .music-vol-icon:hover { background: var(--bg3); border-color: var(--c-main); transform: translateY(-1px); } 
    .music-vol-icon svg { width: 12px; height: 12px; stroke: var(--c-main) !important; } 
    .music-vol-track { width: 54px; height: 5px; background: var(--bg0); border-radius: 999px; border: 1px solid rgba(255,255,255,0.05); cursor: pointer; position: relative; flex-shrink: 0; } 
    .music-vol-fill { height: 100%; background: linear-gradient(90deg, var(--bg3), var(--c-main)); border-radius: 999px; width: 70%; } 
    .music-vol-knob { position: absolute; top: 50%; transform: translateY(-50%); left: calc(70% - 5px); width: 10px; height: 10px; border-radius: 50%; background: #fff; border: 1.5px solid var(--c-main); cursor: pointer; z-index: 2; box-shadow: 0 1px 3px rgba(0,0,0,0.6); } 
    .music-search-section { margin-bottom: 12px; } 
    .music-search-label { font-family: 'Barlow Condensed', sans-serif; font-size: 12px; font-weight: 800; color: #888; text-transform: uppercase; letter-spacing: 1.5px; margin-bottom: 6px; display: flex; align-items: center; gap: 6px; } 
    .music-search-label::after { content: ''; flex: 1; height: 1px; background: rgba(255,255,255,0.08); border-radius: 1px; } 
    .music-search-input { width: 100%; padding: 8px 12px; border-radius: 8px; border: 1px solid rgba(255, 255, 255, 0.1); background: var(--bg0); color: var(--text-bright); font-size: 13px; font-family: 'Barlow Condensed', 'Nunito', sans-serif; font-weight: 700; outline: none; transition: all .2s; box-shadow: inset 0 2px 4px rgba(0,0,0,0.6); } 
    .music-search-input::placeholder { color: #444; font-weight: 600; } 
    .music-search-input:focus { border-color: var(--c-main); box-shadow: inset 0 2px 4px rgba(0,0,0,0.6), 0 0 8px rgba(0,242,254,0.1); } 
    .music-search-dropdown { margin-top: 6px; border-radius: 10px; border: 1px solid rgba(255,255,255,0.1); background: var(--bg2); overflow-y: auto; max-height: 160px; display: none; position: relative; z-index: 10; box-shadow: 0 8px 24px rgba(0,0,0,0.8); } 
    .music-search-dropdown.open { display: block; } 
    .music-search-item { display: flex; align-items: center; gap: 10px; padding: 8px 12px; cursor: pointer; font-family: 'Barlow Condensed', sans-serif; font-size: 13px; font-weight: 700; color: #aaa; border-bottom: 1px solid rgba(255,255,255,0.03); transition: all .15s; } 
    .music-search-item:last-child { border-bottom: none; } 
    .music-search-item:hover { background: var(--bg3); color: var(--text-bright); } 
    .music-search-item-title { flex: 1; overflow: hidden; text-overflow: ellipsis; white-space: nowrap; } 
    .music-search-badge { font-size: 10px; font-weight: 900; padding: 2px 8px; border-radius: 5px; flex-shrink: 0; text-transform: uppercase; letter-spacing: 0.5px; } 
    .music-search-badge.add { background: var(--bg0); color: var(--c-main); border: 1px solid rgba(255,255,255,0.08); } 
    .music-playlist-section { margin-top: 4px; } 
    .music-playlist-label { font-family: 'Barlow Condensed', sans-serif; font-size: 12px; font-weight: 800; color: #888; text-transform: uppercase; letter-spacing: 1.5px; margin-bottom: 6px; display: flex; align-items: center; gap: 6px; } 
    .music-playlist-label::after { content: ''; flex: 1; height: 1px; background: rgba(255,255,255,0.08); border-radius: 1px; } 
    .music-playlist-count { font-size: 10px; font-weight: 900; padding: 1px 6px; border-radius: 4px; background: var(--bg0); color: var(--c-main); border: 1px solid rgba(255,255,255,0.05); } 
    .music-playlist-scroll { height: 140px; overflow-y: auto; padding-right: 2px; } 
    .music-playlist-item { display: flex; align-items: center; gap: 10px; padding: 8px 10px; border-radius: 0 8px 8px 0; margin-bottom: 5px; cursor: pointer; background: var(--bg3); border: 1px solid rgba(255,255,255,0.03); border-left: 3px solid var(--bg0); transition: all .18s ease; font-family: 'Barlow Condensed', sans-serif; font-size: 14px; font-weight: 700; color: #aaa; } 
    .music-playlist-item:hover { background: rgba(30,30,30,0.7); border-left-color: #555; color: var(--text-bright); transform: translateX(2px); } 
    .music-playlist-item.active { background: rgba(20,20,20,0.9); border-left-color: var(--c-main); border-color: rgba(255,255,255,0.08); color: var(--text-bright); box-shadow: inset 0 0 8px rgba(0,242,254,0.02); } 
    .music-pl-num { font-size: 11px; font-weight: 900; color: var(--c-main); min-width: 18px; opacity: 0.6; } 
    .music-pl-icon { font-size: 12px; flex-shrink: 0; color: var(--c-main); } 
    .music-playlist-item.active .music-pl-icon { color: var(--c-cyan); filter: drop-shadow(0 0 4px var(--c-cyan)); } 
    .music-pl-name { flex: 1; overflow: hidden; text-overflow: ellipsis; white-space: nowrap; } 
    .music-pl-remove { font-size: 12px; color: #555; cursor: pointer; padding: 0 4px; transition: color .15s; flex-shrink: 0; line-height: 1; } 
    .music-pl-remove:hover { color: var(--c-cyan); } 
    .music-playlist-empty { text-align: center; padding: 24px 0; font-family: 'Barlow Condensed', sans-serif; font-size: 13px; font-weight: 800; letter-spacing: .5px; color: #444; } 
    .music-playlist-empty span { display: block; font-size: 26px; margin-bottom: 6px; }
    
    /* Section 12 Partner Grid Ecosystem */ 
    .alliances-box { background: linear-gradient(145deg, var(--bg2), var(--bg1)); border-radius: 16px; border: 1px solid rgba(255, 255, 255, 0.05); border-top: 3px solid var(--c-cyan); padding: 14px; font-family: 'Barlow Condensed', sans-serif; box-shadow: 0 12px 40px rgba(0, 0, 0, 0.8); position: relative; overflow: hidden; } 
    .alliances-box::before { content: ''; position: absolute; inset: 0; background: repeating-linear-gradient(-55deg, transparent, transparent 12px, rgba(0,242,254,0.01) 12px, rgba(0,242,254,0.01) 24px); pointer-events: none; } 
    .ally-list-stack { display: flex; flex-direction: column; gap: 8px; position: relative; z-index: 2; } 
    .ally-card { display: flex; align-items: center; gap: 12px; padding: 10px 14px; background: var(--bg3); border: 1px solid rgba(255, 255, 255, 0.03); border-left: 4px solid #222; border-radius: 0 8px 8px 0; text-decoration: none; transition: all .25s cubic-bezier(0.25, 1, 0.5, 1); position: relative; overflow: hidden; } 
    .ally-card::after { content: ''; position: absolute; inset: 0; background: linear-gradient(90deg, rgba(155, 0, 255, 0.04), transparent); opacity: 0; transition: opacity 0.2s; } 
    .ally-card:hover { background: rgba(30, 30, 30, 0.7); border-left-color: var(--c-cyan); border-color: rgba(255, 255, 255, 0.08); transform: translateX(4px); box-shadow: 0 4px 12px rgba(0, 0, 0, 0.5); } 
    .ally-card:hover::after { opacity: 1; } 
    .ally-logo { width: 40px; height: 40px; border-radius: 8px; border: 1px solid rgba(255, 255, 255, 0.1); object-fit: cover; flex-shrink: 0; background: var(--bg0); transition: border-color 0.2s; } 
    .ally-card:hover .ally-logo { border-color: var(--c-cyan); } 
    .ally-info { flex: 1; min-width: 0; display: flex; flex-direction: column; } 
    .ally-name { font-family: 'Barlow Condensed', sans-serif; font-size: 15px; font-weight: 800; letter-spacing: .3px; color: var(--text-bright); white-space: nowrap; overflow: hidden; text-overflow: ellipsis; } 
    .ally-sub { font-size: 11px; font-weight: 700; color: var(--text-dim); letter-spacing: .5px; margin-top: 2px; display: flex; align-items: center; gap: 4px; opacity: 0.85; } 
    .ally-arr { margin-left: auto; color: var(--c-main); font-size: 20px; transition: transform .18s; opacity: .5; flex-shrink: 0; } 
    .ally-card:hover .ally-arr { transform: translateX(3px); opacity: 1; color: var(--c-cyan); } 
    .ally-loading-msg { text-align: center; font-size: 13px; font-weight: 800; color: #444; padding: 20px 0; }
    
    /* Section 13 Masters */ 
    .titled-box { background: linear-gradient(145deg, var(--bg2), var(--bg1)); border-radius: 16px; border: 1px solid rgba(255, 255, 255, 0.05); border-top: 3px solid var(--c-cyan); padding: 14px; font-family: 'Barlow Condensed', sans-serif; box-shadow: 0 12px 40px rgba(0, 0, 0, 0.8); position: relative; overflow: hidden; } 
    .titled-list-stack { display: flex; flex-direction: column; gap: 8px; position: relative; z-index: 2; max-height: 280px; overflow-y: auto; overflow-x: hidden; padding-right: 4px; } 
    .master-list-item { background: var(--bg3); border: 1px solid rgba(255, 255, 255, 0.02); border-left: 3px solid #444; border-radius: 6px; padding: 8px 10px; display: flex; align-items: center; gap: 10px; text-decoration: none; opacity: 0; transform: translateY(8px); animation: slideInRow 0.4s cubic-bezier(0.25, 1, 0.5, 1) forwards; transition: background 0.2s, border-color 0.2s; } 
    @keyframes slideInRow { to { opacity: 1; transform: translateY(0); } } 
    .master-list-item.tier-crimson { border-left-color: var(--c-crimson); } 
    .master-list-item.tier-cyan { border-left-color: var(--c-main); } 
    .master-list-item:hover { background: rgba(30, 30, 30, 0.8); border-left-color: var(--text-bright); } 
    .master-avatar-circle { width: 34px; height: 34px; border-radius: 50%; object-fit: cover; border: 1px solid #444; background: var(--bg0); flex-shrink: 0; } 
    .master-info-block { flex: 1; display: flex; flex-direction: column; min-width: 0; } 
    .master-identity-row { display: flex; align-items: center; gap: 6px; } 
    .master-name-text { font-size: 13px; font-weight: 800; color: var(--text-bright); white-space: nowrap; overflow: hidden; text-overflow: ellipsis; } 
    .master-tag-badge { font-family: 'Bebas Neue', cursive; font-size: 9px; color: #ffffff; padding: 0px 5px; border-radius: 3px; letter-spacing: 0.5px; line-height: 1.3; flex-shrink: 0; box-shadow: 0 1px 3px rgba(0,0,0,0.3); } 
    .master-list-item.tier-crimson .master-tag-badge { background: var(--c-crimson); color: #ffffff; } 
    .master-list-item.tier-cyan .master-tag-badge { background: var(--c-main); color: #000000; font-weight: 900; } 
    .master-meta-rating { font-size: 11px; font-weight: 700; color: #777; text-transform: uppercase; letter-spacing: 0.5px; transition: color 0.2s; } 
    .master-list-item:hover .master-meta-rating { color: var(--c-main); } 
    .titled-status-msg { text-align: center; font-size: 13px; font-weight: 800; color: #444; padding: 30px 0; width: 100%; } 
  </style>
</head>
<body>

<div class="imperium-sidebar-deck"> 
  <div class="sb-top-banner"> 
    <div class="crest-wrap"> 
      <div class="crest-glow"></div> 
      <svg class="crest-svg" viewBox="0 0 24 24" fill="none" stroke="url(#crestGrad)" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"> 
        <defs> 
          <linearGradient id="crestGrad" x1="0%" y1="0%" x2="100%" y2="100%"> 
            <stop offset="0%" stop-color="#00f2fe" /> 
            <stop offset="100%" stop-color="#bf55ec" /> 
          </linearGradient> 
        </defs> 
        <path d="M5 4l3 3 4-4 3 3 3-4v3H5V4z" stroke-width="1.2" fill="rgba(0, 242, 254, 0.05)" /> 
        <path d="M12 22s8-4 8-10V8l-8-3-8 3v4c0 6 8 10 8 10z" /> 
      </svg> 
    </div> 
    <div class="club-title">The Dragon's Imperium</div> 
    <div class="club-sub">The Strategic Citadel For <span>Dragons</span></div> 
    <div class="banner-designer">Sidebar Engine By UchihaMikulMD</div> 
  </div>

  <div class="imperium-separator"><div class="imperium-separator-laser"></div><div class="imperium-separator-node"></div></div>

  <div class="owner-box"> 
    <div class="owner-label">Owner & Founder</div> 
    <div class="owner-avatar-wrapper"> 
      <img class="owner-photo" src="https://images.chesscomfiles.com/uploads/v1/user/487074387.9039d619.200x200o.027dd1ba4dba.jpg" alt="UchihaMikulMD Profile"> 
      <div class="owner-badge" title="Verified Guildmaster">👑</div> 
    </div> 
    <div class="owner-name">@UchihaMikulMD</div> 
    <div class="owner-divider"></div> 
    <div class="owner-punchline"> "In the realm of the mind, chess is our battlefield, and the dragons rule the board." </div> 
  </div>

  <div class="imperium-separator"><div class="imperium-separator-laser"></div><div class="imperium-separator-node"></div></div>

  <div id="sonicCommandDeck" style="width: 100%; max-width: 420px; background: rgba(10, 10, 10, 0.75); backdrop-filter: blur(8px); -webkit-backdrop-filter: blur(8px); border: 1px solid rgba(0, 242, 254, 0.15); border-radius: 16px; padding: 20px; box-shadow: 0 12px 40px rgba(0, 0, 0, 0.6); font-family: 'Barlow Condensed', sans-serif; box-sizing: border-box; position: relative; overflow: hidden;">
      
      <div style="font-size: 11px; font-weight: 800; letter-spacing: 2px; color: #666; text-transform: uppercase; margin-bottom: 12px; text-align: center;">
          Imperium Audio Broadcast
      </div>

      <audio id="imperiumCoreAudio" src="https://www.dropbox.com/scl/fi/pr6mg8vumped7c3a03557/the-dragons-imperium.mp3?rlkey=suzm3900qz1fp95wl7wf00fme&st=njrk918g&raw=1" loop></audio>

      <div style="display: flex; align-items: center; gap: 20px;">
          <div id="sonicSpinner" style="width: 60px; height: 60px; border-radius: 50%; border: 2px solid #00f2fe; background: radial-gradient(circle, #111 30%, #222 70%); display: flex; align-items: center; justify-content: center; box-shadow: 0 0 15px rgba(0, 242, 254, 0.2); transition: transform 0.5s ease; animation: none;">
              <svg viewBox="0 0 24 24" fill="none" stroke="#bf55ec" stroke-width="2" style="width: 24px; height: 24px; filter: drop-shadow(0 0 4px rgba(191,85,236,0.6));">
                  <path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"></path>
              </svg>
          </div>

          <div style="flex-grow: 1;">
              <div id="trackStatusTitle" style="font-size: 16px; font-weight: 800; color: #fff; letter-spacing: 0.5px; text-transform: uppercase;">
                  OFFICIAL ANTHEM
              </div>
              <div id="trackStatusSub" style="font-size: 12px; font-weight: 600; color: #666; letter-spacing: 1px; margin-top: 2px;">
                  STATUS: DISENGAGED
              </div>
              <div style="display: flex; gap: 3px; margin-top: 8px; height: 10px; align-items: flex-end;">
                  <div class="sonic-bar" style="width: 4px; height: 3px; background: #00f2fe; border-radius: 2px; transition: height 0.2s ease;"></div>
                  <div class="sonic-bar" style="width: 4px; height: 3px; background: #bf55ec; border-radius: 2px; transition: height 0.2s ease;"></div>
                  <div class="sonic-bar" style="width: 4px; height: 3px; background: #00f2fe; border-radius: 2px; transition: height 0.2s ease;"></div>
                  <div class="sonic-bar" style="width: 4px; height: 3px; background: #bf55ec; border-radius: 2px; transition: height 0.2s ease;"></div>
                  <div class="sonic-bar" style="width: 4px; height: 3px; background: #00f2fe; border-radius: 2px; transition: height 0.2s ease;"></div>
              </div>
          </div>

          <button id="audioPlaybackTrigger" onclick="toggleImperiumAudio()" 
                  style="width: 50px; height: 50px; border-radius: 12px; border: 1px solid rgba(0, 242, 254, 0.3); background: rgba(0,0,0,0.5); display: flex; align-items: center; justify-content: center; cursor: pointer; transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1); box-shadow: inset 0 0 8px rgba(0,242,254,0.1);"
                  onmouseover="this.style.borderColor='#bf55ec'; this.style.boxShadow='0 0 15px rgba(191,85,236,0.4)';" 
                  onmouseout="if(!isAudioPlaying){ this.style.borderColor='rgba(0, 242, 254, 0.3)'; this.style.boxShadow='inset 0 0 8px rgba(0,242,254,0.1)'; }">
              <svg id="playbackIcon" viewBox="0 0 24 24" fill="#00f2fe" style="width: 20px; height: 20px; transition: all 0.2s ease;">
                  <polygon points="5 3 19 12 5 21 5 3"></polygon>
              </svg>
          </button>
      </div>
  </div>

  <style>
  @keyframes sonicSpinMatrix {
      from { transform: rotate(0deg); }
      to { transform: rotate(360deg); }
  }
  </style>

  <script>
  let isAudioPlaying = false;
  let sonicWaveInterval = null;

  function toggleImperiumAudio() {
      const audioTrack = document.getElementById("imperiumCoreAudio");
      const controlBtn = document.getElementById("audioPlaybackTrigger");
      const playIcon = document.getElementById("playbackIcon");
      const coreSpinner = document.getElementById("sonicSpinner");
      const statusSub = document.getElementById("trackStatusSub");
      const visualizerBars = document.querySelectorAll(".sonic-bar");

      if (!isAudioPlaying) {
          audioTrack.play().then(() => {
              isAudioPlaying = true;
              statusSub.innerText = "STATUS: BROADCASTING";
              statusSub.style.color = "#00f2fe";
              
              controlBtn.style.borderColor = "#00f2fe";
              playIcon.innerHTML = `<rect x="6" y="4" width="4" height="16"></rect><rect x="14" y="4" width="4" height="16"></rect>`;
              playIcon.setAttribute("fill", "#00f2fe");
              
              coreSpinner.style.animation = "sonicSpinMatrix 3s linear infinite";
              coreSpinner.style.borderColor = "#bf55ec";
              
              sonicWaveInterval = setInterval(() => {
                  visualizerBars.forEach(bar => {
                      const dynamicHeight = Math.floor(Math.random() * 16) + 4;
                      bar.style.height = dynamicHeight + "px";
                  });
              }, 150);
          }).catch(err => {
              console.warn("Audio interaction delay encountered.", err);
              statusSub.innerText = "TAP ANYWHERE ON SCREEN FIRST!";
              statusSub.style.color = "#ff3333";
          });
      } else {
          audioTrack.pause();
          isAudioPlaying = false;
          statusSub.innerText = "STATUS: DISENGAGED";
          statusSub.style.color = "#666";
          
          playIcon.innerHTML = `<polygon points="5 3 19 12 5 21 5 3"></polygon>`;
          playIcon.setAttribute("fill", "#00f2fe");
          controlBtn.style.borderColor = "rgba(0, 242, 254, 0.3)";
          coreSpinner.style.animation = "none";
          coreSpinner.style.borderColor = "#00f2fe";
          
          clearInterval(sonicWaveInterval);
          visualizerBars.forEach(bar => bar.style.height = "3px");
      }
  }
  </script>

  <div class="imperium-separator"><div class="imperium-separator-laser"></div><div class="imperium-separator-node"></div></div>

  <div class="roster-container"> 
    <div class="count-box"> 
      <div class="count-display"> 
        <span class="count-icon">👥</span> 
        <div class="count-info"> 
          <div class="count-value" id="clubMemberCount">⏳</div> 
          <div class="count-label">Total Dragons</div> 
        </div> 
        <div class="live-pulse-container" title="Connected Live to Chess.com Engine"> 
          <span class="pulse-ring"></span> 
          <span class="pulse-dot"></span> 
        </div> 
      </div> 
    </div> 
    <div class="members-box"> 
      <div class="members-title">🔥 Latest Members</div> 
      <div class="members-list" id="membersList"> 
        <div class="member-item shimmer-wave" style="height:48px; margin-bottom:6px;"></div>
        <div class="member-item shimmer-wave" style="height:48px; margin-bottom:6px;"></div>
        <div class="member-item shimmer-wave" style="height:48px;"></div>
      </div> 
    </div> 
  </div>

  <div class="imperium-separator"><div class="imperium-separator-laser"></div><div class="imperium-separator-node"></div></div>

  <div class="matches-box"> 
    <div class="matches-header">Events & Matches</div> 
    <div class="matches-tabs" id="matchesTabs"> 
      <button class="matches-tab active" data-tab="live"> 
        <span class="live-dot"></span> Live <span class="tab-count" id="countLive">0</span> 
      </button> 
      <button class="matches-tab" data-tab="upcoming"> 📅 Upcoming <span class="tab-count" id="countUpcoming">0</span> </button> 
      <button class="matches-tab" data-tab="recent"> 🏁 Recent <span class="tab-count" id="countRecent">0</span> </button> 
    </div> 
    <div class="matches-list" id="matchesList"> 
      <div class="matches-empty"><span>⏳</span>Loading matches...</div> 
    </div> 
  </div>

  <div class="imperium-separator"><div class="imperium-separator-laser"></div><div class="imperium-separator-node"></div></div>

  <div class="countdown-box"> 
    <div class="sec-hd"> 
      <div class="sec-hd-bar"></div> 
      <div class="sec-hd-text"> 
        <div class="sec-hd-title">Next Battle Ticker</div> 
        <div class="sec-hd-sub">Live Engine Countdown</div> </div> 
      <div class="sec-hd-line"></div> 
    </div> 
    <div id="tickerStateContainer"> 
      <div class="ticker-status-msg">Scanning engine match matrices...</div> 
    </div> 
  </div>

  <div class="imperium-separator"><div class="imperium-separator-laser"></div><div class="imperium-separator-node"></div></div>

  <div class="podium-box"> 
    <div class="sec-hd"> 
      <div class="sec-hd-bar"></div> 
      <div class="sec-hd-text"> 
        <div class="sec-hd-title">Arena Champions</div> 
        <div class="sec-hd-sub">Top Faction Overlords</div> </div> 
      <div class="sec-hd-line"></div> 
      <div class="sec-hd-icon">🏆</div> 
    </div> 
    <div class="podium-tabs-row" id="podiumTabsStrip"> 
      <button class="podium-tab-btn active" data-type="blitz">⚡ Blitz</button> 
      <button class="podium-tab-btn" data-type="rapid">⏱️ Rapid</button> 
      <button class="podium-tab-btn" data-type="bullet">🏹 Bullet</button> 
    </div> 
    <div class="podium-display-stage" id="podiumStage"> 
      <div class="podium-loading-fallback">⏳ Sorting guild champions matrix...</div> 
    </div> 
  </div>

  <div class="imperium-separator"><div class="imperium-separator-laser"></div><div class="imperium-separator-node"></div></div>

  <div class="gauges-box"> 
    <div class="sec-hd"> 
      <div class="sec-hd-bar"></div> 
      <div class="sec-hd-text"> 
        <div class="sec-hd-title">Tactical Performance</div> 
        <div class="sec-hd-sub">Live Conquest Metrics</div> </div> 
      <div class="sec-hd-line"></div> 
      <div class="sec-hd-icon">📊</div> 
    </div> 
    <div class="gauge-matrix-stack" id="gaugesContainer"> 
      <div class="gauge-loading-fallback">⏳ Evaluating recent battle campaigns...</div> 
    </div> 
  </div>

  <div class="imperium-separator"><div class="imperium-separator-laser"></div><div class="imperium-separator-node"></div></div>

  <div class="puzzle-box"> 
    <div class="sec-hd"> 
      <div class="sec-hd-bar"></div> 
      <div class="sec-hd-text"> 
        <div class="sec-hd-title">Daily Tactical Warmup</div> 
        <div class="sec-hd-sub">Live Chess.com puzzle</div> </div> 
      <div class="sec-hd-line"></div> 
      <div class="sec-hd-icon">🧩</div> 
    </div> 
    <div id="puzzleEngineContainer" style="min-height: 260px; display: flex; align-items: center; justify-content: center;"> 
      <div class="puzzle-loading-msg">⏳ Fetching today's chess matrix...</div> 
    </div> 
  </div>

  <div class="imperium-separator"><div class="imperium-separator-laser"></div><div class="imperium-separator-node"></div></div>

  <div class="bday-box"> 
    <div class="sec-hd"> 
      <div class="sec-hd-bar"></div> 
      <div class="sec-hd-text"> 
        <div class="sec-hd-title">Imperium Birthdays</div> 
        <div class="sec-hd-sub">Track guild celebrations</div> </div> 
      <div class="sec-hd-line"></div> 
    </div> 
    <div class="bday-form"> 
      <input type="text" id="bdayUser" class="bday-input" placeholder="🔍 Chess.com Username..."> 
      <div class="bday-row"> 
        <select id="bdayDate" class="bday-select"><option value="" disabled selected>Select Date</option></select> 
        <select id="bdayMonth" class="bday-select"> 
          <option value="" disabled selected>Select Month</option> 
          <option value="0">January</option><option value="1">February</option><option value="2">March</option><option value="3">April</option><option value="4">May</option><option value="5">June</option><option value="6">July</option><option value="7">August</option><option value="8">September</option><option value="9">October</option><option value="10">November</option><option value="11">December</option> 
        </select> 
      </div> 
      <textarea id="bdayNote" class="bday-textarea" placeholder="📃 Optional custom note..."></textarea> 
      <button id="saveBdayBtn" class="bday-btn">Save Birthday 🪄</button> 
    </div> 
    <div class="bday-list" id="birthdayList"> 
      <div class="bday-empty">No tracked birthdays yet.</div> 
    </div> 
  </div>

  <div class="imperium-separator"><div class="imperium-separator-laser"></div><div class="imperium-separator-node"></div></div>

  <div class="books-section"> 
    <div class="sec-hd"> 
      <div class="sec-hd-bar"></div> 
      <div class="sec-hd-text"> 
        <div class="sec-hd-title">Free Books</div> 
        <div class="sec-hd-sub">100% free · click to download</div> </div> 
      <div class="sec-hd-line"></div> 
      <div class="sec-hd-icon">📚</div> 
    </div> 
    <div class="books-grid"> 
      <a class="book-card" href="https://archive.org/download/AronNimzowitschMySystem/Aron%20Nimzowitsch%20-%20My%20System.pdf" target="_blank" rel="noopener"> 
        <img src="https://images.chesscomfiles.com/uploads/v1/images_users/tiny_mce/Aronole/phpZ3dl12.jpg" alt="My System Cover"> 
        <div class="book-label">My System</div> 
      </a> 
      <a class="book-card" href="https://drive.google.com/file/d/1XZ7wk9Wte8nP-kh_f5wysvbHgLzm-tex/view?usp=drivesdk" target="_blank" rel="noopener"> 
        <img src="https://images.chesscomfiles.com/uploads/v1/images_users/tiny_mce/Aronole/php2aaPk4.jpg" alt="Chess Fundamentals Cover"> 
        <div class="book-label">Fundamentals</div> 
      </a> 
      <a class="book-card" href="https://archive.org/download/laskersmanualofc00lask/laskersmanualofc00lask.pdf" target="_blank" rel="noopener"> 
        <img src="https://i.pinimg.com/736x/8b/37/03/8b370393c76d197f3173a887af4e89a1.jpg" alt="Lasker's Manual Cover"> 
        <div class="book-label">Lasker's Manual</div> 
      </a> 
      <a class="book-card" href="https://archive.org/download/TheGameOfChessSiegbertTarrasch/The%20Game%20of%20Chess%20-%20Siegbert%20Tarrasch.pdf" target="_blank" rel="noopener"> 
        <img src="https://m.media-amazon.com/images/I/61ypDK1iseL._AC_UF1000,1000_QL80_.jpg" alt="The Game of Chess Cover"> 
        <div class="book-label">Game of Chess</div> 
      </a> 
    </div> 
  </div>

  <div class="imperium-separator"><div class="imperium-separator-laser"></div><div class="imperium-separator-node"></div></div>

  <div class="music-card" id="musicCard"> 
    <div class="now-playing-banner"> 
      <div class="disc-wrap" id="disc">🎵</div> 
      <div class="track-info"> 
        <div class="track-label">Now Playing</div> 
        <div class="track-name" id="trackName">Choose a song ↓</div> 
      </div> 
      <div class="eq-bars" id="eqBars"> 
        <div class="eq-bar paused"></div><div class="eq-bar paused"></div><div class="eq-bar paused"></div> 
      </div> 
    </div> 
    <div class="music-progress-section"> 
      <div class="music-progress-track" id="progressTrack"> 
        <div class="music-progress-fill" id="progressFill"><div class="music-progress-knob" id="progressKnob"></div></div> 
      </div> 
      <div class="music-time-row"><span id="timeCur">0:00</span><span id="timeDur">0:00</span></div> 
    </div> 
    <div class="music-controls-row"> 
      <button class="mcbtn sm" id="btnPrev" title="Previous"> 
        <svg viewBox="0 0 24 24" fill="none" stroke="#00f2fe" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polygon points="19 20 9 12 19 4 19 20"/><line x1="5" y1="19" x2="5" y2="5"/></svg> 
      </button> 
      <button class="mcbtn play" id="btnPlay" title="Play"> 
        <svg id="iconPlay" viewBox="0 0 24 24" fill="white" stroke="none"><polygon points="5 3 19 12 5 21 5 3"/></svg> 
      </button> 
      <button class="mcbtn sm" id="btnNext" title="Next"> 
        <svg viewBox="0 0 24 24" fill="none" stroke="#00f2fe" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polygon points="5 4 15 12 5 20 5 4"/><line x1="19" y1="5" x2="19" y2="19"/></svg> 
      </button> 
      <button class="mcbtn sm" id="btnLoop" title="Loop off"> 
        <svg id="iconLoop" viewBox="0 0 24 24" fill="none" stroke="#00f2fe" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="17 1 21 5 17 9"/><path d="M3 11V9a4 4 0 0 1 4-4h14"/><polyline points="7 23 3 19 7 15"/><path d="M21 13v2a4 4 0 0 1-4 4H3"/></svg> 
      </button> 
      <div class="music-vol-row"> 
        <div class="music-vol-icon" id="btnVol" title="Mute"> 
          <svg id="iconVol" viewBox="0 0 24 24" fill="none" stroke="#00f2fe" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><polygon points="11 5 6 9 2 9 2 15 6 15 11 19 11 5"/><path d="M19.07 4.93a10 10 0 0 1 0 14.14"/></svg> 
        </div> 
        <div class="music-vol-track" id="volTrack"> 
          <div class="music-vol-fill" id="volFill"></div><div class="music-vol-knob" id="volKnob"></div> 
        </div> 
      </div> 
    </div> 
    <div class="music-search-section"> 
      <div class="music-search-label">Search &amp; Add Songs</div> 
      <input class="music-search-input" id="searchInput" type="text" placeholder="🔍 Type a song name..."> 
      <div class="music-search-dropdown" id="searchDropdown"></div> 
    </div> 
    <div class="music-playlist-section"> 
      <div class="music-playlist-label">Queue <span class="music-playlist-count" id="plCount">0</span></div> 
      <div class="music-playlist-scroll" id="playlist"></div> 
    </div> 
  </div> <audio id="audio"></audio>

  <div class="imperium-separator"><div class="imperium-separator-laser"></div><div class="imperium-separator-node"></div></div>

  <div class="alliances-box"> 
    <div class="sec-hd"> 
      <div class="sec-hd-bar"></div> 
      <div class="sec-hd-text"> 
        <div class="sec-hd-title">Allied Coalitions</div> 
        <div class="sec-hd-sub">Partner Clubs Network</div> </div> 
      <div class="sec-hd-line"></div> 
      <div class="sec-hd-icon">🤝</div> 
    </div> 
    <div class="ally-list-stack" id="alliancesList"> 
      <div class="ally-loading-msg">⏳ Mapping faction networks...</div> 
    </div> 
  </div>

  <div class="imperium-separator"><div class="imperium-separator-laser"></div><div class="imperium-separator-node"></div></div>

  <div class="titled-box"> 
    <div class="sec-hd"> 
      <div class="sec-hd-bar"></div> 
      <div class="sec-hd-text"> 
        <div class="sec-hd-title">Citadel Masters</div> 
        <div class="sec-hd-sub">Titled Players Roster</div> </div> 
      <div class="sec-hd-line"></div> 
      <div class="sec-hd-icon">👑</div> 
    </div> 
    <div class="titled-list-stack" id="titledPlayersList"> 
      <div class="titled-status-msg">Scanning club directory for masters...</div> 
    </div> 
  </div>
  
  <div style="clear: both; display: block; width: 100%; text-align: center; font-family: 'Barlow Condensed', sans-serif; font-size: 11px; font-weight: 800; letter-spacing: 2px; color: #00f2fe; text-transform: uppercase; margin-top: 30px; margin-bottom: 10px;"> The Dragon's Imperium © 2026</div>
</div>

<script> 
(function UnifiedImperiumEngine(){ 
  const CLUB_SLUG = "the-dragons-imperium"; 
  const DEFAULT_PAWN = "https://taki2023.github.io/taki/default-pawn.png"; 

  // UTILS 
  function humanizeSlug(slug){ return slug.replace(/-/g, " ").replace(/\b\w/g, c => c.toUpperCase()); } 
  function matchUrlFromApiId(apiId){ return "https://www.chess.com/club/matches/" + apiId.split("/").pop(); }

  // MODULE 03: LIVE MEMBERS 
  async function fetchClubMemberCount() { 
    const counterDisplay = document.getElementById("clubMemberCount"); 
    try { 
      const res = await fetch(`https://api.chess.com/pub/club/${CLUB_SLUG}`); 
      if (!res.ok) throw new Error(); 
      const payload = await res.json(); 
      if (payload && typeof payload.members_count !== 'undefined') { 
        counterDisplay.textContent = payload.members_count.toLocaleString(); 
      } 
    } catch (e) { counterDisplay.textContent = "Offline"; } 
  }

  function timeAgo(timestamp) { 
    const diffSeconds = Math.floor((Date.now() - (timestamp * 1000)) / 1000); 
    if (diffSeconds < 60) return `${diffSeconds}s ago`; 
    const minutes = Math.floor(diffSeconds / 60); 
    if (minutes < 60) return `${minutes}m ago`; 
    const hours = Math.floor(minutes / 60); 
    if (hours < 24) return `${hours}h ago`; 
    const days = Math.floor(hours / 24); 
    if (days < 7) return `${days}d ago`; 
    return `${Math.floor(days / 7)}w ago`; 
  }

  async function loadNewestMembers() { 
    const box = document.getElementById("membersList"); 
    try { 
      const r = await fetch(`https://api.chess.com/pub/club/${CLUB_SLUG}/members`); 
      if (!r.ok) throw new Error(); 
      const d = await r.json(); 
      const members = [...(d.weekly||[]), ...(d.monthly||[]), ...(d.all_time||[])]; 
      if(!members.length) { 
        box.innerHTML = '<div class="error-msg">No active member data found.</div>'; 
        return; 
      } 
      members.sort((a, b) => b.joined - a.joined); 
      
      // Limit processing to slice to avoid rate limits
      const promises = members.slice(0, 3).map(async (m) => { 
        try { 
          const [pj, stats] = await Promise.all([ 
            fetch(`https://api.chess.com/pub/player/${m.username}`).then(res => res.ok ? res.json() : {}), 
            fetch(`https://api.chess.com/pub/player/${m.username}/stats`).then(res => res.ok ? res.json() : {}) 
          ]); 
          const ratings = [ 
            {type:"Rapid", value: stats.chess_rapid?.last?.rating}, 
            {type:"Blitz", value: stats.chess_blitz?.last?.rating}, 
            {type:"Bullet", value: stats.chess_bullet?.last?.rating}, 
            {type:"Daily", value: stats.chess_daily?.last?.rating} 
          ].filter(x => x.value); 
          const best = ratings.length ? ratings.sort((a,b)=>b.value-a.value)[0] : {type:"New", value:"—"}; 
          return { username: m.username, avatar: pj.avatar || DEFAULT_PAWN, ratingType: best.type, ratingValue: best.value, joined: m.joined }; 
        } catch(e) { 
          return { username: m.username, avatar: DEFAULT_PAWN, ratingType: "Chess", ratingValue: "—", joined: m.joined }; 
        } 
      }); 
      const resolved = await Promise.all(promises); 
      box.innerHTML = resolved.map(m => ` 
        <a class="member-item" href="https://www.chess.com/member/${m.username}" target="_blank"> 
          <img class="member-avatar" src="${m.avatar}" onerror="this.src='${DEFAULT_PAWN}';"> 
          <div class="member-info"> 
            <div class="member-name">@${m.username}</div> 
            <div class="member-meta"><span class="member-rating">${m.ratingType}: ${m.ratingValue}</span><span class="member-joined">⏱ ${timeAgo(m.joined)}</span></div> 
          </div> 
        </a> `).join(""); 
    } catch (err) { 
      box.innerHTML = '<div class="error-msg">Unable to parse live data.</div>'; 
    } 
  }

  // MODULE 04 & MODULE 07: MATCH CALENDAR & PERFORMANCE 
  let matchesCache = { live: [], upcoming: [], recent: [] }; 
  let activeMatchTab = "live";

  function matchTimeLabel(timestamp){ 
    if (!timestamp) return "TBD"; 
    const diff = (timestamp * 1000) - Date.now(); 
    const absDays = Math.round(Math.abs(diff) / (1000*60*60*24)); 
    if (diff > 0) { 
      if (diff < 1000*60*60) return "soon"; 
      if (diff < 1000*60*60*24) return `in ${Math.round(diff/(1000*60*60))}h`; 
      return `in ${absDays}d`; 
    } 
    if (-diff < 1000*60*60*24) return "today"; 
    if (absDays < 7) return `${absDays}d ago`; 
    return `${Math.round(absDays/7)}w ago`; 
  }

  async function loadMatchesAndGauges(){ 
    try { 
      const res = await fetch(`https://api.chess.com/pub/club/${CLUB_SLUG}/matches`); 
      if (!res.ok) throw new Error(); 
      const data = await res.json(); 
      
      matchesCache.live = (data.in_progress || []).slice().sort((a,b)=>b.start_time-a.start_time); 
      matchesCache.upcoming = (data.registered || []).slice().sort((a,b)=>a.start_time-b.start_time); 
      matchesCache.recent = (data.finished || []).slice().sort((a,b)=>b.start_time-a.start_time).slice(0, 15); 
      
      document.getElementById("countLive").textContent = matchesCache.live.length; 
      document.getElementById("countUpcoming").textContent = matchesCache.upcoming.length; 
      document.getElementById("countRecent").textContent = matchesCache.recent.length; 
      renderMatches(); 
      hydratePerformanceGauges(data.finished || []); 
    } catch (err) { 
      document.getElementById("matchesList").innerHTML = '<div class="matches-empty"><span>📡</span>Failed to load match schedules</div>'; 
    } 
  }

  function renderMatches(){ 
    const list = document.getElementById("matchesList"); 
    const items = matchesCache[activeMatchTab] || []; 
    if (!items.length){ 
      const emptyMsg = activeMatchTab === "live" ? "No matches in battle right now" : activeMatchTab === "upcoming" ? "No upcoming matches scheduled" : "No finished matches found"; 
      list.innerHTML = `<div class="matches-empty"><span>🏁</span>${emptyMsg}</div>`; 
      return; 
    } 
    list.innerHTML = items.map(m => { 
      const oppName = humanizeSlug(m.opponent.split("/").pop()); 
      let badgeClass = activeMatchTab === "live" ? "live" : activeMatchTab === "upcoming" ? "upcoming" : (m.result || "draw"); 
      let badgeIcon = activeMatchTab === "live" ? "▶" : activeMatchTab === "upcoming" ? "🕒" : (m.result === "win" ? "W" : m.result === "lose" ? "L" : "D"); 
      return ` 
        <a class="match-item ${activeMatchTab === 'live'?'live':''}" href="${matchUrlFromApiId(m["@id"])}" target="_blank"> 
          <div class="match-result-badge ${badgeClass}">${badgeIcon}</div> 
          <div class="match-info"> 
            <div class="match-name">${(m.name || "Club Battle").replace(/</g,"&lt;")}</div> 
            <div class="match-meta"><span class="match-vs">vs ${oppName}</span><span class="match-time-class">${m.time_class || "daily"}</span><span class="match-time">${matchTimeLabel(m.start_time)}</span></div> 
          </div> 
        </a> `; 
    }).join(""); 
  }

  function hydratePerformanceGauges(finishedMatches) { 
    const container = document.getElementById("gaugesContainer"); 
    if (!container || !finishedMatches.length) return; 
    let wins = 0, losses = 0, draws = 0; 
    finishedMatches.forEach(m => { 
      if (m.result === 'win') wins++; 
      else if (m.result === 'lose') losses++; 
      else draws++; 
    }); 
    const total = wins + losses + draws; 
    container.innerHTML = ` 
      <div class="gauge-row"><div class="gauge-label-strip"><span class="gauge-name" style="color:var(--c-main);">Victories</span><span class="gauge-count-tag"><span>${wins}</span> / ${total}</span></div><div class="gauge-track-bar"><div class="gauge-fill fill-cyan" id="fillWins"></div></div></div> 
      <div class="gauge-row"><div class="gauge-label-strip"><span class="gauge-name" style="color:var(--c-cyan);">Defeats</span><span class="gauge-count-tag"><span>${losses}</span> / ${total}</span></div><div class="gauge-track-bar"><div class="gauge-fill fill-purple" id="fillLosses"></div></div></div> 
      <div class="gauge-row"><div class="gauge-label-strip"><span class="gauge-name" style="color:#aaa;">Draws</span><span class="gauge-count-tag"><span>${draws}</span> / ${total}</span></div><div class="gauge-track-bar"><div class="gauge-fill fill-charcoal" id="fillDraws"></div></div></div>`; 
    setTimeout(() => { 
      document.getElementById("fillWins").style.width = ((wins/total)*100).toFixed(1) + '%'; 
      document.getElementById("fillLosses").style.width = ((losses/total)*100).toFixed(1) + '%'; 
      document.getElementById("fillDraws").style.width = ((draws/total)*100).toFixed(1) + '%'; 
    }, 100); 
  }

  // MODULE 05: BATTLE TICKER 
  let activeTimerLoop = null, targetMatchTimestamp = 0; 
  async function queryClosestMatch() { 
    try { 
      const res = await fetch(`https://api.chess.com/pub/club/${CLUB_SLUG}/matches`); 
      const data = await res.json(); 
      const validMatches = (data.registered || []).filter(m => m.start_time && m.start_time > Math.floor(Date.now() / 1000)); 
      if (!validMatches.length) { 
        clearInterval(activeTimerLoop); 
        document.getElementById("tickerStateContainer").innerHTML = `<div class="ticker-status-msg">🛡️ No upcoming battles scheduled</div>`; 
        return; 
      } 
      validMatches.sort((a, b) => a.start_time - b.start_time); 
      const target = validMatches[0]; 
      targetMatchTimestamp = target.start_time; 
      const oppName = humanizeSlug(target.opponent.split("/").pop()); 
      document.getElementById("tickerStateContainer").innerHTML = ` 
        <div class="match-target-panel"><div class="match-target-title">${target.name.replace(/</g, "&lt;")}</div><div class="match-target-opp">Clash vs <span>${oppName}</span></div></div> 
        <div class="ticker-display-row"> 
          <div class="ticker-block"><div class="ticker-value" id="tickHrs">00</div><div class="ticker-label">Hrs</div></div><div class="ticker-colon">:</div> 
          <div class="ticker-block"><div class="ticker-value" id="tickMins">00</div><div class="ticker-label">Mins</div></div><div class="ticker-colon">:</div> 
          <div class="ticker-block"><div class="ticker-value" id="tickSecs">00</div><div class="ticker-label">Secs</div></div> 
        </div><a href="${matchUrlFromApiId(target["@id"])}" target="_blank" class="ticker-action-btn">Register For Battle ⚔️</a>`; 
      clearInterval(activeTimerLoop); 
      activeTimerLoop = setInterval(executeClockTick, 1000); 
      executeClockTick(); 
    } catch (e) {} 
  } 
  
  function executeClockTick() { 
    const deltaSec = Math.floor((targetMatchTimestamp * 1000 - Date.now()) / 1000); 
    if (deltaSec <= 0) { 
      clearInterval(activeTimerLoop); 
      queryClosestMatch(); 
      return; 
    } 
    const h = Math.floor(deltaSec / 3600), m = Math.floor((deltaSec % 3600) / 60), s = deltaSec % 60; 
    const hEl = document.getElementById("tickHrs"), mEl = document.getElementById("tickMins"), sEl = document.getElementById("tickSecs"); 
    if (hEl) { 
      hEl.textContent = String(h).padStart(2,"0"); 
      mEl.textContent = String(m).padStart(2,"0"); 
      sEl.textContent = String(s).padStart(2,"0"); 
    } 
  }

  // MODULE 06 & MODULE 13: PODIUM & MASTERS ROSTER
  let currentPodiumMode = "blitz", masterCacheList = []; 
  
  async function loadPodiumAndMasters(force = false) { 
    try { 
      if (!masterCacheList.length || force) { 
        const r = await fetch(`https://api.chess.com/pub/club/${CLUB_SLUG}/members`); 
        const data = await r.json(); 
        masterCacheList = [...(data.weekly||[]), ...(data.monthly||[]), ...(data.all_time||[])]; 
      } 
      
      // CRITICAL PERFORMANCE PROTECTION: Limit checking profile queries to top slice to prevent client-side rate limits
      const processingSlice = masterCacheList.slice(0, 15);
      
      const promises = processingSlice.map(async (m) => { 
        try { 
          const [pData, sData] = await Promise.all([ 
            fetch(`https://api.chess.com/pub/player/${m.username}`).then(res => res.ok?res.json():null), 
            fetch(`https://api.chess.com/pub/player/${m.username}/stats`).then(res => res.ok?res.json():{}) 
          ]); 
          if(!pData) return null; 
          let pScore = currentPodiumMode==="blitz"? sData.chess_blitz?.last?.rating : currentPodiumMode==="rapid"? sData.chess_rapid?.last?.rating : sData.chess_bullet?.last?.rating; 
          const ratings = [{type:"Blitz", s:sData.chess_blitz?.last?.rating},{type:"Rapid", s:sData.chess_rapid?.last?.rating},{type:"Daily", s:sData.chess_daily?.last?.rating},{type:"Bullet", s:sData.chess_bullet?.last?.rating}].filter(x=>x.s); 
          const topR = ratings.length ? ratings.sort((a,b)=>b.s-a.s)[0] : {type:"Rating", s:"—"};
          return { username:m.username, avatar: pData.avatar || DEFAULT_PAWN, title: pData.title, rating: pScore || 0, topLabel: `${topR.type} • ${topR.s}`, maxScore: topR.s!=="—"?topR.s:0 }; 
        } catch(e) { return null; } 
      }); 
      
      const profiles = (await Promise.all(promises)).filter(x => x !== null); 
      const stage = document.getElementById("podiumStage"); 
      const podiumPlayers = profiles.filter(p => p.rating > 0).sort((a,b)=>b.rating-a.rating); 
      
      if(podiumPlayers.length > 0) { 
        const first = podiumPlayers[0] || {username:"Empty", avatar:DEFAULT_PAWN, rating:"—"}; 
        const second = podiumPlayers[1] || {username:"Empty", avatar:DEFAULT_PAWN, rating:"—"}; 
        const third = podiumPlayers[2] || {username:"Empty", avatar:DEFAULT_PAWN, rating:"—"}; 
        stage.innerHTML = ` 
          <a class="podium-pillar-wrap rank-2" href="https://www.chess.com/member/${second.username}" target="_blank"><div class="podium-avatar-frame"><span class="podium-crown-medal">🥈</span><img class="podium-img" src="${second.avatar}"></div><div class="podium-base-pillar"><span class="p-name">@${second.username}</span><span class="p-score">${second.rating}</span><span class="p-rank-num">#2</span></div></a> 
          <a class="podium-pillar-wrap rank-1" href="https://www.chess.com/member/${first.username}" target="_blank"><div class="podium-avatar-frame"><span class="podium-crown-medal">🥇</span><img class="podium-img" src="${first.avatar}"></div><div class="podium-base-pillar"><span class="p-name">@${first.username}</span><span class="p-score">${first.rating}</span><span class="p-rank-num">#1</span></div></a> 
          <a class="podium-pillar-wrap rank-3" href="https://www.chess.com/member/${third.username}" target="_blank"><div class="podium-avatar-frame"><span class="podium-crown-medal">🥉</span><img class="podium-img" src="${third.avatar}"></div><div class="podium-base-pillar"><span class="p-name">@${third.username}</span><span class="p-score">${third.rating}</span><span class="p-rank-num">#3</span></div></a>`; 
      } else { 
        stage.innerHTML = `<div class="podium-loading-fallback">🛡️ No active ratings recorded.</div>`; 
      }
      
      const masters = profiles.filter(p => p.title).sort((a,b)=>b.maxScore-a.maxScore); 
      const mList = document.getElementById("titledPlayersList"); 
      if (masters.length) { 
        mList.innerHTML = masters.map((m, idx) => { 
          const t = m.title.toUpperCase(); 
          const tier = ["GM","IM","FM","WGM","WIM","WFM"].includes(t) ? "tier-crimson" : "tier-cyan"; 
          return `<a class="master-list-item ${tier}" href="https://www.chess.com/member/${m.username}" target="_blank" style="animation-delay: ${idx*0.04}s"><img class="master-avatar-circle" src="${m.avatar}"><div class="master-info-block"><div class="master-identity-row"><span class="master-tag-badge">${m.title}</span><span class="master-name-text">@${m.username}</span></div></div><div class="master-meta-rating">${m.topLabel}</div></a>`; 
        }).join(""); 
      } else { 
        mList.innerHTML = `<div class="titled-status-msg">🛡️ No titled masters inside the club yet</div>`; 
      } 
    } catch(e) {} 
  }

  // MODULE 08: PUZZLE 
  async function fetchDailyPuzzleData() { 
    const container = document.getElementById('puzzleEngineContainer'); 
    try { 
      const res = await fetch('https://api.chess.com/pub/puzzle'); 
      const data = await res.json(); 
      container.innerHTML = `<div class="puzzle-display-card"><div class="puzzle-board-frame"><img class="puzzle-img" src="${data.image}" alt="Puzzle"></div><div class="puzzle-meta-panel"><div class="puzzle-title">${data.title.replace(/</g, "&lt;")}</div><div class="puzzle-desc">Objective: Find the <span>Best Move</span></div></div><a href="${data.url}" target="_blank" class="puzzle-action-btn">Solve Puzzle ♟️</a></div>`; 
    } catch (err) { 
      container.innerHTML = `<div class="puzzle-loading-msg">📡 Puzzle sync pipeline down.</div>`; 
    } 
  }

  // MODULE 09: BIRTHDAYS ENGINE 
  function initBirthdays() { 
    const dSel = document.getElementById("bdayDate"), mSel = document.getElementById("bdayMonth"), uInp = document.getElementById("bdayUser"), nInp = document.getElementById("bdayNote"), sBtn = document.getElementById("saveBdayBtn"), listC = document.getElementById("birthdayList"); 
    for(let i=1; i<=31; i++) { 
      const o = document.createElement("option"); o.value=i; o.textContent=i; dSel.appendChild(o); 
    } 
    const MONTHS = ["Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"]; 
    const getB = () => { try { return JSON.parse(localStorage.getItem("imperium_birthdays")) || []; } catch(e){return [];} }; 
    const remB = (idx) => { 
      if(prompt("Enter Admin Password:") === "PMK") { 
        const b = getB(); 
        b.sort((x,y)=>cDays(x.month,x.day)-cDays(y.month,y.day)); 
        b.splice(idx,1); 
        localStorage.setItem("imperium_birthdays",JSON.stringify(b)); 
        rB(); 
      } else { alert("Access Denied."); } 
    }; 
    const cDays = (m, d) => { 
      const t = new Date(); t.setHours(0,0,0,0); let tg = new Date(t.getFullYear(), m, d); 
      if (tg < t) tg.setFullYear(t.getFullYear()+1); 
      return Math.ceil((tg-t)/(1000*60*60*24))%365; 
    }; 
    const rB = () => { 
      const b = getB(); 
      if(!b.length) { 
        listC.innerHTML='<div class="bday-empty">No tracked birthdays yet.</div>'; 
        return; 
      } 
      b.sort((x,y)=>cDays(x.month,x.day)-cDays(y.month,y.day)); 
      listC.innerHTML = b.map((x,i)=>{ 
        const dl=cDays(x.month,x.day), it=dl===0; 
        return `<div class="bday-item ${it?'highlight-today':''}"><div class="bday-avatar">${it?'👑':'🎂'}</div><div class="bday-info"><div class="bday-name-row"><span class="bday-name">@${x.username.replace(/</g,"&lt;")}</span>${it?'<span class="bday-celebration">HAPPY BIRTHDAY 🎈</span>':''}</div>${x.note?`<div class="bday-note">${x.note.replace(/</g,"&lt;")}</div>`:''}</div><div class="bday-date-badge">${MONTHS[x.month]} ${x.day}</div><span class="bday-delete" data-i="${i}">✕</span></div>`; 
      }).join(""); 
      listC.querySelectorAll(".bday-delete").forEach(btn=>btn.onclick=()=>remB(parseInt(btn.dataset.i))); 
    }; 
    sBtn.onclick=()=>{ 
      const u=uInp.value.trim(), d=parseInt(dSel.value), m=parseInt(mSel.value), n=nInp.value.trim(); 
      if(!u||isNaN(d)||isNaN(m)){alert("Fill Required Data!"); return;} 
      const b=getB(); b.push({username:u,day:d,month:m,note:n}); 
      localStorage.setItem("imperium_birthdays",JSON.stringify(b)); 
      uInp.value=""; nInp.value=""; dSel.value=""; mSel.value=""; rB(); 
    }; 
    rB(); 
  }

  // MODULE 11: MUSIC PLAYER ENGINE 
  function initMusicPlayer() { 
    const DB = [ 
      { title:"Headlights", src:"https://www.dropbox.com/scl/fi/31bp454p5grmy2qtyk06s/Headlights-feat.-KIDDO-Alok-Alan-Walker-KIDDO.mp3?rlkey=97pg07lg7alyzv2xmupgzpxkb&st=hn4nbr7o&raw=1" }, 
      { title:"No Batidao", src:"https://www.dropbox.com/scl/fi/4hzh47wzbfogz4lsncmsw/NO-BATID-O-ZXKAI-x-NAGI-1.mp3?rlkey=qol510o9k54yieve4vjv8hj&st=awqjeywk&raw=1" }, 
      { title:"Montagem Xogada", src:"https://www.dropbox.com/scl/fi/4zklj4s3f770vpm5pgw5r/MONTAGEM-XONADA-Sped-Up-SambalpuriStar.In.mp3?rlkey=geq33m77s364w4awdj4t8zgi5&st=bexf3q1l&raw=1" }, 
      { title:"Montagem Tomada", src:"https://www.dropbox.com/scl/fi/el5z0wrc6pqjhcjxcud71/Montagem-Tomada-Slowed-SambalpuriStar.In.mp3?rlkey=35mrax0rs2fq46tjbebxyqn0o&st=xtjw8zuv&raw=1" }, 
      { title:"Montagem Rugada", src:"https://www.dropbox.com/scl/fi/fzcod4y204m2ivnsnb6qa/Montagem-Rugada-Downringtone.com.mp3?rlkey=13xq882lsx5egufkz2qjcajqe&st=y1ckmddj&raw=1" }, 
      { title:"Papaoutai", src:"https://www.dropbox.com/scl/fi/9l5we3td2xn5idg03p5jw/Papaoutai_Afro_Soul.mp3?rlkey=hqatsih5u0xr5xvyh73gwsavd&st=3dspfulw&raw=1" }, 
      { title:"Airtel phonk", src:"https://www.dropbox.com/scl/fi/6p2jkdydqchmhz34dnt2t/AIRTEL_PHONK.mp3?rlkey=ichurm0lrqbmjkc3vb933ppgk&st=s5ez92n9&raw=1" }, 
      { title:"Luz Roja", src:"https://www.dropbox.com/scl/fi/prsixha5i1qjca0f8l7c8/Luz-Roja-Slowed.mp3?rlkey=c06zsyatjcnufaolqaxklstoq&st=ff40xchd&raw=1"}, 
      { title:"Montagem Alquimia", src:"https://www.dropbox.com/scl/fi/ra9bxs0sffns0w6xyn4a8/MONTAGEM-ALQUIMIA-SLOWED-h6itam-youtube.mp3?rlkey=b3104ft2hjndl744b6p9hlxey&st=eze86f7f&raw=1" }, 
      { title:"Matadora", src:"https://www.dropbox.com/scl/fi/4qj2dhqxcolyne7wa44ay/DJ_Asul_-_MATADORA_Slowed_-SkySound.cc.mp3?rlkey=v5yzru826oidg7if66twe5ryu&st=w06w9es4&raw=1" } 
    ]; 
    let queue = [], cur = 0, savedTime = 0, draggingProg = false; 
    try { 
      queue = JSON.parse(localStorage.getItem('cuc_queue')) || []; 
      cur = parseInt(localStorage.getItem('cuc_cur')) || 0; 
      savedTime = parseFloat(localStorage.getItem('cuc_t')) || 0; 
    } catch(e){} 
    
    const audio = document.getElementById('audio'), disc = document.getElementById('disc'), trackName = document.getElementById('trackName'), eqBars = document.getElementById('eqBars'), progTrack = document.getElementById('progressTrack'), progFill = document.getElementById('progressFill'), timeCur = document.getElementById('timeCur'), timeDur = document.getElementById('timeDur'), btnPlay = document.getElementById('btnPlay'), btnPrev = document.getElementById('btnPrev'), btnNext = document.getElementById('btnNext'), btnLoop = document.getElementById('btnLoop'), btnVol = document.getElementById('btnVol'), iconVol = document.getElementById('iconVol'), volTrack = document.getElementById('volTrack'), volFill = document.getElementById('volFill'), volKnob = document.getElementById('volKnob'), iconPlay = document.getElementById('iconPlay'), iconLoop = document.getElementById('iconLoop'), searchInp = document.getElementById('searchInput'), dropdown = document.getElementById('searchDropdown'), playlist = document.getElementById('playlist'), plCount = document.getElementById('plCount'); 
    
    const fmt = (s) => { if(!s||isNaN(s)) return '0:00'; const m=Math.floor(s/60), sc=Math.floor(s%60); return m+':'+(sc<10?'0':'')+sc; }; 
    const save = () => { try{ localStorage.setItem('cuc_queue', JSON.stringify(queue)); localStorage.setItem('cuc_cur', cur); }catch(e){} }; 
    
    const setPlayingUI = (p) => { 
      if(p){ 
        iconPlay.innerHTML='<rect x="6" y="4" width="4" height="16" rx="1"/><rect x="14" y="4" width="4" height="16" rx="1"/>'; disc.classList.add('spinning'); eqBars.querySelectorAll('.eq-bar').forEach(b=>b.classList.remove('paused')); 
      } else { 
        iconPlay.innerHTML='<polygon points="5 3 19 12 5 21 5 3"/>'; disc.classList.remove('spinning'); eqBars.querySelectorAll('.eq-bar').forEach(b=>b.classList.add('paused')); 
      } 
    }; 
    
    const setLoopUI = (o) => { 
      if(o){ btnLoop.classList.add('loop-on'); iconLoop.setAttribute('stroke','#fff'); } 
      else { btnLoop.classList.remove('loop-on'); iconLoop.setAttribute('stroke','#00f2fe'); } 
    }; 
    
    const setVolUI = () => { 
      const v = audio.muted?0:audio.volume; const pct=(v*100)+'%'; volFill.style.width=pct; volKnob.style.left=`calc(${pct} - 6px)`; 
      iconVol.innerHTML = (audio.muted||v===0)?'<polygon points="11 5 6 9 2 9 2 15 6 15 11 19 11 5"/><line x1="23" y1="9" x2="17" y2="15"/><line x1="17" y1="9" x2="23" y2="15"/>':'<polygon points="11 5 6 9 2 9 2 15 6 15 11 19 11 5"/><path d="M19.07 4.93a10 10 0 0 1 0 14.14"/>'; 
    }; 
    
    const syncProg = () => { 
      if(!audio.duration||draggingProg) return; const p=(audio.currentTime/audio.duration)*100; progFill.style.width=p+'%'; timeCur.textContent=fmt(audio.currentTime); timeDur.textContent=fmt(audio.duration); 
      try{ localStorage.setItem('cuc_t', audio.currentTime); }catch(e){} 
    }; 
    
    const loadTrack = (idx, auto) => { 
      if(!queue.length) return; cur=idx; audio.src=queue[cur].src; trackName.textContent=queue[cur].title; rP(); save(); audio.load(); 
      if(auto) audio.play().catch(()=>{}); 
      else { audio.onloadedmetadata=()=>{ if(savedTime>0&&savedTime<audio.duration) audio.currentTime=savedTime; savedTime=0; }; } 
    }; 
    
    const rP = () => { 
      plCount.textContent=queue.length; if(!queue.length){ playlist.innerHTML='<div class="music-playlist-empty"><span>🎵</span>No songs yet!</div>'; return; } 
      playlist.innerHTML=''; 
      queue.forEach((t,i)=>{ 
        const div=document.createElement('div'); div.className='music-playlist-item'+(i===cur?' active':''); 
        div.innerHTML=`<span class="music-pl-num">${String(i+1).padStart(2,'0')}</span><span class="music-pl-icon">${i===cur&&!audio.paused?'▶':'♪'}</span><span class="music-pl-name">${t.title}</span><span class="music-pl-remove">✕</span>`; 
        div.querySelector('.music-pl-name').onclick=()=>{savedTime=0; loadTrack(i,true);}; 
        div.querySelector('.music-pl-remove').onclick=(e)=>{ 
          e.stopPropagation(); queue.splice(i,1); 
          if(!queue.length){ audio.pause(); audio.src=''; cur=0; trackName.textContent='Choose a song'; setPlayingUI(false); } 
          else { if(i<cur) cur--; if(i===cur) loadTrack(cur%queue.length, !audio.paused); } rP(); save(); 
        }; 
        playlist.appendChild(div); 
      }); 
    }; 
    
    btnPlay.onclick=()=>{ if(!queue.length) return; audio.src===''?loadTrack(cur,true):audio.paused?audio.play():audio.pause(); }; 
    btnNext.onclick=()=>{ if(queue.length){ cur=(cur+1)%queue.length; savedTime=0; loadTrack(cur,true); } }; 
    btnPrev.onclick=()=>{ if(queue.length){ cur=audio.currentTime>3?cur:(cur-1+queue.length)%queue.length; savedTime=0; loadTrack(cur,true); } }; 
    btnLoop.onclick=()=>{ audio.loop=!audio.loop; setLoopUI(audio.loop); localStorage.setItem('cuc_loop', audio.loop); }; 
    
    audio.onended=()=>{ if(!audio.loop) btnNext.click(); }; 
    audio.ontimeupdate=syncProg; audio.onplay=()=>setPlayingUI(true); audio.onpause=()=>setPlayingUI(false); 
    
    const savedLoop = localStorage.getItem('cuc_loop')==='true'; audio.loop=savedLoop; setLoopUI(savedLoop); 
    const sV=localStorage.getItem('cuc_vol'); audio.volume=sV!==null?parseFloat(sV):0.7; audio.muted=localStorage.getItem('cuc_muted')==='true'; setVolUI(); 
    
    volTrack.onmousedown=(e)=>{ 
      const seek=(ev)=>{ const r=volTrack.getBoundingClientRect(); const v=Math.max(0,Math.min(1,(ev.clientX-r.left)/r.width)); audio.volume=v; audio.muted=false; setVolUI(); localStorage.setItem('cuc_vol',v); localStorage.setItem('cuc_muted',false); }; 
      seek(e); document.onmousemove=seek; document.onmouseup=()=>document.onmousemove=null; 
    }; 
    
    btnVol.onclick=()=>{ audio.muted=!audio.muted; localStorage.setItem('cuc_muted',audio.muted); setVolUI(); }; 
    progTrack.onmousedown=(e)=>{ 
      draggingProg=true; 
      const seek=(ev)=>{ if(!audio.duration) return; const r=progTrack.getBoundingClientRect(); const p=Math.max(0,Math.min(1,(ev.clientX-r.left)/r.width)); audio.currentTime=p*audio.duration; progFill.style.width=(p*100)+'%'; }; 
      seek(e); document.onmousemove=seek; document.onmouseup=()=>{ draggingProg=false; document.onmousemove=null; }; 
    }; 
    
    searchInp.onfocus=()=>{ 
      dropdown.innerHTML=''; 
      DB.forEach(s=>{ 
        const div=document.createElement('div'); div.className='music-search-item'; 
        div.innerHTML=`<span class="music-search-item-title">${s.title}</span><span class="music-search-badge add">+ Add</span>`; 
        div.onclick=()=>{ const empty=queue.length===0; queue.push(s); save(); rP(); if(empty) loadTrack(0,false); }; 
        dropdown.appendChild(div); 
      }); 
      dropdown.classList.add('open'); 
    }; 
    
    document.addEventListener('click', e=> { if(!searchInp.contains(e.target)&&!dropdown.contains(e.target)) dropdown.classList.remove('open'); }); 
    if(queue.length) loadTrack(cur, false); else rP(); 
  }

  // MODULE 12: PARTNER ALLIANCES 
  async function fetchAllianceData(){ 
    const CLUBS = ['supreme-elite-society', 'the-club-for-the-legends', 'virat2-fans']; 
    const containerBox = document.getElementById('alliancesList'); 
    if (!containerBox) return; 
    try { 
      const resolved = await Promise.all(CLUBS.map(s => fetch(`https://api.chess.com/pub/club/${s}`).then(r => r.ok?r.json():null).catch(()=>null))); 
      containerBox.innerHTML = resolved.map((club, i) => { 
        const slug = CLUBS[i], name = club?.name || humanizeSlug(slug), icon = club?.icon || 'https://www.chess.com/bundles/web/images/black_400.918e8b14.png'; 
        return `<a class="ally-card" href="https://www.chess.com/club/${slug}" target="_blank"><img class="ally-logo" src="${icon}" onerror="this.src='https://www.chess.com/bundles/web/images/black_400.918e8b14.png'"><div class="ally-info"><div class="ally-name">${name}</div><div class="ally-sub">👥 ${club?club.members_count.toLocaleString()+' Members':'Alliance'}</div></div><span class="ally-arr">›</span></a>`; 
      }).join(''); 
    } catch(e) { containerBox.innerHTML = '<div class="ally-loading-msg">⚠️ Failed to map coalitions.</div>'; } 
  }

  // CORE ENGINE BOOT INITIALIZATION 
  window.addEventListener("DOMContentLoaded", () => { 
    fetchClubMemberCount(); 
    loadNewestMembers(); 
    loadMatchesAndGauges(); 
    queryClosestMatch(); 
    loadPodiumAndMasters(true); 
    fetchDailyPuzzleData(); 
    initBirthdays(); 
    initMusicPlayer(); 
    fetchAllianceData();

    // Setup Navigation Event Tabs Subsystems 
    document.getElementById("matchesTabs").onclick = (e) => { 
      const btn = e.target.closest(".matches-tab"); if (!btn) return; 
      document.querySelectorAll(".matches-tab").forEach(t => t.classList.remove("active")); 
      btn.classList.add("active"); activeMatchTab = btn.dataset.tab; renderMatches(); 
    };

    document.getElementById("podiumTabsStrip").onclick = (e) => { 
      const btn = e.target.closest(".podium-tab-btn"); if (!btn) return; 
      document.querySelectorAll(".podium-tab-btn").forEach(t => t.classList.remove("active")); 
      btn.classList.add("active"); currentPodiumMode = btn.getAttribute("data-type"); loadPodiumAndMasters(false); 
    };

    // Global Sync Fallback Framework Intervals 
    setInterval(fetchClubMemberCount, 5 * 60 * 1000); 
    setInterval(loadNewestMembers, 3 * 60 * 1000); 
    setInterval(loadMatchesAndGauges, 3 * 60 * 1000); 
    setInterval(queryClosestMatch, 2 * 60 * 1000); 
    setInterval(() => loadPodiumAndMasters(true), 15 * 60 * 1000); 
    setInterval(fetchAllianceData, 10 * 60 * 1000); 
  }); 
})(); 
</script>
</body>
</html>
