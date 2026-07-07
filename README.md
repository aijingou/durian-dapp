---
permalink: /
---
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>双轨螺旋 · 榴莲链上生态园</title>
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <style>
        body {
            background: radial-gradient(circle at top, #062f19 0%, #020617 100%);
            -webkit-tap-highlight-color: transparent;
        }
    </style>
</head>
<body class="text-slate-100 min-h-screen flex flex-col justify-between font-sans selection:bg-green-500 selection:text-black">

    <header class="flex justify-between items-center px-4 py-3 border-b border-green-900/30 backdrop-blur-md sticky top-0 z-50 bg-slate-950/40">
        <div class="flex items-center gap-2">
            <span class="text-2xl animate-bounce">👑</span>
            <div>
                <h1 class="text-sm font-black tracking-wider text-green-400">榴莲生态园</h1>
                <p class="text-[9px] text-gray-500 font-mono">DURIAN ECO-CHAIN v1.0</p>
            </div>
        </div>
        <button id="connectBtn" onclick="toggleConnect()" class="bg-gradient-to-r from-green-600 to-emerald-500 hover:from-green-500 hover:to-emerald-400 text-[11px] px-4 py-1.5 rounded-full font-bold transition-all shadow-lg shadow-green-900/40 active:scale-95 text-slate-950">
            连接钱包
        </button>
    </header>

    <main class="flex-1 px-4 py-4 space-y-4 overflow-y-auto pb-24">
        
        <div class="bg-green-950/30 border border-green-900/40 rounded-lg px-3 py-1.5 text-[11px] text-green-400 flex items-center gap-2 overflow-hidden">
            <span class="font-bold">🔥 动态:</span>
            <marquee scrollamount="3" class="font-mono">区代 0x7a...9b 刚刚激活 5U 矿机，3U 管道分红已秒拨到位！</marquee>
        </div>

        <div class="bg-slate-900/90 border border-green-500/20 rounded-2xl p-4 shadow-xl backdrop-blur-md relative overflow-hidden">
            <div class="absolute -right-8 -top-8 w-24 h-24 bg-green-500/5 rounded-full blur-xl"></div>
            
            <div class="text-[10px] text-gray-400 mb-1 flex justify-between">
                <span>链上当前
