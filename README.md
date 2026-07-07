<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>双轨螺旋 · 榴莲链上生态园</title>
    <!-- 引入 Tailwind CSS 强力渲染引擎 -->
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <style>
        body {
            background: radial-gradient(circle at top, #062f19 0%, #020617 100%);
            -webkit-tap-highlight-color: transparent;
        }
    </style>
</head>
<body class="text-slate-100 min-h-screen flex flex-col justify-between font-sans selection:bg-green-500 selection:text-black">

    <!-- 顶部状态栏：Web3钱包连接区 -->
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

    <!-- 主体内容：九盘联控控制台 -->
    <main class="flex-1 px-4 py-4 space-y-4 overflow-y-auto pb-24">
        
        <!-- 跑马灯滚动公告 -->
        <div class="bg-green-950/30 border border-green-900/40 rounded-lg px-3 py-1.5 text-[11px] text-green-400 flex items-center gap-2 overflow-hidden">
            <span class="font-bold">🔥 动态:</span>
            <marquee scrollamount="3" class="font-mono">区代 0x7a...9b 刚刚激活 5U 矿机，3U 管道分红已秒拨到位！</marquee>
        </div>

        <!-- 邀请人信息与挖矿状态看板 -->
        <div class="bg-slate-900/90 border border-green-500/20 rounded-2xl p-4 shadow-xl backdrop-blur-md relative overflow-hidden">
            <div class="absolute -right-8 -top-8 w-24 h-24 bg-green-500/5 rounded-full blur-xl"></div>
            
            <div class="text-[10px] text-gray-400 mb-1 flex justify-between">
                <span>链上当前推荐人 (20代图网络)</span>
                <span class="text-green-400 font-bold">BSC 链已锁定</span>
            </div>
            <div class="text-xs text-green-300 font-mono bg-black/60 p-2 rounded-xl border border-slate-800 truncate mb-4">
                0x55d398326f99059fF775485246999027B3197955 (示例邀请码)
            </div>
            
            <!-- 双轨齿轮资产实时跳动显示 -->
            <div class="grid grid-cols-2 gap-3 text-center mb-4">
                <div class="bg-slate-950/50 p-3 rounded-xl border border-slate-800/80">
                    <p class="text-[10px] text-gray-400">待领 DLF 积分 (模式轨)</p>
                    <p class="text-lg font-black text-yellow-500 mt-0.5 font-mono">142.50 <span class="text-[9px] text-gray-500">个</span></p>
                </div>
                <div class="bg-slate-950/50 p-3 rounded-xl border border-slate-800/80">
                    <p class="text-[10px] text-gray-400">待领 DLC 榴莲币 (实体轨)</p>
                    <p class="text-lg font-black text-emerald-400 mt-0.5 font-mono">12.00 <span class="text-[9px] text-gray-500">枚</span></p>
                </div>
            </div>

            <!-- 核心动作：激活矿机 -->
            <button id="activateBtn" onclick="triggerActivate()" class="w-full bg-gradient-to-r from-yellow-500 via-amber-500 to-green-600 hover:brightness-110 text-slate-950 font-black py-3.5 rounded-xl shadow-lg transition-all text-xs tracking-widest active:scale-[0.98] shadow-yellow-900/20">
                ⚡ 充值 5 USDT 激活榴莲云矿机
            </button>
        </div>

        <!-- 7人拼树众筹联动板块 -->
        <div class="bg-slate-900/90 border border-yellow-500/20 rounded-2xl p-4 shadow-xl backdrop-blur-md relative overflow-hidden">
            <div class="absolute top-0 right-0 bg-gradient-to-l from-yellow-500 to-amber-500 text-slate-950 text-[9px] font-black px-3 py-1 rounded-bl-xl shadow-md">
                10% 实体永久股份
            </div>
            
            <h3 class="text-xs font-black text-yellow-400 mb-1 flex items-center gap-1">
                🌳 7人组拼 / 独享有产权榴莲树
            </h3>
            <p class="text-[11px] text-gray-400 mb-4 leading-relaxed">
                每人出资 150U（满7人成团）。占整棵树10%收益权，尊享线下果园“送货包吃”与线上 DLF 积分加倍裂变。
            </p>
            
            <!-- 众筹进度条 -->
            <div class="w-full bg-slate-950 rounded-full h-2.5 mb-2 border border-slate-800 overflow-hidden">
                <div class="bg-gradient-to-r from-yellow-500 via-amber-400 to-emerald-400 h-full rounded-full" style="width: 57.1%"></div>
            </div>
            <div class="flex justify-between text-[10px] text-gray-400 mb-4 font-mono">
                <span>当前成团进度: <span class="text-yellow-400 font-bold">4</span> / 7 人</span>
                <span>还差: <span class="text-red-400 font-bold">3</span> 人</span>
            </div>

            <button onclick="triggerJoinGroup()" class="w-full bg-slate-950/80 hover:bg-slate-950 border border-yellow-500/30 text-yellow-400 font-bold py-2.5 rounded-xl text-xs transition-all active:scale-[0.98]">
                🤝 立即参与该树组拼 (150 USDT)
            </button>
        </div>

        <!-- 实体造血数据看板（加强信心） -->
        <div class="bg-slate-900/40 border border-slate-800 rounded-xl p-3 grid grid-cols-3 gap-2 text-center text-[10px]">
            <div>
                <p class="text-gray-500">自有果园规模</p>
                <p class="text-slate-300 font-bold font-mono mt-0.5">1,000 亩</p>
            </div>
            <div class="border-x border-slate-800">
                <p class="text-gray-500">全网区代节点</p>
                <p class="text-slate-300 font-bold font-mono mt-0.5">1,000 个</p>
            </div>
            <div>
                <p class="text-gray-500">昨日实体回购</p>
                <p class="text-emerald-400 font-bold font-mono mt-0.5">500,000 元</p>
            </div>
        </div>

    </main>

    <!-- 移动端底部黄金 4 键导航 -->
    <footer class="fixed bottom-0 left-0 right-0 grid grid-cols-4 bg-slate-950/95 border-t border-green-900/30 py-3 text-center text-[10px] text-gray-500 rounded-t-2xl backdrop-blur-lg shadow-2xl z-50">
        <div class="text-green-400 font-bold">
            <span class="text-lg block mb-0.5">🌱</span>矿机双挖
        </div>
        <div onclick="alert('进入拼树板块')">
            <span class="text-lg block mb-0.5">🛒</span>拼树众筹
        </div>
        <div onclick="alert('20代团队管理（开发中）')">
            <span class="text-lg block mb-0.5">👥</span>20代团队
        </div>
        <div onclick="alert('区代订单与一手货源仓')">
            <span class="text-lg block mb-0.5">📦</span>区代货仓
        </div>
    </footer>

    <!-- 简单的核心 H5 交互仿真脚本 -->
    <script>
        let isConnected = false;

        function toggleConnect() {
            const btn = document.getElementById('connectBtn');
            if(!isConnected) {
                btn.innerHTML = "0x55d3...7955";
                btn.className = "bg-slate-800 border border-green-500/40 text-[11px] px-4 py-1.5 rounded-full font-mono transition-all text-green-400";
                isConnected = true;
                console.log("Web3 钱包模拟连接成功");
            } else {
                btn.innerHTML = "连接钱包";
                btn.className = "bg-gradient-to-r from-green-600 to-emerald-500 text-[11px] px-4 py-1.5 rounded-full font-bold text-slate-950";
                isConnected = false;
            }
        }

        function triggerActivate() {
            if(!isConnected) {
                alert("👉 请先点击右上角【连接钱包】模拟拉起加密钱包授权");
                return;
            }
            const actBtn = document.getElementById('activateBtn');
            actBtn.innerHTML = "🔄 正在拉起 BSC 链上清算合约...";
            actBtn.disabled = true;

            setTimeout(() => {
                alert("🎉 模拟清算成功！\n\n1. 3U 已通过链上秒拨给您所属线的地推代理商地址\n2. 2U 已自动锁入底池总管\n3. 您的24小时双挖算力已激活！");
                actBtn.innerHTML = "⚡ 5U矿机已激活 (双挖进行中)";
                actBtn.className = "w-full bg-slate-800 border border-green-500/30 text-green-400 font-bold py-3.5 rounded-xl text-xs tracking-widest cursor-not-allowed";
            }, 1500);
        }

        function triggerJoinGroup() {
            if(!isConnected) {
                alert("👉 请先点击右上角【连接钱包】");
                return;
            }
            let confirmPay = confirm("是否确认调用智能合约支付 150 USDT 参与本树组拼？");
            if(confirmPay) {
                alert("🎉 150U 链上拼树成功！成团人数已变为 5/7，已为您生成该树 10% 股份对应的区块链 NFT 通证凭证。");
            }
        }
    </script>
</body>
</html>
