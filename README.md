local Players = game:GetService("Players")
local UserInputService = game:GetService("UserInputService")

local function createUI(player)
    local frame = Instance.new("Frame")
    frame.Size = UDim2.new(0, 300, 0, 200)
    frame.Position = UDim2.new(0, -150, 0, 20)
    frame.BackgroundColor3 = Color3.new(1, 1, 1)
    frame.BorderColor3 = Color3.new(0.25, 0.25, 0.25)
    frame.Parent = player.PlayerGui
    
    local textLabel = Instance.new("TextLabel")
    textLabel.Size = UDim2.new(0, 200, 0, 30)
    textLabel.Position = UDim2.new(0, 50, 0, 20)
    textLabel.BackgroundColor3 = Color3.new(1, 1, 1)
    textLabel.BorderColor3 = Color3.new(0.25, 0.25, 0.25)
    textLabel.Text = "Clique nos botões para interagir"
    textLabel.Parent = frame
    
    local button1 = Instance.new("TextButton")
    button1.Size = UDim2.new(0, 100, 0, 40)
    button1.Position = UDim2.new(0, 50, 0, 80)
    button1.Text = "Botão 1"
    button1.Parent = frame
    
    local function onButton1Click()
        print("Clicou no Botão 1")
    end
    button1.MouseButton1Click:Connect(onButton1Click)
    
    local button2 = Instance.new("TextButton")
    button2.Size = UDim2.new(0, 100, 0, 40)
    button2.Position = UDim2.new(0, 160, 0, 80)
    button2.Text = "Botão 2"
    button2.Parent = frame
    
    local function onButton2Click()
        print("Clicou no Botão 2")
    end
    button2.MouseButton1Click:Connect(onButton2Click)
end

Players.PlayerAdded:Connect(function(player)
    createUI(player)
end)

RunService.Heartbeat:Connect(function()
    for _, player in ipairs(Players:GetPlayers()) do
        createUI(player)
    end
end)
