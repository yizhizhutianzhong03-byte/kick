-- Self Kick Hub (LocalScript)
local player = game.Players.LocalPlayer
local playerGui = player:WaitForChild("PlayerGui")
-- ScreenGui
local screenGui = Instance.new("ScreenGui")
screenGui.Name = "SelfKickHub"
screenGui.ResetOnSpawn = false
screenGui.Parent = playerGui
-- Main Frame
local mainFrame = Instance.new("Frame")
mainFrame.Size = UDim2.new(0, 350, 0, 220)
mainFrame.Position = UDim2.new(0.5, 0, 0.5, 0)
mainFrame.AnchorPoint = Vector2.new(0.5, 0.5)
mainFrame.BackgroundColor3 = Color3.fromRGB(28, 28, 32)
mainFrame.BorderSizePixel = 0
mainFrame.Active = true
mainFrame.Draggable = true
mainFrame.Parent = screenGui
-- Corner
local corner = Instance.new("UICorner")
corner.CornerRadius = UDim.new(0, 16)
corner.Parent = mainFrame
-- Title
local title = Instance.new("TextLabel")
title.Size = UDim2.new(1, -60, 0, 40)
title.Position = UDim2.new(0, 14, 0, 10)
title.BackgroundTransparency = 1
title.Text = "Kick Hub"
title.TextColor3 = Color3.fromRGB(240, 240, 240)
title.Font = Enum.Font.GothamBold
title.TextSize = 22
title.TextXAlignment = Enum.TextXAlignment.Left
title.Parent = mainFrame
-- Close Button (×)
local closeButton = Instance.new("TextButton")
closeButton.Size = UDim2.new(0, 32, 0, 32)
closeButton.Position = UDim2.new(1, -44, 0, 10)
closeButton.BackgroundColor3 = Color3.fromRGB(220, 70, 70)
closeButton.Text = "×"
closeButton.TextColor3 = Color3.new(1,1,1)
closeButton.Font = Enum.Font.GothamBold
closeButton.TextSize = 20
closeButton.BorderSizePixel = 0
closeButton.Parent = mainFrame
local closeCorner = Instance.new("UICorner")
closeCorner.CornerRadius = UDim.new(0, 8)
closeCorner.Parent = closeButton
closeButton.MouseButton1Click:Connect(function()
screenGui:Destroy()
end)
-- Kick Button (Self)
local kickButton = Instance.new("TextButton")
kickButton.Size = UDim2.new(0, 220, 0, 54)
kickButton.Position = UDim2.new(0.5, 0, 0.55, 0)
kickButton.AnchorPoint = Vector2.new(0.5, 0.5)
kickButton.BackgroundColor3 = Color3.fromRGB(255, 85, 85)
kickButton.Text = "Kick Me"
kickButton.TextColor3 = Color3.new(1,1,1)
kickButton.Font = Enum.Font.GothamBold
kickButton.TextSize = 20
kickButton.BorderSizePixel = 0
kickButton.Parent = mainFrame
local kickCorner = Instance.new("UICorner")
kickCorner.CornerRadius = UDim.new(0, 12)
kickCorner.Parent = kickButton
-- Self Kick
kickButton.MouseButton1Click:Connect(function()
player:Kick("Kicked by Kick Hub")
end)
