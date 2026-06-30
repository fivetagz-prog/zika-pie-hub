local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local TweenService = game:GetService("TweenService")
local LocalPlayer = Players.LocalPlayer

local function playClick()
    local sound = Instance.new("Sound")
    sound.SoundId = "rbxassetid://6042053626"
    sound.Volume = 0.5
    sound.Parent = game:GetService("SoundService")
    sound:Play()
    game:GetService("Debris"):AddItem(sound, 2)
end

local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Name = "ZikaHub"
ScreenGui.ResetOnSpawn = false
ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
ScreenGui.Parent = LocalPlayer:WaitForChild("PlayerGui")

local MainFrame = Instance.new("Frame")
MainFrame.Name = "MainFrame"
MainFrame.Size = UDim2.new(0, 280, 0, 340)
MainFrame.Position = UDim2.new(0.5, -140, 0.5, -170)
MainFrame.BackgroundColor3 = Color3.fromRGB(15, 10, 25)
MainFrame.BorderSizePixel = 0
MainFrame.Active = true
MainFrame.Draggable = true
MainFrame.Parent = ScreenGui

local UICorner = Instance.new("UICorner")
UICorner.CornerRadius = UDim.new(0, 12)
UICorner.Parent = MainFrame

local UIStroke = Instance.new("UIStroke")
UIStroke.Color = Color3.fromRGB(120, 60, 220)
UIStroke.Thickness = 1.5
UIStroke.Parent = MainFrame

local HeaderFrame = Instance.new("Frame")
HeaderFrame.Size = UDim2.new(1, 0, 0, 52)
HeaderFrame.BackgroundColor3 = Color3.fromRGB(100, 40, 200)
HeaderFrame.BorderSizePixel = 0
HeaderFrame.Parent = MainFrame

local HeaderCorner = Instance.new("UICorner")
HeaderCorner.CornerRadius = UDim.new(0, 12)
HeaderCorner.Parent = HeaderFrame

local HeaderFix = Instance.new("Frame")
HeaderFix.Size = UDim2.new(1, 0, 0, 12)
HeaderFix.Position = UDim2.new(0, 0, 1, -12)
HeaderFix.BackgroundColor3 = Color3.fromRGB(100, 40, 200)
HeaderFix.BorderSizePixel = 0
HeaderFix.Parent = HeaderFrame

local HeaderGradient = Instance.new("UIGradient")
HeaderGradient.Color = ColorSequence.new({
    ColorSequenceKeypoint.new(0, Color3.fromRGB(140, 40, 220)),
    ColorSequenceKeypoint.new(0.5, Color3.fromRGB(40, 80, 220)),
    ColorSequenceKeypoint.new(1, Color3.fromRGB(0, 200, 230)),
})
HeaderGradient.Rotation = 90
HeaderGradient.Parent = HeaderFrame

local gradientOffset = 0
RunService.Heartbeat:Connect(function(dt)
    gradientOffset = (gradientOffset + dt * 0.3) % 1
    local t = math.abs(math.sin(gradientOffset * math.pi))
    HeaderGradient.Rotation = 90 + t * 20
end)

local TitleLabel = Instance.new("TextLabel")
TitleLabel.Size = UDim2.new(1, -16, 0, 28)
TitleLabel.Position = UDim2.new(0, 12, 0, 8)
TitleLabel.BackgroundTransparency = 1
TitleLabel.Text = "Zika Hub"
TitleLabel.TextColor3 = Color3.fromRGB(230, 220, 255)
TitleLabel.TextSize = 18
TitleLabel.Font = Enum.Font.GothamBold
TitleLabel.TextXAlignment = Enum.TextXAlignment.Left
TitleLabel.Parent = HeaderFrame

local SubLabel = Instance.new("TextLabel")
SubLabel.Size = UDim2.new(1, -16, 0, 16)
SubLabel.Position = UDim2.new(0, 12, 0, 34)
SubLabel.BackgroundTransparency = 1
SubLabel.Text = "ESP and Utilities"
SubLabel.TextColor3 = Color3.fromRGB(160, 190, 255)
SubLabel.TextSize = 11
SubLabel.Font = Enum.Font.Gotham
SubLabel.TextXAlignment = Enum.TextXAlignment.Left
SubLabel.Parent = HeaderFrame

local ContentFrame = Instance.new("ScrollingFrame")
ContentFrame.Size = UDim2.new(1, 0, 1, -52)
ContentFrame.Position = UDim2.new(0, 0, 0, 52)
ContentFrame.BackgroundTransparency = 1
ContentFrame.BorderSizePixel = 0
ContentFrame.ScrollBarThickness = 3
ContentFrame.ScrollBarImageColor3 = Color3.fromRGB(100, 80, 200)
ContentFrame.CanvasSize = UDim2.new(0, 0, 0, 0)
ContentFrame.AutomaticCanvasSize = Enum.AutomaticSize.Y
ContentFrame.Parent = MainFrame

local UIListLayout = Instance.new("UIListLayout")
UIListLayout.Padding = UDim.new(0, 8)
UIListLayout.Parent = ContentFrame

local UIPadding = Instance.new("UIPadding")
UIPadding.PaddingLeft = UDim.new(0, 12)
UIPadding.PaddingRight = UDim.new(0, 12)
UIPadding.PaddingTop = UDim.new(0, 10)
UIPadding.PaddingBottom = UDim.new(0, 10)
UIPadding.Parent = ContentFrame

local function makeSection(text)
    local lbl = Instance.new("TextLabel")
    lbl.Size = UDim2.new(1, 0, 0, 18)
    lbl.BackgroundTransparency = 1
    lbl.Text = "  " .. text
    lbl.TextColor3 = Color3.fromRGB(100, 160, 255)
    lbl.TextSize = 11
    lbl.Font = Enum.Font.GothamBold
    lbl.TextXAlignment = Enum.TextXAlignment.Left
    lbl.Parent = ContentFrame
    return lbl
end

local function makeToggle(labelText, callback)
    local enabled = false

    local Row = Instance.new("Frame")
    Row.Size = UDim2.new(1, 0, 0, 44)
    Row.BackgroundColor3 = Color3.fromRGB(25, 18, 45)
    Row.BorderSizePixel = 0
    Row.Parent = ContentFrame

    local RowCorner = Instance.new("UICorner")
    RowCorner.CornerRadius = UDim.new(0, 8)
    RowCorner.Parent = Row

    local RowStroke = Instance.new("UIStroke")
    RowStroke.Color = Color3.fromRGB(60, 40, 100)
    RowStroke.Thickness = 1
    RowStroke.Parent = Row

    local RowLabel = Instance.new("TextLabel")
    RowLabel.Size = UDim2.new(1, -70, 1, 0)
    RowLabel.Position = UDim2.new(0, 12, 0, 0)
    RowLabel.BackgroundTransparency = 1
    RowLabel.Text = labelText
    RowLabel.TextColor3 = Color3.fromRGB(210, 200, 240)
    RowLabel.TextSize = 13
    RowLabel.Font = Enum.Font.Gotham
    RowLabel.TextXAlignment = Enum.TextXAlignment.Left
    RowLabel.Parent = Row

    local ToggleBG = Instance.new("Frame")
    ToggleBG.Size = UDim2.new(0, 44, 0, 24)
    ToggleBG.Position = UDim2.new(1, -54, 0.5, -12)
    ToggleBG.BackgroundColor3 = Color3.fromRGB(50, 40, 80)
    ToggleBG.BorderSizePixel = 0
    ToggleBG.Parent = Row

    local ToggleBGCorner = Instance.new("UICorner")
    ToggleBGCorner.CornerRadius = UDim.new(1, 0)
    ToggleBGCorner.Parent = ToggleBG

    local Knob = Instance.new("Frame")
    Knob.Size = UDim2.new(0, 18, 0, 18)
    Knob.Position = UDim2.new(0, 3, 0.5, -9)
    Knob.BackgroundColor3 = Color3.fromRGB(160, 140, 200)
    Knob.BorderSizePixel = 0
    Knob.Parent = ToggleBG

    local KnobCorner = Instance.new("UICorner")
    KnobCorner.CornerRadius = UDim.new(1, 0)
    KnobCorner.Parent = Knob

    local Button = Instance.new("TextButton")
    Button.Size = UDim2.new(1, 0, 1, 0)
    Button.BackgroundTransparency = 1
    Button.Text = ""
    Button.Parent = Row

    Button.MouseButton1Click:Connect(function()
        playClick()
        enabled = not enabled

        local targetPos = enabled and UDim2.new(1, -21, 0.5, -9) or UDim2.new(0, 3, 0.5, -9)
        local targetBG = enabled and Color3.fromRGB(80, 60, 180) or Color3.fromRGB(50, 40, 80)
        local targetKnob = enabled and Color3.fromRGB(0, 200, 230) or Color3.fromRGB(160, 140, 200)

        TweenService:Create(Knob, TweenInfo.new(0.2, Enum.EasingStyle.Quad), {Position = targetPos, BackgroundColor3 = targetKnob}):Play()
        TweenService:Create(ToggleBG, TweenInfo.new(0.2), {BackgroundColor3 = targetBG}):Play()

        if callback then callback(enabled) end
    end)

    return Row
end

local function makeDropdown(labelText, options, callback)
    local selected = options[1]

    local Container = Instance.new("Frame")
    Container.Size = UDim2.new(1, 0, 0, 44)
    Container.BackgroundColor3 = Color3.fromRGB(25, 18, 45)
    Container.BorderSizePixel = 0
    Container.ClipsDescendants = false
    Container.Parent = ContentFrame

    local ContainerCorner = Instance.new("UICorner")
    ContainerCorner.CornerRadius = UDim.new(0, 8)
    ContainerCorner.Parent = Container

    local ContainerStroke = Instance.new("UIStroke")
    ContainerStroke.Color = Color3.fromRGB(60, 40, 100)
    ContainerStroke.Thickness = 1
    ContainerStroke.Parent = Container

    local DLabel = Instance.new("TextLabel")
    DLabel.Size = UDim2.new(0.5, 0, 1, 0)
    DLabel.Position = UDim2.new(0, 12, 0, 0)
    DLabel.BackgroundTransparency = 1
    DLabel.Text = labelText
    DLabel.TextColor3 = Color3.fromRGB(210, 200, 240)
    DLabel.TextSize = 13
    DLabel.Font = Enum.Font.Gotham
    DLabel.TextXAlignment = Enum.TextXAlignment.Left
    DLabel.Parent = Container

    local DropBtn = Instance.new("TextButton")
    DropBtn.Size = UDim2.new(0, 100, 0, 28)
    DropBtn.Position = UDim2.new(1, -112, 0.5, -14)
    DropBtn.BackgroundColor3 = Color3.fromRGB(50, 35, 100)
    DropBtn.BorderSizePixel = 0
    DropBtn.Text = selected .. " v"
    DropBtn.TextColor3 = Color3.fromRGB(180, 220, 255)
    DropBtn.TextSize = 12
    DropBtn.Font = Enum.Font.GothamBold
    DropBtn.Parent = Container

    local DropBtnCorner = Instance.new("UICorner")
    DropBtnCorner.CornerRadius = UDim.new(0, 6)
    DropBtnCorner.Parent = DropBtn

    local OptionList = Instance.new("Frame")
    OptionList.Size = UDim2.new(0, 100, 0, #options * 28)
    OptionList.Position = UDim2.new(1, -112, 1, 4)
    OptionList.BackgroundColor3 = Color3.fromRGB(30, 20, 55)
    OptionList.BorderSizePixel = 0
    OptionList.Visible = false
    OptionList.ZIndex = 10
    OptionList.Parent = Container

    local OLCorner = Instance.new("UICorner")
    OLCorner.CornerRadius = UDim.new(0, 6)
    OLCorner.Parent = OptionList

    local OLStroke = Instance.new("UIStroke")
    OLStroke.Color = Color3.fromRGB(80, 60, 160)
    OLStroke.Thickness = 1
    OLStroke.Parent = OptionList

    for i, opt in ipairs(options) do
        local OptBtn = Instance.new("TextButton")
        OptBtn.Size = UDim2.new(1, 0, 0, 28)
        OptBtn.Position = UDim2.new(0, 0, 0, (i - 1) * 28)
        OptBtn.BackgroundTransparency = 1
        OptBtn.Text = opt
        OptBtn.TextColor3 = Color3.fromRGB(180, 210, 255)
        OptBtn.TextSize = 12
        OptBtn.Font = Enum.Font.Gotham
        OptBtn.ZIndex = 11
        OptBtn.Parent = OptionList

        OptBtn.MouseButton1Click:Connect(function()
            playClick()
            selected = opt
            DropBtn.Text = opt .. " v"
            OptionList.Visible = false
            if callback then callback(selected) end
        end)
    end

    DropBtn.MouseButton1Click:Connect(function()
        playClick()
        OptionList.Visible = not OptionList.Visible
    end)

    return Container
end

local function makeButton(labelText, callback)
    local Btn = Instance.new("TextButton")
    Btn.Size = UDim2.new(1, 0, 0, 40)
    Btn.BackgroundColor3 = Color3.fromRGB(50, 35, 110)
    Btn.BorderSizePixel = 0
    Btn.Text = labelText
    Btn.TextColor3 = Color3.fromRGB(200, 220, 255)
    Btn.TextSize = 13
    Btn.Font = Enum.Font.GothamBold
    Btn.Parent = ContentFrame

    local BtnGrad = Instance.new("UIGradient")
    BtnGrad.Color = ColorSequence.new({
        ColorSequenceKeypoint.new(0, Color3.fromRGB(100, 40, 180)),
        ColorSequenceKeypoint.new(1, Color3.fromRGB(20, 80, 200)),
    })
    BtnGrad.Rotation = 90
    BtnGrad.Parent = Btn

    local BtnCorner = Instance.new("UICorner")
    BtnCorner.CornerRadius = UDim.new(0, 8)
    BtnCorner.Parent = Btn

    local BtnStroke = Instance.new("UIStroke")
    BtnStroke.Color = Color3.fromRGB(80, 60, 200)
    BtnStroke.Thickness = 1
    BtnStroke.Parent = Btn

    Btn.MouseEnter:Connect(function()
        TweenService:Create(Btn, TweenInfo.new(0.15), {BackgroundColor3 = Color3.fromRGB(70, 50, 150)}):Play()
    end)
    Btn.MouseLeave:Connect(function()
        TweenService:Create(Btn, TweenInfo.new(0.15), {BackgroundColor3 = Color3.fromRGB(50, 35, 110)}):Play()
    end)
    Btn.MouseButton1Click:Connect(function()
        playClick()
        if callback then callback() end
    end)

    return Btn
end

local espEnabled = false
local espHighlights = {}

local function clearESP()
    for _, h in pairs(espHighlights) do
        if h and h.Parent then h:Destroy() end
    end
    espHighlights = {}
end

local function applyESP()
    clearESP()
    for _, obj in ipairs(workspace:GetDescendants()) do
        if obj:IsA("Model") and obj.Name == "Anomalies" then
            local highlight = Instance.new("SelectionBox")
            highlight.Color3 = Color3.fromRGB(255, 50, 50)
            highlight.LineThickness = 0.05
            highlight.SurfaceTransparency = 0.5
            highlight.SurfaceColor3 = Color3.fromRGB(255, 50, 50)
            highlight.Adornee = obj
            highlight.Parent = obj
            table.insert(espHighlights, highlight)

            local rootPart = obj:FindFirstChild("HumanoidRootPart") or obj:FindFirstChildWhichIsA("BasePart")
            if rootPart then
                local bb = Instance.new("BillboardGui")
                bb.Size = UDim2.new(0, 100, 0, 30)
                bb.AlwaysOnTop = true
                bb.StudsOffsetWorldSpace = Vector3.new(0, 3, 0)
                bb.Adornee = rootPart
                bb.Parent = obj

                local nameLabel = Instance.new("TextLabel")
                nameLabel.Size = UDim2.new(1, 0, 1, 0)
                nameLabel.BackgroundTransparency = 1
                nameLabel.Text = "Esp Cham"
                nameLabel.TextColor3 = Color3.fromRGB(255, 60, 60)
                nameLabel.TextStrokeTransparency = 0
                nameLabel.TextStrokeColor3 = Color3.fromRGB(0, 0, 0)
                nameLabel.TextSize = 14
                nameLabel.Font = Enum.Font.GothamBold
                nameLabel.Parent = bb

                table.insert(espHighlights, bb)
            end
        end
    end
end

RunService.Heartbeat:Connect(function()
    if espEnabled then
        applyESP()
    end
end)

local teleportEnabled = false

local function teleportToGuard()
    local Teams = game:GetService("Teams")
    for _, team in ipairs(Teams:GetTeams()) do
        if team.Name == "Guards" then
            for _, player in ipairs(Players:GetPlayers()) do
                if player.Team == team and player ~= LocalPlayer then
                    local char = player.Character
                    if char then
                        local root = char:FindFirstChild("HumanoidRootPart")
                        local myChar = LocalPlayer.Character
                        local myRoot = myChar and myChar:FindFirstChild("HumanoidRootPart")
                        if root and myRoot then
                            myRoot.CFrame = root.CFrame + Vector3.new(0, 3, 0)
                            return
                        end
                    end
                end
            end
        end
    end
end

makeSection("ESP")
makeToggle("Esp Cham", function(state)
    espEnabled = state
    if not state then clearESP() end
end)

makeSection("Teleport")
makeButton("Teleport To Guards", function()
    teleportToGuard()
end)
