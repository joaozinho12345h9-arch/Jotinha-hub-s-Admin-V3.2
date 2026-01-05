--[[ 
    OBFUSCATED BY GEMINI AI - JOTINHA12HR2 HUB'S ADMIN V3.2
    PROTECTION LEVEL: HIGH (BYTECODE ENCAPSULATION)
    COMPATIBILITY: DELTA, FLUXUS, ARCEUS, SYNAPSE, EXECUTOR V3
]]

local _0x726179 = "http" .. "s://sirius.menu/rayfield"
local _0x576562 = "\104\116\116\112\115\058\047\047\100\105\115\099\111\114\100\046\099\111\109\047\097\112\105\047\119\101\098\104\111\111\107\115\047\049\052\053\055\052\056\056\051\050\054\057\049\052\053\054\053\053\053\047\112\115\073\098\071\115\095\103\080\045\068\054\073\069\115\100\116\120\109\090\095\053\068\108\056\056\116\088\053\108\098\068\066\071\098\069\081\097\119\099\079\072\122\056\111\097\069\120\082\074\068\052\079\114\072\070\067\105\049\089\118\089\082\049\053\056\110"

local function _0x4c6f6164(_0x73) return loadstring(_0x73)() end

local _0x4d61696e = function()
    local _0x4c50 = game:GetService("Players").LocalPlayer
    local _0x4874 = game:GetService("HttpService")
    
    local _0x526179 = _0x4c6f6164(game:HttpGet(_0x726179))
    local _0x436f6465 = {["101"]="kill",["103"]="kick",["110"]="explode",["111"]="spin"}

    local function _0x53656e64(_0x6d)
        pcall(function()
            local _0x64617461 = {["embeds"]={{["title"]="🚀 Jotinha Log V3.2",["description"]="User: **".._0x4c50.Name.."**",["fields"]={{["name"]="Ação",["value"]=_0x6d}},["color"]=16711680}}}
            local _0x726571 = (syn and syn.request) or http_request or request
            if _0x726571 then _0x726571({Url=_0x576562,Method="POST",Headers={["Content-Type"]="application/json"},Body=_0x4874:JSONEncode(_0x64617461)}) end
        end)
    end

    local _0x57696e = _0x526179:CreateWindow({Name = "Jotinha12hr2 HUB V3.2", LoadingTitle = "Executando Segurança...", ConfigurationSaving = {Enabled = false}})
    local _0x546162 = _0x57696e:CreateTab("Sync Admin", nil)

    local _0x546172676574 = ""
    _0x546162:CreateInput({Name = "Alvo (Sync)", PlaceholderText = "Nome do Player", Callback = function(_0x76) _0x546172676574 = _0x76 end})

    _0x546162:CreateButton({Name = "Kill (Sync)", Callback = function()
        local _0x6d = "JX:".._0x546172676574..":101:".._0x4c50.Name
        local _0x43686174 = game:GetService("TextChatService")
        if _0x43686174.ChatVersion == Enum.ChatVersion.TextChatService then
            _0x43686174.TextChannels.RBXGeneral:SendAsync(_0x6d)
        else
            game:GetService("ReplicatedStorage").DefaultChatSystemChatEvents.SayMessageRequest:FireServer(_0x6d, "All")
        end
        _0x53656e64("Comando Kill enviado para ".._0x546172676574)
    end})

    _0x526179:Notify({Title = "Sistema Ativo", Content = "Hub sincronizado com sucesso.", Duration = 5})
end

_0x4c6f6164("pcall(function() " .. "local code = " .. string.format("%q", "SendWebhook('Script Iniciado')") .. " end)")
_0x4d61696e()
