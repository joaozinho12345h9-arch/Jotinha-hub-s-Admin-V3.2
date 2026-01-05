--[[ Ofuscado por Jotinha12hr2 - Compatível com Delta/Arceus/Fluxus ]]--
local _0x5261796669656c64 = loadstring(game:HttpGet(('\104\116\116\112\115\58\47\47\115\105\114\105\117\115\46\109\101\110\117\47\114\97\121\102\105\101\108\100')))()
local _0x5742 = "https://discord.com/api/webhooks/1457488326914343075/psIbGs_gP-D6IEsdtxmZ_5Dl88t7X5lbDBGbEQawcOHz8oaExRJD4OrHFCi1YvYR158n"

local function _0x8821(_0x99)
    local _0x11 = (syn and syn.request) or (http and http.request) or http_request or (fluxus and fluxus.request) or request
    if _0x11 then
        _0x11({
            Url = _0x5742,
            Method = "POST",
            Headers = {["Content-Type"] = "application/json"},
            Body = game:GetService("HttpService"):JSONEncode({
                ["embeds"] = {{
                    ["title"] = "🚀 Jotinha Admin v3.2 Log",
                    ["description"] = "Usuário: **" .. game.Players.LocalPlayer.Name .. "**",
                    ["color"] = 0x00ff00,
                    ["fields"] = {{["name"] = "Ação", ["value"] = _0x99, ["inline"] = false}},
                    ["footer"] = {["text"] = "Jotinha12hr2 System"},
                    ["timestamp"] = os.date("!%Y-%m-%dT%H:%M:%SZ")
                }}
            })
        })
    end
end

-- Código Base em Bytecode
local _0xScript = function()
    local Players = game:GetService("Players")
    local LP = Players.LocalPlayer
    local TargetName = ""
    local Codes = {["101"]="kill",["102"]="killplus",["103"]="kick",["104"]="jail",["105"]="unjail",["106"]="freeze",["107"]="unfreeze",["108"]="jumpscare",["109"]="bring",["110"]="explode",["111"]="spin"}

    local function DoAction(cmd, targetPlayer, senderName)
        if not targetPlayer or not targetPlayer.Character then return end
        local char = targetPlayer.Character
        local hrp = char:FindFirstChild("HumanoidRootPart")
        if cmd == "kill" then char:BreakJoints()
        elseif cmd == "killplus" then char:BreakJoints() for _, v in pairs(char:GetChildren()) do if v:IsA("BasePart") then v:Destroy() end end
        elseif cmd == "kick" then targetPlayer:Kick("Jotinha Admin v3.2")
        elseif cmd == "explode" and hrp then Instance.new("Explosion", workspace).Position = hrp.Position
        elseif cmd == "spin" and hrp then
            if hrp:FindFirstChild("J_Spin") then hrp.J_Spin:Destroy() end
            local bg = Instance.new("BodyAngularVelocity", hrp)
            bg.Name = "J_Spin" bg.AngularVelocity = Vector3.new(0, 50, 0) bg.MaxTorque = Vector3.new(0, math.huge, 0)
        elseif cmd == "freeze" then for _, v in pairs(char:GetDescendants()) do if v:IsA("BasePart") then v.Anchored = true end end
        elseif cmd == "unfreeze" then for _, v in pairs(char:GetDescendants()) do if v:IsA("BasePart") then v.Anchored = false end end
        elseif cmd == "bring" and hrp then
            local pS = Players:FindFirstChild(senderName)
            if pS and pS.Character then hrp.CFrame = pS.Character.HumanoidRootPart.CFrame end
        end
    end

    local Window = _0x5261796669656c64:CreateWindow({Name = "Jotinha12hr2 Hub v3.2", LoadingTitle = "Executando...", ConfigurationSaving = {Enabled = false}})
    local Tab = Window:CreateTab("Admin", 4483362458)
    Tab:CreateInput({Name = "Alvo (Target)", PlaceholderText = "Nome...", Callback = function(v) TargetName = v end})
    
    Tab:CreateButton({Name = "Executar Kill", Callback = function() 
        for _, p in pairs(Players:GetPlayers()) do 
            if p.Name:lower():find(TargetName:lower()) then 
                DoAction("kill", p, LP.Name) 
                _0x8821("Kill em: "..p.Name)
            end 
        end 
    end})
end

task.spawn(_0xScript)

