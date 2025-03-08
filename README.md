local ScreenGui = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local UICorner = Instance.new("UICorner")
local UIStroke = Instance.new("UIStroke")
local Title = Instance.new("TextLabel")
local Button1 = Instance.new("TextButton")
local Button2 = Instance.new("TextButton")
local Button3 = Instance.new("TextButton")
local UserInputService = game:GetService("UserInputService")

-- Propriedades da ScreenGui
ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")

-- Propriedades da Frame
Frame.Parent = ScreenGui
Frame.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
Frame.Position = UDim2.new(0.5, -100, 0.5, -150)
Frame.Size = UDim2.new(0, 200, 0, 300)
Frame.Active = true
Frame.Draggable = true

-- Adicionando cantos arredondados e borda à Frame
UICorner.CornerRadius = UDim.new(0, 50)
UICorner.Parent = Frame

UIStroke.Color = Color3.fromRGB(255, 255, 255)
UIStroke.Thickness = 2
UIStroke.Parent = Frame

-- Propriedades do Title
Title.Parent = Frame
Title.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
Title.Size = UDim2.new(1, 0, 0, 50)
Title.Font = Enum.Font.SourceSansBold
Title.Text = "tubergamer (beta) (1.1)"
Title.TextColor3 = Color3.fromRGB(255, 255, 255)
Title.TextSize = 24

-- Função para estilizar botões
local function styleButton(button, text, color, posY)
    button.Parent = Frame
    button.BackgroundColor3 = color
    button.Position = UDim2.new(0, 10, 0, posY)
    button.Size = UDim2.new(1, -20, 0, 50)
    button.Text = text
    button.TextColor3 = Color3.fromRGB(255, 255, 255)
    button.Font = Enum.Font.SourceSansBold
    button.TextSize = 20
    local buttonCorner = Instance.new("UICorner")
    buttonCorner.CornerRadius = UDim.new(0, 50)
    buttonCorner.Parent = button
end

-- Propriedades do Button1
styleButton(Button1, "inf time (risk ban)", Color3.fromRGB(255, 140, 0), 70)
-- Script para o Button1 (Desconectar jogador)
Button1.MouseButton1Click:Connect(function()
    game.Players.LocalPlayer:Kick("Não está mais funcionando")
end)

-- Propriedades do Button2
styleButton(Button2, "inf parts (risk ban)", Color3.fromRGB(255, 0, 0), 140)
-- Script para o Button2
Button2.MouseButton1Click:Connect(function()
    local args = {
        [1] = 999999999999999999 -- Change here
    }
    game:GetService("ReplicatedStorage"):WaitForChild("dataTransfer"):FireServer(unpack(args))
end)

-- Propriedades do Button3
styleButton(Button3, "get all gamepass (patchet)", Color3.fromRGB(255, 0, 0), 210)
