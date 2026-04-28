-- 独立脚本：只获取吸血鬼刀（原样提取）
local Players = game:GetService("Players")
local lp = Players.LocalPlayer

local function getPurchaseEvent()
    local rs = game:GetService("ReplicatedStorage")
    local events = rs:FindFirstChild("Events")
    if not events then return nil end
    local customize = events:FindFirstChild("Customize")
    if not customize then return nil end
    return customize:FindFirstChild("PurchaseEvent")
end

local purchase = getPurchaseEvent()
if purchase then
    purchase:FireServer("Voivode")
    game:GetService("StarterGui"):SetCore("SendNotification", {Title="获取", Text="已获取吸血鬼刀", Duration=2})
end
