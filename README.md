local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local humanoid = character:WaitForChild("Humanoid")
local tool = nil

-- Espera até que o jogador esteja com uma espada ou ferramenta equipada
while not tool do
    tool = character:FindFirstChildOfClass("Tool")
    wait()
end

-- Loop de ataque automático
while true do
    if tool and humanoid.Health > 0 then
        tool:Activate()
    end
    wait(0.1) -- A velocidade do ataque (quanto menor, mais rápido)
end
