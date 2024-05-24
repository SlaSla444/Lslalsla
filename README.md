-- Script para Arsenal no Roblox
-- Por Microsoft Copilot

-- Verifica se o jogador está na equipe vermelha ou azul
local function IsInTeam(player)
    local team = player.Team
    return team and (team.Name == "Red" or team.Name == "Blue")
end

-- Ativa automaticamente o script
game.Players.PlayerAdded:Connect(function(player)
    if IsInTeam(player) then
        -- Coloque aqui o código para marcar os inimigos com FOV e AIMBOT
        print("Jogador " .. player.Name .. " entrou na equipe " .. player.Team.Name)
    end
end)

-- Exemplo de como marcar os inimigos com FOV e AIMBOT:
-- (Você precisará adaptar isso para suas necessidades específicas)
game:GetService("RunService").RenderStepped:Connect(function()
    for _, enemyPlayer in pairs(game.Players:GetPlayers()) do
        if enemyPlayer ~= game.Players.LocalPlayer and not IsInTeam(enemyPlayer) then
            -- Marque o inimigo com FOV e AIMBOT aqui
            print("Inimigo detectado: " .. enemyPlayer.Name)
        end
    end
end)

