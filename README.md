local P, CG, TS = game:GetService("Players"), game:GetService("CoreGui"), game:GetService("TweenService")
local LP = P.LocalPlayer local PG = LP:FindFirstChildOfClass("PlayerGui")
local Target = PG or CG if Target:FindFirstChild("AstraHub") then Target["AstraHub"]:Destroy() end
local SG = Instance.new("ScreenGui") SG.Name = "AstraHub" SG.ResetOnSpawn = false SG.Parent = Target
local function round(o, r) local c = Instance.new("UICorner") c.CornerRadius = UDim.new(0, r or 8) c.Parent = o end

local Temas = {
	["Dark"] = {F = Color3.fromRGB(25, 25, 30), T = Color3.fromRGB(18, 18, 22), B = Color3.fromRGB(45, 45, 55)},
	["Neon"] = {F = Color3.fromRGB(15, 10, 25), T = Color3.fromRGB(30, 15, 50), B = Color3.fromRGB(50, 20, 80)},
	["Vamp"] = {F = Color3.fromRGB(20, 10, 10), T = Color3.fromRGB(40, 10, 15), B = Color3.fromRGB(70, 15, 20)},
	["Menta"] = {F = Color3.fromRGB(20, 30, 25), T = Color3.fromRGB(15, 45, 35), B = Color3.fromRGB(30, 65, 50)}
}
local T_At, C_Load, C_Succ = "Dark", Color3.fromRGB(215, 160, 15), Color3.fromRGB(30, 160, 70)

local Main = Instance.new("Frame") Main.Size = UDim2.new(0, 480, 0, 320) Main.Position = UDim2.new(0.5, -240, 0.5, -160) Main.BackgroundColor3 = Temas[T_At].F Main.Active = true Main.Draggable = true Main.Parent = SG round(Main, 10)
local Bar = Instance.new("Frame") Bar.Size = UDim2.new(1, 0, 0, 38) Bar.BackgroundColor3 = Temas[T_At].T Bar.Parent = Main round(Bar, 10)
local Adj = Instance.new("Frame") Adj.Size = UDim2.new(1, 0, 0, 12) Adj.Position = UDim2.new(0, 0, 1, -12) Adj.BackgroundColor3 = Temas[T_At].T Adj.BorderSizePixel = 0 Adj.Parent = Bar

local Title = Instance.new("TextLabel") Title.Text = "  ★ Astra Hub Premium" Title.Size = UDim2.new(0.5, 0, 1, 0) Title.BackgroundTransparency = 1 Title.TextColor3 = Color3.fromRGB(255, 255, 255) Title.Font = Enum.Font.GothamBold Title.TextSize = 14 Title.TextXAlignment = Enum.TextXAlignment.Left Title.Parent = Bar
local B_Min = Instance.new("TextButton") B_Min.Text = "-" B_Min.Size = UDim2.new(0, 30, 0, 25) B_Min.Position = UDim2.new(1, -65, 0.5, -12) B_Min.BackgroundColor3 = Color3.fromRGB(40, 40, 45) B_Min.TextColor3 = Color3.fromRGB(220, 220, 220) B_Min.Font = Enum.Font.GothamBold B_Min.TextSize = 16 B_Min.Parent = Bar round(B_Min, 5)
local B_Cls = Instance.new("TextButton") B_Cls.Text = "X" B_Cls.Size = UDim2.new(0, 30, 0, 25) B_Cls.Position = UDim2.new(1, -35, 0.5, -12) B_Cls.BackgroundColor3 = Color3.fromRGB(180, 50, 50) B_Cls.TextColor3 = Color3.fromRGB(255, 255, 255) B_Cls.Font = Enum.Font.GothamBold B_Cls.TextSize = 12 B_Cls.Parent = Bar round(B_Cls, 5)

local Menu = Instance.new("Frame") Menu.Size = UDim2.new(0, 110, 1, -38) Menu.Position = UDim2.new(0, 0, 0, 38) Menu.BackgroundColor3 = Temas[T_At].T Menu.Parent = Main
local LLM = Instance.new("UIListLayout") LLM.Padding = UDim.new(0, 5) LLM.HorizontalAlignment = Enum.HorizontalAlignment.Center LLM.Parent = Menu

local A_Hub = Instance.new("TextButton") A_Hub.Text = "Jogos" A_Hub.Size = UDim2.new(0.85, 0, 0, 30) A_Hub.BackgroundColor3 = Temas[T_At].B A_Hub.TextColor3 = Color3.fromRGB(255, 255, 255) A_Hub.Font = Enum.Font.GothamBold A_Hub.TextSize = 11 A_Hub.Parent = Menu round(A_Hub, 6)
local A_Mini = Instance.new("TextButton") A_Mini.Text = "" A_Mini.Size = UDim2.new(0.0, 0, 0, 0) A_Mini.BackgroundColor3 = Temas[T_At].B A_Mini.TextColor3 = Color3.fromRGB(180, 180, 180) A_Mini.Font = Enum.Font.GothamBold A_Mini.TextSize = 11 A_Mini.Parent = Menu round(A_Mini, 6)
local A_Cfg = Instance.new("TextButton") A_Cfg.Text = "Temas" A_Cfg.Size = UDim2.new(0.85, 0, 0, 30) A_Cfg.BackgroundColor3 = Temas[T_At].B A_Cfg.TextColor3 = Color3.fromRGB(180, 180, 180) A_Cfg.Font = Enum.Font.GothamBold A_Cfg.TextSize = 11 A_Cfg.Parent = Menu round(A_Cfg, 6)
local Cred = Instance.new("TextLabel") Cred.Text = "By: Micah64362" Cred.Size = UDim2.new(1, 0, 0, 20) Cred.Position = UDim2.new(0, 8, 1, -22) Cred.BackgroundTransparency = 1 Cred.TextColor3 = Color3.fromRGB(130, 130, 140) Cred.Font = Enum.Font.GothamMedium Cred.TextSize = 10 Cred.Parent = Menu

local P_Hubs = Instance.new("Frame") P_Hubs.Size = UDim2.new(1, -120, 1, -85) P_Hubs.Position = UDim2.new(0, 115, 0, 80) P_Hubs.BackgroundTransparency = 1 P_Hubs.Parent = Main
local P_Minis = Instance.new("Frame") P_Minis.Size = UDim2.new(1, -120, 1, -50) P_Minis.Position = UDim2.new(0, 115, 0, 45) P_Minis.BackgroundTransparency = 1 P_Minis.Visible = false P_Minis.Parent = Main
local P_Cfgs = Instance.new("Frame") P_Cfgs.Size = UDim2.new(1, -120, 1, -50) P_Cfgs.Position = UDim2.new(0, 115, 0, 45) P_Cfgs.BackgroundTransparency = 1 P_Cfgs.Visible = false P_Cfgs.Parent = Main

local SearchBar = Instance.new("TextBox") SearchBar.PlaceholderText = "Pesquisar jogo..." SearchBar.Size = UDim2.new(1, -135, 0, 30) SearchBar.Position = UDim2.new(0, 115, 0, 45) SearchBar.BackgroundColor3 = Color3.fromRGB(35, 35, 40) SearchBar.TextColor3 = Color3.fromRGB(255, 255, 255) SearchBar.Font = Enum.Font.GothamMedium SearchBar.TextSize = 12 SearchBar.Parent = Main round(SearchBar, 6)

local G_Hubs = Instance.new("UIGridLayout") G_Hubs.CellSize = UDim2.new(0, 160, 0, 50) G_Hubs.CellPadding = UDim2.new(0, 12, 0, 12) G_Hubs.Parent = P_Hubs
local G_Minis = Instance.new("UIGridLayout") G_Minis.CellSize = UDim2.new(0, 160, 0, 50) G_Minis.CellPadding = UDim2.new(0, 12, 0, 12) G_Minis.Parent = P_Minis
local G_Cfgs = Instance.new("UIGridLayout") G_Cfgs.CellSize = UDim2.new(0, 160, 0, 45) G_Cfgs.CellPadding = UDim2.new(0, 12, 0, 12) G_Cfgs.Parent = P_Cfgs

local function resetAbas() P_Hubs.Visible, P_Minis.Visible, P_Cfgs.Visible, SearchBar.Visible = false, false, false, false A_Hub.TextColor3, A_Mini.TextColor3, A_Cfg.TextColor3 = Color3.fromRGB(180, 180, 180), Color3.fromRGB(180, 180, 180), Color3.fromRGB(180, 180, 180) end
A_Hub.MouseButton1Click:Connect(function() resetAbas() P_Hubs.Visible, SearchBar.Visible = true, true A_Hub.TextColor3 = Color3.fromRGB(255, 255, 255) end)
A_Mini.MouseButton1Click:Connect(function() resetAbas() P_Minis.Visible = true A_Mini.TextColor3 = Color3.fromRGB(255, 255, 255) end)
A_Cfg.MouseButton1Click:Connect(function() resetAbas() P_Cfgs.Visible = true A_Cfg.TextColor3 = Color3.fromRGB(255, 255, 255) end)

local gameButtons = {}
local function regGame(n, f)
	local b = Instance.new("TextButton") b.Text = n b.BackgroundColor3 = Temas[T_At].B b.TextColor3 = Color3.fromRGB(255, 255, 255) b.Font = Enum.Font.GothamBold b.TextSize = 12 b.Parent = P_Hubs round(b, 6) gameButtons[n] = b
	local clk = false b.MouseButton1Click:Connect(function()
		if clk then return end clk = true b.Text = "Carregando..." TS:Create(b, TweenInfo.new(0.25), {BackgroundColor3 = C_Load}):Play()
		task.spawn(function()
			local s, r = pcall(f) task.wait(0.6)
			if s then b.Text = "Executado!" TS:Create(b, TweenInfo.new(0.3), {BackgroundColor3 = C_Succ}):Play() task.wait(2.5)
			else b.Text = "Erro!" b.BackgroundColor3 = Color3.fromRGB(180, 50, 50) task.wait(2) end
			b.Text = n TS:Create(b, TweenInfo.new(0.3), {BackgroundColor3 = Temas[T_At].B}):Play() clk = false
		end)
	end)
end

SearchBar:GetPropertyChangedSignal("Text"):Connect(function()
	local text = SearchBar.Text:lower()
	for name, btn in pairs(gameButtons) do
		if text == "" or name:lower():find(text) then btn.Visible = true else btn.Visible = false end
	end
end)

regGame("Slap Battles", function() loadstring(game:HttpGet("https://raw.githubusercontent.com/interscripting/OPSlapRoyale/main/OPSlapRoyalePCUI"))() end)
regGame("MPS", function() loadstring(game:HttpGet("https://raw.githubusercontent.com/wrestonbest/Helixia-2026/refs/heads/main/Universal%20Reach/v1.lua"))() end)
regGame("Brookhaven", function() loadstring(game:HttpGet("https://raw.githubusercontent.com/as6cd0/SP_Hub/refs/heads/main/Brookhaven"))() end)
regGame("Infinite Yield", function() loadstring(game:HttpGet("https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source"))() end)
regGame("StrongMan Simulator", function() loadstring(game:HttpGet("https://raw.githubusercontent.com/SpdmXDev/luascripts/refs/heads/main/AtwiStrongman"))() end)
regGame("Rivals", function() loadstring(game:HttpGet("https://flowauth.net/v1/ui/d00ec69382de97372fc9559efc722298.lua"))() end)
regGame("Forsaken", function() loadstring(game:HttpGet("https://raw.githubusercontent.com/zxcursedsocute/Forsaken-Script/refs/heads/main/lua"))() end)

local function regMini(n, clickFunc)
	local b = Instance.new("TextButton") b.Text = n b.BackgroundColor3 = Temas[T_At].B b.TextColor3 = Color3.fromRGB(255, 255, 255) b.Font = Enum.Font.GothamBold b.TextSize = 12 b.Parent = P_Minis round(b, 6)
	b.MouseButton1Click:Connect(clickFunc)
end

local btnsTema = {}
local function chgTema(tName)
	T_At = tName local info = Temas[tName]
	Main.BackgroundColor3 = info.F Bar.BackgroundColor3 = info.T Adj.BackgroundColor3 = info.T Menu.BackgroundColor3 = info.T A_Hub.BackgroundColor3 = info.B A_Cfg.BackgroundColor3 = info.B A_Mini.BackgroundColor3 = info.B
	for _, b in pairs(gameButtons) do if b.Text ~= "Carregando..." and b.Text ~= "Executado!" and b.Text ~= "Erro!" then b.BackgroundColor3 = info.B end end
	for _, b in ipairs(btnsTema) do b.BackgroundColor3 = info.B end
end
local function regTema(tName)
	local b = Instance.new("TextButton") b.Text = "Tema: " .. tName b.BackgroundColor3 = Temas[T_At].B b.TextColor3 = Color3.fromRGB(255, 255, 255) b.Font = Enum.Font.GothamBold b.TextSize = 11 b.Parent = P_Cfgs round(b, 6) table.insert(btnsTema, b)
	b.MouseButton1Click:Connect(function() chgTema(tName) end)
end
regTema("Dark") regTema("Neon") regTema("Vamp") regTema("Menta")

local Pop = Instance.new("Frame") Pop.Size = UDim2.new(0, 240, 0, 120) Pop.Position = UDim2.new(0.5, -120, 0.5, -60) Pop.BackgroundColor3 = Color3.fromRGB(30, 30, 35) Pop.Visible = false Pop.ZIndex = 5 Pop.Parent = SG round(Pop, 10)
local Lbl = Instance.new("TextLabel") Lbl.Text = "Deseja fechar o Astra?" Lbl.Size = UDim2.new(1, 0, 0, 50) Lbl.BackgroundTransparency = 1 Lbl.TextColor3 = Color3.fromRGB(255, 255, 255) Lbl.Font = Enum.Font.GothamMedium Lbl.TextSize = 14 Lbl.ZIndex = 5 Lbl.Parent = Pop
local B_Y = Instance.new("TextButton") B_Y.Text = "Sim" B_Y.Size = UDim2.new(0, 80, 0, 32) B_Y.Position = UDim2.new(0, 25, 0, 65) B_Y.BackgroundColor3 = Color3.fromRGB(180, 50, 50) B_Y.TextColor3 = Color3.fromRGB(255, 255, 255) B_Y.Font = Enum.Font.GothamBold B_Y.TextSize = 13 B_Y.ZIndex = 5 B_Y.Parent = Pop round(B_Y, 5)local B_N = Instance.new("TextButton") B_N.Text = "Não" B_N.Size = UDim2.new(0, 80, 0, 32) B_N.Position = UDim2.new(1, -105, 0, 65) B_N.BackgroundColor3 = Color3.fromRGB(60, 60, 65) B_N.TextColor3 = Color3.fromRGB(255, 255, 255) B_N.Font = Enum.Font.GothamBold B_N.TextSize = 13 B_N.ZIndex = 5 B_N.Parent = Pop round(B_N, 5)local B_Op = Instance.new("TextButton") B_Op.Name = "BotaoAbrir" B_Op.Text = "Abrir Astra" B_Op.Size = UDim2.new(0, 110, 0, 35) B_Op.Position = UDim2.new(1, -125, 0, 15) B_Op.BackgroundColor3 = Color3.fromRGB(45, 100, 230) B_Op.TextColor3 = Color3.fromRGB(255, 255, 255) B_Op.Font = Enum.Font.GothamBold B_Op.TextSize = 12 B_Op.Visible = false B_Op.Parent = SG round(B_Op, 6)B_Min.MouseButton1Click:Connect(function() Main.Visible = false B_Op.Visible = true end)B_Op.MouseButton1Click:Connect(function() B_Op.Visible = false Main.Visible = true end)B_Cls.MouseButton1Click:Connect(function() Pop.Visible = true end)B_N.MouseButton1Click:Connect(function() Pop.Visible = false end)B_Y.MouseButton1Click:Connect(function() SG:Destroy() end)
