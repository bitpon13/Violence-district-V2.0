# Violence-district-V2.0
Script=Flashlight+crosshair+Clear fog
--[[
    VIOLENCE DISTRICT PRO 2.0
    FLASHLIGHT + TIRA NEBLINA + MIRA
    SISTEMA DE KEY - MOBILE
    By Assistant
]]

repeat task.wait() until game:IsLoaded()
task.wait(2)

-- ==================== SISTEMA DE KEY ====================
local KEY_CORRETA = "B13"

local KeyScreen = Instance.new("ScreenGui")
KeyScreen.Name = "KeySystemB13"
KeyScreen.Parent = game:GetService("CoreGui")
KeyScreen.ResetOnSpawn = false
KeyScreen.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
KeyScreen.IgnoreGuiInset = true

local Background = Instance.new("Frame")
Background.Size = UDim2.new(1, 0, 1, 0)
Background.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
Background.BackgroundTransparency = 0.5
Background.BorderSizePixel = 0
Background.Parent = KeyScreen

local KeyPanel = Instance.new("Frame")
KeyPanel.Size = UDim2.new(0, 300, 0, 240)
KeyPanel.Position = UDim2.new(0.5, -150, 0.5, -120)
KeyPanel.BackgroundColor3 = Color3.fromRGB(15, 15, 15)
KeyPanel.BorderSizePixel = 0
KeyPanel.ClipsDescendants = true
KeyPanel.Parent = Background

local PanelCorner = Instance.new("UICorner")
PanelCorner.CornerRadius = UDim.new(0, 10)
PanelCorner.Parent = KeyPanel

local PanelStroke = Instance.new("UIStroke")
PanelStroke.Thickness = 2
PanelStroke.Color = Color3.fromRGB(255, 215, 0)
PanelStroke.Parent = KeyPanel

local TopBar = Instance.new("Frame")
TopBar.Size = UDim2.new(1, 0, 0, 40)
TopBar.BackgroundColor3 = Color3.fromRGB(139, 0, 0)
TopBar.BorderSizePixel = 0
TopBar.Parent = KeyPanel

local TopCorner = Instance.new("UICorner")
TopCorner.CornerRadius = UDim.new(0, 10)
TopCorner.Parent = TopBar

local TopFix = Instance.new("Frame")
TopFix.Size = UDim2.new(1, 0, 0, 10)
TopFix.Position = UDim2.new(0, 0, 0, 30)
TopFix.BackgroundColor3 = Color3.fromRGB(139, 0, 0)
TopFix.BorderSizePixel = 0
TopFix.Parent = TopBar

local Title = Instance.new("TextLabel")
Title.Size = UDim2.new(1, 0, 1, 0)
Title.BackgroundTransparency = 1
Title.Text = "VIOLENCE DISTRICT"
Title.TextSize = 15
Title.Font = Enum.Font.GothamBlack
Title.TextColor3 = Color3.fromRGB(255, 255, 255)
Title.Parent = TopBar

-- Ícone pequeno no lugar do B13 grande
local IconFrame = Instance.new("Frame")
IconFrame.Size = UDim2.new(0, 40, 0, 40)
IconFrame.Position = UDim2.new(0.5, -20, 0, 50)
IconFrame.BackgroundColor3 = Color3.fromRGB(139, 0, 0)
IconFrame.BorderSizePixel = 0
IconFrame.Parent = KeyPanel

local IconCorner = Instance.new("UICorner")
IconCorner.CornerRadius = UDim.new(0.3, 0)
IconCorner.Parent = IconFrame

local IconStroke = Instance.new("UIStroke")
IconStroke.Thickness = 1.5
IconStroke.Color = Color3.fromRGB(255, 215, 0)
IconStroke.Parent = IconFrame

local IconText = Instance.new("TextLabel")
IconText.Size = UDim2.new(1, 0, 1, 0)
IconText.BackgroundTransparency = 1
IconText.Text = "🔒"
IconText.TextSize = 20
IconText.Font = Enum.Font.Gotham
IconText.TextColor3 = Color3.fromRGB(255, 255, 255)
IconText.Parent = IconFrame

local StatusText = Instance.new("TextLabel")
StatusText.Size = UDim2.new(1, -20, 0, 25)
StatusText.Position = UDim2.new(0, 10, 0, 98)
StatusText.BackgroundTransparency = 1
StatusText.Text = "Digite a key para acessar"
StatusText.TextSize = 12
StatusText.Font = Enum.Font.Gotham
StatusText.TextColor3 = Color3.fromRGB(200, 200, 200)
StatusText.Parent = KeyPanel

local KeyInput = Instance.new("TextBox")
KeyInput.Size = UDim2.new(0, 240, 0, 38)
KeyInput.Position = UDim2.new(0.5, -120, 0, 128)
KeyInput.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
KeyInput.BorderSizePixel = 0
KeyInput.PlaceholderText = "KEY..."
KeyInput.PlaceholderColor3 = Color3.fromRGB(150, 150, 150)
KeyInput.Text = ""
KeyInput.TextSize = 16
KeyInput.Font = Enum.Font.GothamBold
KeyInput.TextColor3 = Color3.fromRGB(255, 255, 255)
KeyInput.Parent = KeyPanel

local InputCorner = Instance.new("UICorner")
InputCorner.CornerRadius = UDim.new(0, 6)
InputCorner.Parent = KeyInput

local InputStroke = Instance.new("UIStroke")
InputStroke.Thickness = 1.5
InputStroke.Color = Color3.fromRGB(255, 215, 0)
InputStroke.Transparency = 0.5
InputStroke.Parent = KeyInput

local ConfirmBtn = Instance.new("TextButton")
ConfirmBtn.Size = UDim2.new(0, 240, 0, 38)
ConfirmBtn.Position = UDim2.new(0.5, -120, 0, 178)
ConfirmBtn.BackgroundColor3 = Color3.fromRGB(139, 0, 0)
ConfirmBtn.BorderSizePixel = 0
ConfirmBtn.Text = "CONFIRMAR"
ConfirmBtn.TextSize = 15
ConfirmBtn.Font = Enum.Font.GothamBlack
ConfirmBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
ConfirmBtn.Parent = KeyPanel

local BtnCorner = Instance.new("UICorner")
BtnCorner.CornerRadius = UDim.new(0, 6)
BtnCorner.Parent = ConfirmBtn

local BtnStroke = Instance.new("UIStroke")
BtnStroke.Thickness = 1.5
BtnStroke.Color = Color3.fromRGB(255, 215, 0)
BtnStroke.Parent = ConfirmBtn

local function checkKey()
    local key = KeyInput.Text
    if key == KEY_CORRETA then
        StatusText.Text = "ACESSO LIBERADO!"
        StatusText.TextColor3 = Color3.fromRGB(0, 255, 100)
        ConfirmBtn.BackgroundColor3 = Color3.fromRGB(0, 150, 0)
        ConfirmBtn.Text = "LIBERADO!"
        task.wait(0.5)
        KeyScreen:Destroy()
        iniciarScript()
    else
        StatusText.Text = "KEY INVALIDA!"
        StatusText.TextColor3 = Color3.fromRGB(255, 50, 50)
        ConfirmBtn.BackgroundColor3 = Color3.fromRGB(180, 0, 0)
        KeyInput.Text = ""
        task.wait(0.8)
        StatusText.Text = "Digite a key para acessar"
        StatusText.TextColor3 = Color3.fromRGB(200, 200, 200)
        ConfirmBtn.BackgroundColor3 = Color3.fromRGB(139, 0, 0)
    end
end

ConfirmBtn.MouseButton1Click:Connect(checkKey)
ConfirmBtn.TouchTap:Connect(checkKey)

-- ==================== SCRIPT PRINCIPAL ====================
function iniciarScript()
    local flashAtivo = false
    local neblinaAtiva = false
    local miraAtiva = false
    local mira
    local B13Btn

    local lighting = game:GetService("Lighting")
    local configOriginal = {
        Brightness = lighting.Brightness,
        Ambient = lighting.Ambient,
        OutdoorAmbient = lighting.OutdoorAmbient,
        ExposureCompensation = lighting.ExposureCompensation,
        ClockTime = lighting.ClockTime,
        FogEnd = lighting.FogEnd,
        FogStart = lighting.FogStart,
        FogColor = lighting.FogColor,
        GlobalShadows = lighting.GlobalShadows
    }

    -- ==================== FLASHLIGHT SUAVE ====================
    local function FlashLight(estado)
        local l = game:GetService("Lighting")
        if estado then
            -- Brilho bem suave e natural
            l.Brightness = 2.5
            l.Ambient = Color3.fromRGB(180, 180, 180)
            l.OutdoorAmbient = Color3.fromRGB(160, 160, 160)
            l.ExposureCompensation = 0.3
            l.ClockTime = 13
            l.GlobalShadows = false
            l.ShadowSoftness = 0.2
            l.FogEnd = 50000
            l.FogStart = 30000
            l.FogColor = Color3.fromRGB(150, 150, 150)
            if l:FindFirstChild("Atmosphere") then 
                l.Atmosphere:Destroy() 
            end
        else
            l.Brightness = configOriginal.Brightness
            l.Ambient = configOriginal.Ambient
            l.OutdoorAmbient = configOriginal.OutdoorAmbient
            l.ExposureCompensation = configOriginal.ExposureCompensation
            l.ClockTime = configOriginal.ClockTime
            l.GlobalShadows = configOriginal.GlobalShadows
            l.ShadowSoftness = 0.5
            l.FogEnd = configOriginal.FogEnd
            l.FogStart = configOriginal.FogStart
            l.FogColor = configOriginal.FogColor
        end
    end

    -- ==================== TIRA NEBLINA ====================
    local function RemoveFog(estado)
        local l = game:GetService("Lighting")
        if estado then
            l.FogEnd = 999999
            l.FogStart = 999999
            l.FogColor = Color3.fromRGB(255, 255, 255)
            l.GlobalShadows = false
            l.ShadowSoftness = 0
            if l:FindFirstChild("Atmosphere") then 
                l.Atmosphere:Destroy() 
            end
            for _, obj in pairs(workspace:GetDescendants()) do
                if obj:IsA("Atmosphere") then 
                    obj:Destroy() 
                end
                if obj.ClassName == "Fog" then 
                    obj:Destroy() 
                end
            end
        else
            l.FogEnd = configOriginal.FogEnd
            l.FogStart = configOriginal.FogStart
            l.FogColor = configOriginal.FogColor
            l.GlobalShadows = configOriginal.GlobalShadows
            l.ShadowSoftness = 0.5
            if not l:FindFirstChild("Atmosphere") then
                Instance.new("Atmosphere", l)
            end
        end
    end

    -- ==================== MIRA BOLA ====================
    local function AtivarMira(estado)
        if estado then
            if mira then mira:Remove() end
            mira = Drawing.new("Circle")
            mira.Visible = true
            mira.Color = Color3.fromRGB(255, 0, 0)
            mira.Thickness = 1.5
            mira.Radius = 8
            mira.Filled = true
            mira.Transparency = 0.3
            mira.Position = Vector2.new(
                workspace.CurrentCamera.ViewportSize.X/2,
                workspace.CurrentCamera.ViewportSize.Y/2
            )
            local conn
            conn = game:GetService("RunService").RenderStepped:Connect(function()
                if mira and miraAtiva then
                    pcall(function()
                        mira.Position = Vector2.new(
                            workspace.CurrentCamera.ViewportSize.X/2,
                            workspace.CurrentCamera.ViewportSize.Y/2
                        )
                    end)
                else
                    if conn then conn:Disconnect() end
                end
            end)
        else
            if mira then 
                mira:Remove()
                mira = nil 
            end
        end
    end

    -- ==================== BOTÃO FLUTUANTE B13 ====================
    local B13Gui = Instance.new("ScreenGui")
    B13Gui.Name = "B13_FloatingButton"
    B13Gui.Parent = game:GetService("CoreGui")
    B13Gui.ResetOnSpawn = false
    B13Gui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

    B13Btn = Instance.new("TextButton")
    B13Btn.Size = UDim2.new(0, 50, 0, 50)
    B13Btn.Position = UDim2.new(1, -60, 0, 10)
    B13Btn.BackgroundColor3 = Color3.fromRGB(139, 0, 0)
    B13Btn.BorderSizePixel = 0
    B13Btn.Text = "B13"
    B13Btn.TextSize = 16
    B13Btn.Font = Enum.Font.GothamBlack
    B13Btn.TextColor3 = Color3.fromRGB(255, 255, 255)
    B13Btn.Visible = false
    B13Btn.Active = true
    B13Btn.Selectable = true
    B13Btn.Parent = B13Gui
    B13Btn.ZIndex = 999

    local B13Corner = Instance.new("UICorner")
    B13Corner.CornerRadius = UDim.new(0.3, 0)
    B13Corner.Parent = B13Btn

    local B13Stroke = Instance.new("UIStroke")
    B13Stroke.Thickness = 2
    B13Stroke.Color = Color3.fromRGB(255, 215, 0)
    B13Stroke.Parent = B13Btn

    -- Arrastar botão B13
    local UIS = game:GetService("UserInputService")
    local arrastando = false
    local inicioPos, inicioBtn

    B13Btn.InputBegan:Connect(function(input)
        if input.UserInputType == Enum.UserInputType.Touch or 
           input.UserInputType == Enum.UserInputType.MouseButton1 then
            arrastando = true
            inicioPos = input.Position
            inicioBtn = B13Btn.Position
        end
    end)

    B13Btn.InputEnded:Connect(function(input)
        if input.UserInputType == Enum.UserInputType.Touch or 
           input.UserInputType == Enum.UserInputType.MouseButton1 then
            arrastando = false
        end
    end)

    UIS.InputChanged:Connect(function(input)
        if arrastando and (input.UserInputType == Enum.UserInputType.Touch or 
           input.UserInputType == Enum.UserInputType.MouseMovement) then
            local delta = input.Position - inicioPos
            local nx = math.clamp(inicioBtn.X.Offset + delta.X, 0, 
                workspace.CurrentCamera.ViewportSize.X - 50)
            local ny = math.clamp(inicioBtn.Y.Offset + delta.Y, 0, 
                workspace.CurrentCamera.ViewportSize.Y - 50)
            B13Btn.Position = UDim2.new(0, nx, 0, ny)
        end
    end)

    -- ==================== PAINEL FLUENT ====================
    local Fluent = loadstring(game:HttpGet("https://github.com/dawid-scripts/Fluent/releases/latest/download/main.lua"))()
    local SaveManager = loadstring(game:HttpGet("https://raw.githubusercontent.com/dawid-scripts/Fluent/master/Addons/SaveManager.lua"))()
    local InterfaceManager = loadstring(game:HttpGet("https://raw.githubusercontent.com/dawid-scripts/Fluent/master/Addons/InterfaceManager.lua"))()

    local Window = Fluent:CreateWindow({
        Title = "VIOLENCE DISTRICT PRO 2.0",
        SubTitle = "Mobile",
        TabWidth = 160,
        Size = UDim2.fromOffset(420, 350),
        Acrylic = false,
        Theme = "Dark",
        MinimizeKey = Enum.KeyCode.RightControl
    })

    local function togglePainel()
        local gui = Window:GetGui()
        if gui and gui.Enabled then
            gui.Enabled = false
            if B13Btn then
                B13Btn.Visible = true
                B13Btn.ZIndex = 999
            end
        else
            if gui then 
                gui.Enabled = true 
            end
            if B13Btn then
                B13Btn.Visible = false
            end
        end
    end

    B13Btn.MouseButton1Click:Connect(function()
        if not arrastando then
            togglePainel()
        end
    end)
    
    B13Btn.TouchTap:Connect(function()
        if not arrastando then
            togglePainel()
        end
    end)

    spawn(function()
        while task.wait(0.3) do
            pcall(function()
                local gui = Window:GetGui()
                if gui and B13Btn then
                    if not gui.Enabled and not B13Btn.Visible then
                        B13Btn.Visible = true
                        B13Btn.ZIndex = 999
                    elseif gui.Enabled and B13Btn.Visible then
                        B13Btn.Visible = false
                    end
                end
            end)
        end
    end)

    local Tabs = {
        Main = Window:AddTab({ Title = "Principal", Icon = "rbxassetid://7733960981" }),
        Settings = Window:AddTab({ Title = "Ajustes", Icon = "rbxassetid://7733996608" })
    }

    Fluent:Notify({
        Title = "VIOLENCE DISTRICT PRO 2.0",
        Content = "Sistema liberado!",
        Duration = 3
    })

    -- ==================== BOTÕES PRINCIPAIS ====================
    Tabs.Main:AddToggle("Flash", {
        Title = "FLASHLIGHT SUAVE",
        Description = "Iluminacao natural e leve",
        Default = false,
        Callback = function(v)
            flashAtivo = v
            FlashLight(v)
        end
    })

    Tabs.Main:AddToggle("Neblina", {
        Title = "TIRA NEBLINA",
        Description = "Remove neblina e escuridao",
        Default = false,
        Callback = function(v)
            neblinaAtiva = v
            RemoveFog(v)
        end
    })

    Tabs.Main:AddToggle("Mira", {
        Title = "MIRA BOLA VERMELHA",
        Description = "Bola vermelha no centro",
        Default = false,
        Callback = function(v)
            miraAtiva = v
            AtivarMira(v)
        end
    })

    -- ==================== AJUSTES ====================
    Tabs.Settings:AddParagraph({
        Title = "PERSONALIZACAO DA MIRA",
        Content = "Use os sliders abaixo para ajustar"
    })

    Tabs.Settings:AddSlider("TamMira", {
        Title = "Tamanho da Bola",
        Description = "Ajuste o tamanho da mira",
        Default = 8,
        Min = 2,
        Max = 25,
        Rounding = 0,
        Callback = function(v)
            if mira then 
                pcall(function()
                    mira.Radius = math.floor(v)
                end)
            end
        end
    })

    Tabs.Settings:AddSlider("TranspMira", {
        Title = "Transparencia",
        Description = "0 = opaca | 1 = transparente",
        Default = 0.3,
        Min = 0,
        Max = 1,
        Rounding = 1,
        Callback = function(v)
            if mira then 
                pcall(function()
                    mira.Transparency = math.floor(v * 10) / 10
                end)
            end
        end
    })

    Tabs.Settings:AddColorpicker("CorMira", {
        Title = "Cor da Mira",
        Description = "Escolha a cor da bola",
        Default = Color3.fromRGB(255, 0, 0),
        Callback = function(v)
            if mira then 
                pcall(function()
                    mira.Color = v
                end)
            end
        end
    })

    SaveManager:SetLibrary(Fluent)
    InterfaceManager:SetLibrary(Fluent)
    SaveManager:IgnoreThemeSettings()
    InterfaceManager:SetFolder("ViolenceDistrictPro")
    SaveManager:SetFolder("ViolenceDistrictPro/settings")
    InterfaceManager:BuildInterfaceSection(Tabs.Settings)
    SaveManager:BuildConfigSection(Tabs.Settings)
    Window:SelectTab(1)

    spawn(function()
        while task.wait(10) do
            pcall(function()
                if flashAtivo then FlashLight(true) end
                if neblinaAtiva then RemoveFog(true) end
            end)
        end
    end)
end
