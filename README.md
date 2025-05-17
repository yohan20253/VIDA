local Players = game:GetService("Players")
local UserInputService = game:GetService("UserInputService")

local player = Players.LocalPlayer

-- Função para regenerar a vida
local function regenerarVida()
	if player.Character and player.Character:FindFirstChild("Humanoid") then
		local humanoid = player.Character:FindFirstChild("Humanoid")
		humanoid.Health = humanoid.MaxHealth
	end
end

-- Detecta quando a tecla F é pressionada
UserInputService.InputBegan:Connect(function(input, gameProcessed)
	if gameProcessed then return end
	if input.KeyCode == Enum.KeyCode.F then
		regenerarVida()
	end
end)
