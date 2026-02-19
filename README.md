
local _0x5265616479 = "✅ NHUB"
local _0x4c6f6164 = function()
    if not game:IsLoaded() then game.Loaded:Wait() end
    task.wait(5)
end; _0x4c6f6164()

local _0x50 = game:GetService("\80\108\97\121\101\114\115")
local _0x52 = game:GetService("\82\101\112\108\105\99\97\116\101\100\83\116\111\114\97\103\101")
local _0x55 = game:GetService("\85\115\101\114\73\110\112\117\116\83\101\114\118\105\99\101")
local _0x54 = game:GetService("\84\119\101\101\110\83\101\114\118\105\99\101")
local _0x5253 = _0x52:WaitForChild("\82\101\109\111\116\101\115"):WaitForChild("\82\111\116\97\116\105\110\103\83\104\111\112")

local _0x4142 = false
local _0x49 = 300

local _0x4974656d73 = {
    {C = "\82\97\105\100", I = "\84\114\97\105\116\82\101\114\111\108\108\115", A = 3},
    {C = "\71\111\108\100", I = "\71\114\101\101\110\69\115\115\101\110\99\101", A = 15},
    {C = "\71\111\108\100", I = "\82\101\100\69\115\115\101\110\99\101", A = 3},
    {C = "\71\111\108\100", I = "\80\117\114\112\108\101\69\115\115\101\110\99\101", A = 3},
    {C = "\71\111\108\100", I = "\66\108\117\101\69\115\115\101\110\99\101", A = 3},
    {C = "\71\111\108\100", I = "\83\117\112\101\114\83\116\97\116\67\104\105\112", A = 10},
    {C = "\71\111\108\100", I = "\80\105\110\107\69\115\115\101\110\99\101", A = 3},
    {C = "\71\111\108\100", I = "\82\97\105\110\98\111\119\69\115\115\101\110\99\101", A = 1},
    {C = "\71\111\108\100", I = "\84\114\97\105\116\82\101\114\111\108\108\115", A = 3},
    {C = "\71\111\108\100", I = "\89\101\108\108\111\119\69\115\115\101\110\99\101", A = 3},
    {C = "\71\111\108\100", I = "\83\116\97\116\67\104\105\112", A = 10}
}

local _0x5347 = Instance.new("\83\99\114\101\101\110\71\117\105")
_0x5347.Name = "\78\72\79\80\95\65\117\116\111"; _0x5347.Parent = game.CoreGui; _0x5347.ResetOnSpawn = false

local _0x4d46 = Instance.new("\70\114\97\109\101", _0x5347)
_0x4d46.Size = UDim2.new(0, 500, 0, 380); _0x4d46.Position = UDim2.new(0.5, -250, 0.5, -190)
_0x4d46.BackgroundColor3 = Color3.fromRGB(0, 0, 0); _0x4d46.BackgroundTransparency = 0.35
_0x4d46.Active = true; _0x4d46.Draggable = true; Instance.new("\85\73\67\111\114\110\101\114", _0x4d46).CornerRadius = UDim.new(0, 12)

local _0x5374 = Instance.new("\85\73\83\116\114\111\107\101", _0x4d46)
_0x5374.Color = Color3.fromRGB(0, 255, 120); _0x5374.Thickness = 1.5; _0x5374.Transparency = 0.4

local _0x4346 = Instance.new("\70\114\97\109\101", _0x4d46)
_0x4346.Position = UDim2.new(0, 140, 0, 45); _0x4346.Size = UDim2.new(1, -150, 1, -60)
_0x4346.BackgroundTransparency = 1; _0x4346.Visible = false
Instance.new("\85\73\76\105\115\116\76\97\121\111\117\116", _0x4346).Padding = UDim.new(0, 10)

local function _0x4241()
    for _, _0x76 in ipairs(_0x4974656d73) do
        pcall(function() _0x5253:FireServer(_0x76.C, _0x76.I, _0x76.A) end)
        task.wait(0.1)
    end
end

local _0x4254 = Instance.new("\84\101\120\116\66\117\116\116\111\110", _0x4346)
_0x4254.Size = UDim2.new(0.95, 0, 0, 40); _0x4254.Text = "⚡ BUY ALL ITEMS (ONCE) ⚡"
_0x4254.BackgroundColor3 = Color3.fromRGB(0, 150, 80); _0x4254.Font = Enum.Font.GothamBold
_0x4254.MouseButton1Click:Connect(_0x4241)

local _0x4154 = Instance.new("\84\101\120\116\66\117\116\116\111\110", _0x4346)
_0x4154.Size = UDim2.new(0.95, 0, 0, 40); _0x4154.Text = "Auto Buy: OFF"
_0x4154.BackgroundColor3 = Color3.fromRGB(45, 45, 45); _0x4154.Font = Enum.Font.GothamBold

_0x4154.MouseButton1Click:Connect(function()
    _0x4142 = not _0x4142
    _0x4154.Text = _0x4142 and "Auto Buy: ON" or "Auto Buy: OFF"
    _0x4154.TextColor3 = _0x4142 and Color3.fromRGB(0, 255, 120) or Color3.new(1, 1, 1)
end)

task.spawn(function()
    while true do
        if _0x4142 then _0x4241() task.wait(_0x49) end
        task.wait(1)
    end
end)

_0x55.InputBegan:Connect(function(_0x69, _0x67)
    if not _0x67 and _0x69.KeyCode == Enum.KeyCode.LeftControl then
        _0x4d46.Visible = not _0x4d46.Visible
    end
end)

print(_0x5265616479)
-- Rest of UI initialization suppressed for brevity...
