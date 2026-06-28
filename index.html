<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Universal Quant Scanner - LLM Engine</title>
    <style>
        :root { --primary: #00f0ff; --secondary: #7000ff; --bg: #020617; --glass: rgba(15, 23, 42, 0.85); --border: rgba(0, 240, 255, 0.3); --danger: #ef4444; --text: #e2e8f0; }
        * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Consolas', 'Monaco', 'PingFang SC', sans-serif; }
        body { background-color: var(--bg); color: var(--text); min-height: 100vh; overflow-x: hidden; display: flex; justify-content: center; padding: 20px; }
        .cyber-bg { position: fixed; top: 0; left: 0; width: 100%; height: 100%; z-index: -1; background: radial-gradient(circle at 50% 50%, #1e1b4b 0%, #020617 100%); }
        .cyber-bg::before { content: ""; position: absolute; width: 200%; height: 200%; top: -50%; left: -50%; background-image: linear-gradient(rgba(0, 240, 255, 0.05) 1px, transparent 1px), linear-gradient(90deg, rgba(0, 240, 255, 0.05) 1px, transparent 1px); background-size: 40px 40px; transform: perspective(500px) rotateX(60deg); animation: grid-move 10s linear infinite; }
        @keyframes grid-move { from { background-position: 0 0; } to { background-position: 0 40px; } }
        .app-container { display: flex; width: 100%; max-width: 1400px; gap: 20px; align-items: flex-start; }
        .sidebar { width: 280px; flex-shrink: 0; background: var(--glass); backdrop-filter: blur(15px); border: 1px solid var(--border); border-radius: 16px; padding: 20px; display: flex; flex-direction: column; height: calc(100vh - 40px); position: sticky; top: 20px; box-shadow: 0 0 30px rgba(0, 0, 0, 0.5); }
        .btn-new-chat { width: 100%; padding: 12px; background: rgba(0, 240, 255, 0.1); border: 1px solid var(--primary); border-radius: 8px; color: var(--primary); font-size: 15px; font-weight: bold; cursor: pointer; transition: 0.3s; margin-bottom: 20px; display: flex; align-items: center; justify-content: center; gap: 8px; }
        .btn-new-chat:hover { background: var(--primary); color: #000; box-shadow: 0 0 15px rgba(0, 240, 255, 0.4); }
        .session-list { flex: 1; overflow-y: auto; display: flex; flex-direction: column; gap: 10px; padding-right: 5px; }
        ::-webkit-scrollbar { width: 6px; } ::-webkit-scrollbar-track { background: rgba(255, 255, 255, 0.05); border-radius: 10px; } ::-webkit-scrollbar-thumb { background: rgba(0, 240, 255, 0.3); border-radius: 10px; } ::-webkit-scrollbar-thumb:hover { background: var(--primary); }
        .session-item { background: rgba(0, 0, 0, 0.4); border: 1px solid rgba(255,255,255,0.1); border-radius: 8px; padding: 12px; cursor: pointer; display: flex; justify-content: space-between; align-items: center; transition: 0.2s; }
        .session-item:hover { border-color: var(--primary); background: rgba(0, 240, 255, 0.05); }
        .session-item.active { border-color: var(--primary); background: rgba(0, 240, 255, 0.1); border-left: 4px solid var(--primary); }
        .session-title { font-size: 13px; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; flex: 1; color: #cbd5e1; }
        .session-item.active .session-title { color: #fff; font-weight: bold; }
        .btn-del-session { background: transparent; border: none; color: #64748b; cursor: pointer; font-size: 16px; padding: 4px; border-radius: 4px; transition: 0.2s; display: flex; align-items: center; justify-content: center; }
        .btn-del-session:hover { color: var(--danger); background: rgba(239, 68, 68, 0.1); }
        .main-content { flex: 1; display: flex; flex-direction: column; min-width: 0; gap: 20px; }
        .container, .box-container { width: 100%; background: var(--glass); backdrop-filter: blur(15px); border: 1px solid var(--border); border-radius: 16px; box-shadow: 0 0 30px rgba(0, 0, 0, 0.5); }
        .container { padding: 30px; }
        h1 { font-size: 1.5rem; color: var(--primary); text-align: center; margin-bottom: 20px; letter-spacing: 2px; text-shadow: 0 0 10px var(--primary); }
        .config-group { margin-bottom: 15px; } .config-group label { display: flex; justify-content: space-between; font-size: 12px; color: #94a3b8; margin-bottom: 6px; text-transform: uppercase; }
        .input-row { display: flex; gap: 10px; } .config-group input { flex: 1; background: rgba(0, 0, 0, 0.5); border: 1px solid var(--border); border-radius: 6px; padding: 10px 15px; color: #fff; font-size: 14px; outline: none; transition: 0.3s; }
        .config-group input:focus { border-color: var(--primary); box-shadow: 0 0 10px rgba(0, 240, 255, 0.2); }
        .divider { height: 1px; background: linear-gradient(90deg, transparent, var(--border), transparent); margin: 20px 0; }
        .btn-delete { background: rgba(239, 68, 68, 0.1); border: 1px solid var(--danger); border-radius: 6px; color: var(--danger); width: 42px; display: flex; align-items: center; justify-content: center; cursor: pointer; transition: 0.2s; font-size: 16px; }
        .btn-delete:hover { background: var(--danger); color: #fff; }
        .btn-add { width: 100%; padding: 10px; background: rgba(0, 240, 255, 0.05); border: 1px dashed var(--primary); border-radius: 6px; color: var(--primary); font-size: 14px; cursor: pointer; transition: 0.3s; margin-bottom: 10px; }
        .btn-add:hover { background: rgba(0, 240, 255, 0.15); }
        .box-container { background: rgba(0,0,0,0.6); display: flex; flex-direction: column; overflow: hidden; }
        .box-header { background: rgba(255, 255, 255, 0.05); padding: 10px 15px; display: flex; justify-content: space-between; align-items: center; border-bottom: 1px solid var(--border); }
        .box-title { font-size: 13px; color: var(--primary); font-weight: bold; } .query-title { color: #f59e0b; }
        .controls { display: flex; gap: 8px; } .control-btn { width: 26px; height: 26px; border-radius: 4px; border: 1px solid rgba(255,255,255,0.1); background: rgba(255,255,255,0.05); color: #fff; cursor: pointer; display: flex; align-items: center; justify-content: center; font-size: 14px; transition: 0.2s; }
        .control-btn:hover { background: rgba(255,255,255,0.2); }
        textarea { width: 100%; height: 100px; background: transparent; border: none; color: #fff; padding: 15px; font-size: 15px; line-height: 1.6; resize: none; outline: none; }
        #output-area { height: 450px; padding: 20px; overflow-y: auto; font-size: 15px; line-height: 1.7; background: rgba(0, 0, 0, 0.7); }
        .msg-user { color: #f59e0b; font-weight: bold; margin-top: 15px; margin-bottom: 10px; border-left: 3px solid #f59e0b; padding-left: 10px; }
        .msg-ai { color: #ffffff; text-shadow: 0 0 8px rgba(0, 240, 255, 0.4); background: rgba(15, 23, 42, 0.7); padding: 16px; border-radius: 8px; border-left: 3px solid var(--primary); margin-bottom: 20px; white-space: pre-wrap; }
        .msg-error { color: #ef4444; font-weight: bold; margin-bottom: 20px; background: rgba(239, 68, 68, 0.1); padding: 10px; border-radius: 6px; }
        .btn-run { width: 100%; padding: 15px; background: linear-gradient(90deg, var(--secondary), var(--primary)); border: none; border-radius: 10px; color: #fff; font-size: 16px; font-weight: bold; cursor: pointer; letter-spacing: 2px; transition: 0.3s; }
        .btn-run:hover { filter: brightness(1.2); box-shadow: 0 0 20px var(--primary); }
        .btn-log-toggle { position: fixed; bottom: 20px; right: 20px; z-index: 1000; padding: 12px 20px; background: rgba(15, 23, 42, 0.9); border: 1px solid var(--primary); border-radius: 8px; color: var(--primary); font-weight: bold; cursor: pointer; transition: 0.3s; box-shadow: 0 0 15px rgba(0, 240, 255, 0.2); }
        .btn-log-toggle:hover { background: var(--primary); color: #000; box-shadow: 0 0 25px rgba(0, 240, 255, 0.6); }
        .log-panel { position: fixed; bottom: 70px; right: 20px; width: 450px; height: 350px; background: rgba(5, 9, 20, 0.95); border: 1px solid var(--border); border-radius: 12px; z-index: 999; display: flex; flex-direction: column; transform: translateY(120%); transition: transform 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275); box-shadow: 0 10px 30px rgba(0,0,0,0.8); visibility: hidden; }
        .log-panel.show { transform: translateY(0); visibility: visible; }
        .log-panel-header { padding: 10px 15px; border-bottom: 1px solid var(--border); display: flex; justify-content: space-between; align-items: center; color: var(--primary); font-size: 13px; font-weight: bold; }
        .log-panel-content { flex: 1; overflow-y: auto; padding: 15px; font-family: monospace; font-size: 12px; color: #10b981; line-height: 1.5; }
        .log-entry { margin-bottom: 6px; border-bottom: 1px dashed rgba(16, 185, 129, 0.2); padding-bottom: 4px; } .log-entry.error { color: var(--danger); } .log-entry.warn { color: #f59e0b; }
        .box-container.fullscreen { position: fixed; top: 0; left: 0; width: 100vw; height: 100vh; max-width: 100vw; z-index: 9999; border-radius: 0; margin: 0; } .box-container.fullscreen #output-area { height: calc(100vh - 45px); font-size: 18px; }
        @media (max-width: 900px) { .app-container { flex-direction: column; } .sidebar { width: 100%; height: 250px; position: relative; top: 0; } }
    </style>
</head>
<body>
    <div class="cyber-bg"></div>
    <div class="app-container">
        <div class="sidebar">
            <button class="btn-new-chat" onclick="createNewSession()"><span>+</span> 新建策略对话</button>
            <div class="session-list" id="session-list"></div>
        </div>
        <div class="main-content">
            <div class="container">
                <h1>Universal Quant Scanner</h1>
                <div class="config-group">
                    <label>✦ 主模型请求地址 (API Endpoint)</label>
                    <input type="text" id="api-main-url" placeholder="如: https://open.bigmodel.cn/api/paas/v4/chat/completions" oninput="saveConfigToLocal()">
                </div>
                <div class="input-row">
                    <div class="config-group" style="flex: 1;">
                        <label>✦ 模型名称 (Model ID)</label>
                        <input type="text" id="api-main-model" placeholder="如: glm-4" oninput="saveConfigToLocal()">
                    </div>
                    <div class="config-group" style="flex: 2;">
                        <label>✦ API 密钥 (Bearer Token)</label>
                        <input type="password" id="api-main-key" placeholder="在此填入你的 API Key" oninput="saveConfigToLocal()">
                    </div>
                </div>
                <div class="divider"></div>
                <div class="config-group">
                    <label>✦ 数据源 / 参考节点 1</label>
                    <input type="text" class="ref-api-input" placeholder="填入通用 API 或以 http 开头的网址...">
                </div>
                <div class="config-group">
                    <label>✦ 数据源 / 参考节点 2</label>
                    <input type="text" class="ref-api-input" placeholder="填入通用 API 或以 http 开头的网址...">
                </div>
                <div id="dynamic-nodes-wrapper"></div>
                <button class="btn-add" onclick="addNode()"><span>+</span> 增加更多参考节点</button>
            </div>
            <div class="box-container" id="queryContainer">
                <div class="box-header">
                    <span class="box-title query-title">INPUT_QUERY (输入筛选指令)</span>
                    <div class="controls">
                        <button class="control-btn" onclick="toggleFullscreen('queryContainer')" title="全屏">⛶</button>
                        <button class="control-btn" onclick="clearBox('queryArea')" title="清空">✕</button>
                    </div>
                </div>
                <textarea id="queryArea" placeholder="输入量化筛选条件..."></textarea>
            </div>
            <button class="btn-run" onclick="executeCommand()">执行扫描策略 / RUN SCANNER</button>
            <div class="box-container" id="resContainer">
                <div class="box-header">
                    <span class="box-title">FINAL_OUTPUT (分析报告)</span>
                    <div class="controls">
                        <button class="control-btn" onclick="toggleFullscreen('resContainer')" title="全屏">⛶</button>
                    </div>
                </div>
                <div id="output-area"></div>
            </div>
        </div>
    </div>
    <button class="btn-log-toggle" onclick="toggleLog()">[ TERMINAL LOGS ]</button>
    <div class="log-panel" id="logPanel">
        <div class="log-panel-header">
            <span>SYSTEM EXECUTION LOG</span>
            <button class="control-btn btn-close" onclick="toggleLog()">✕</button>
        </div>
        <div class="log-panel-content" id="logContent">
            <div class="log-entry">System ready. Strict LLM Engine mode activated.</div>
        </div>
    </div>

    <script>
        const outputArea = document.getElementById('output-area');
        const sessionListEl = document.getElementById('session-list');
        const logContent = document.getElementById('logContent');
        const logPanel = document.getElementById('logPanel');
        
        let sessions = JSON.parse(localStorage.getItem('geek_sessions')) || {};
        let currentSessionId = null;
        let chatHistory = []; 

        window.onload = () => {
            document.getElementById('api-main-url').value = localStorage.getItem('geek_api_url') || '';
            document.getElementById('api-main-model').value = localStorage.getItem('geek_api_model') || '';
            document.getElementById('api-main-key').value = localStorage.getItem('geek_api_key') || '';
            renderSidebar();
            const sessionIds = Object.keys(sessions);
            if (sessionIds.length > 0) { loadSession(sessionIds[sessionIds.length - 1]); } 
            else { createNewSession(); }
        };

        function saveConfigToLocal() {
            localStorage.setItem('geek_api_url', document.getElementById('api-main-url').value.trim());
            localStorage.setItem('geek_api_model', document.getElementById('api-main-model').value.trim());
            localStorage.setItem('geek_api_key', document.getElementById('api-main-key').value.trim());
        }

        function toggleLog() { logPanel.classList.toggle('show'); }
        function appendSysLog(text, type = 'info') {
            const entry = document.createElement('div');
            entry.className = `log-entry ${type}`;
            const time = new Date().toISOString();
            entry.innerText = `[${time}] > [System] ${text}`;
            logContent.appendChild(entry);
            logContent.scrollTop = logContent.scrollHeight;
        }

        function renderSidebar() {
            sessionListEl.innerHTML = '';
            const sessionIds = Object.keys(sessions).reverse(); 
            sessionIds.forEach(id => {
                const sessionData = sessions[id];
                const item = document.createElement('div');
                item.className = `session-item ${id === currentSessionId ? 'active' : ''}`;
                item.onclick = () => loadSession(id);
                item.innerHTML = `<div class="session-title" title="${sessionData.title}">${sessionData.title}</div><button class="btn-del-session" onclick="deleteSession(event, '${id}')" title="删除">✕</button>`;
                sessionListEl.appendChild(item);
            });
        }

        function createNewSession() {
            currentSessionId = 'session_' + Date.now(); chatHistory = [];
            sessions[currentSessionId] = { title: "新对话", history: [] };
            saveToLocal(); renderSidebar(); outputArea.innerHTML = ''; document.getElementById('queryArea').value = '';
        }

        function loadSession(id) {
            currentSessionId = id; chatHistory = sessions[id].history || []; renderSidebar(); outputArea.innerHTML = '';
            chatHistory.forEach(msg => {
                if (msg.role === 'user') {
                    let cleanContent = msg.content;
                    if(cleanContent.includes('【Quant Scanner 指令】')) {
                        cleanContent = cleanContent.split('用户动态条件：\n')[1].split('\n\n【辅助节点获取的数据】')[0];
                    }
                    outputArea.innerHTML += `<div class="msg-user">用户提问: ${cleanContent}</div>`;
                } else if (msg.role === 'assistant') {
                    outputArea.innerHTML += `<div class="msg-ai">${msg.content}</div>`;
                }
            });
            outputArea.scrollTop = outputArea.scrollHeight;
        }

        function deleteSession(event, id) {
            event.stopPropagation(); 
            if (confirm("确定要永久删除这条对话记录吗？")) {
                delete sessions[id]; saveToLocal();
                if (id === currentSessionId) {
                    const remainingIds = Object.keys(sessions);
                    if (remainingIds.length > 0) { loadSession(remainingIds[remainingIds.length - 1]); } else { createNewSession(); }
                } else { renderSidebar(); }
            }
        }

        function saveToLocal() { localStorage.setItem('geek_sessions', JSON.stringify(sessions)); }

        function addNode() {
            const wrapper = document.getElementById('dynamic-nodes-wrapper');
            const newGroup = document.createElement('div');
            newGroup.className = 'config-group dynamic-node';
            newGroup.innerHTML = `<label class="dynamic-label">✦ 参考节点</label><div class="input-row"><input type="text" class="ref-api-input" placeholder="填入通用 API 或网址..."><button class="btn-delete" onclick="removeNode(this)">✕</button></div>`;
            wrapper.appendChild(newGroup); updateNodeLabels(); 
        }

        function removeNode(btnElement) { btnElement.closest('.dynamic-node').remove(); updateNodeLabels(); }
        function updateNodeLabels() { document.querySelectorAll('.dynamic-node .dynamic-label').forEach((label, index) => { label.innerText = `✦ 参考节点 ${index + 3}`; }); }

        function clearBox(areaId) { document.getElementById(areaId).value = ""; }
        function toggleFullscreen(containerId) {
            const container = document.getElementById(containerId); container.classList.toggle('fullscreen');
            document.body.style.overflow = container.classList.contains('fullscreen') ? 'hidden' : 'auto';
        }

        // ==========================================================
        // 核心进化：纯粹的 Raw Data -> LLM Inference 模型
        // ==========================================================
        async function executeCommand() {
            const queryInput = document.getElementById('queryArea');
            const query = queryInput.value.trim();
            const apiUrl = document.getElementById('api-main-url').value.trim();
            const apiModel = document.getElementById('api-main-model').value.trim();
            const apiKey = document.getElementById('api-main-key').value.trim();

            if (!query) { alert("请输入筛选指令！"); return; }
            if (!apiUrl || !apiModel || !apiKey) { alert("主模型的配置缺一不可！"); return; }

            saveConfigToLocal();
            if (chatHistory.length === 0 || sessions[currentSessionId].title === "新对话") {
                sessions[currentSessionId].title = query.substring(0, 15) + (query.length > 15 ? '...' : '');
            }

            outputArea.innerHTML += `<div class="msg-user">用户提问: ${query}</div>`;
            outputArea.scrollTop = outputArea.scrollHeight;
            queryInput.value = ""; 

            // 生成请求时间戳，禁用缓存
            const runTimestamp = new Date().toISOString();
            const cacheBuster = `_t=${Date.now()}`;
            
            appendSysLog(`=== 真实抓取流程开启 (所有网页端沙盒限制已移除) ===`);
            appendSysLog(`执行时间戳: ${runTimestamp}`);

            try {
                let combinedRawData = "";
                const allNodes = document.querySelectorAll('.ref-api-input'); 
                let dataSourceMeta = "未配置有效节点网址";
                
                // 1. 暴力抓取所有节点数据 (API Scan)
                for (let i = 0; i < allNodes.length; i++) {
                    const nodeValue = allNodes[i].value.trim();
                    if (nodeValue) {
                        if (nodeValue.startsWith('http://') || nodeValue.startsWith('https://')) {
                            // 记录第一个有效的数据源来源
                            if (dataSourceMeta === "未配置有效节点网址") {
                                dataSourceMeta = nodeValue.split('?')[0]; 
                            }
                            
                            const fetchUrl = nodeValue.includes('?') ? `${nodeValue}&${cacheBuster}` : `${nodeValue}?${cacheBuster}`;
                            appendSysLog(`正在尝试真实抓取节点 ${i + 1} 数据... (Cache Disabled)`);
                            
                            try {
                                const res = await fetch(fetchUrl, { cache: 'no-store' });
                                if (res.ok) {
                                    const textData = await res.text();
                                    // 为防止撑爆大模型 token 上限，保留截断逻辑但放宽上限至 30000 字符
                                    const truncatedData = textData.length > 30000 ? textData.substring(0, 30000) + '\n...[因数据量过大，为保证模型稳定已截断]' : textData;
                                    combinedRawData += `【节点 ${i + 1} 来源网址: ${dataSourceMeta}】:\n${truncatedData}\n\n`;
                                    appendSysLog(`节点 ${i + 1} 抓取成功。`);
                                } else {
                                    appendSysLog(`节点 ${i + 1} 抓取失败 (Status: ${res.status})`, 'warn');
                                    combinedRawData += `【节点 ${i + 1} 抓取失败，HTTP状态码: ${res.status}】\n\n`;
                                }
                            } catch (e) {
                                appendSysLog(`节点 ${i + 1} 网络异常: ${e.message}`, 'error');
                            }
                        } else {
                            // 如果填入的是纯文本，作为补充信息
                            combinedRawData += `【节点 ${i + 1} 文本补充信息】: ${nodeValue}\n\n`;
                        }
                    }
                }

                // 2. 将 Raw Data 丢给大模型，让大模型自行推理 (AI Summarize)
                appendSysLog(`所有节点数据抓取完毕。正在将原生数据交由 AI 大模型进行独立计算与推理...`);

                const finalPrompt = `【Quant Scanner 指令】：
您是专业的量化分析引擎。前端系统已经为你抓取了底层 API 提供的一手原生数据流。现在需要你接管运算大脑。

用户动态条件：
${query}

【辅助节点获取的数据】（Raw Data）：
${combinedRawData || "未抓取到有效数据"}

【输出要求（强制）】：
1. 你的回答必须在最开头，强制按照此格式打印元数据（不要加粗，直接输出）：
   数据时间: ${runTimestamp} UTC
   行情来源: ${dataSourceMeta}
   扫描股票数量: [请根据你处理的实际股票数量填写，或者填写 '全市场扫描']

2. 仔细阅读辅助数据。结合你自身庞大的内置金融知识库、实时搜索能力和逻辑推演能力，独立完成用户要求的量化筛选（如过滤市值、排除ADR/Meme/Mag7、计算涨跌幅等）。
3. 绝对不要列出或解释被排除的股票及其原因。直接给出最终符合条件的股票清单及催化剂分析。
4. 如果抓取的数据不足或残缺，你必须突破数据的局限，利用你的模型内置知识强制推演并补全结果，绝对不允许回答“无法完成任务”。`;

                chatHistory.push({ role: "user", content: finalPrompt });

                const response = await fetch(apiUrl, {
                    method: "POST",
                    headers: {
                        "Content-Type": "application/json",
                        "Authorization": `Bearer ${apiKey}`
                    },
                    body: JSON.stringify({
                        model: apiModel,
                        messages: chatHistory
                    })
                });

                if (!response.ok) {
                    const errText = await response.text();
                    throw new Error(`AI 服务器拒绝响应: ${response.status} \n${errText}`);
                }

                const resultJSON = await response.json();
                let aiAnswer = resultJSON.choices[0].message.content;

                chatHistory.push({ role: "assistant", content: aiAnswer });
                sessions[currentSessionId].history = chatHistory;
                saveToLocal(); renderSidebar(); 

                outputArea.innerHTML += `<div class="msg-ai">${aiAnswer}</div>`;
                outputArea.scrollTop = outputArea.scrollHeight;
                appendSysLog("=== Workflow Completed Successfully ===");

            } catch (error) {
                appendSysLog(`Pipeline crashed: ${error.message}`, 'error');
                outputArea.innerHTML += `<div class="msg-error">[系统中止] ${error.message}</div>`;
                outputArea.scrollTop = outputArea.scrollHeight;
                chatHistory.pop(); 
            }
        }
    </script>
</body>
</html>
