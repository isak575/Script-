-- Script para Blox Fruits
-- Funções: Auto Farm, Auto Fruto, Auto Level Max

-- Configurações
_G.AutoFarm = true
_G.AutoFruit = true
_G.AutoLevelMax = true

-- Função de Auto Farm
function AutoFarm()
    while _G.AutoFarm do
        -- Código para auto farm
        -- Exemplo: Ataque automático em inimigos
        local player = game.Players.LocalPlayer
        local character = player.Character
        local humanoid = character:FindFirstChildOfClass("Humanoid")
        if humanoid then
            humanoid:MoveTo(Vector3.new(0, 0, 0)) -- Mova para a posição desejada
            wait(1) -- Aguarde um segundo
        end
    end
end

-- Função de Auto Fruto
function AutoFruit()
    while _G.AutoFruit do
        -- Código para auto fruto
        -- Exemplo: Coleta automática de frutas
        local fruits = game.Workspace:FindFirstChild("Fruits")
        if fruits then
            for _, fruit in pairs(fruits:GetChildren()) do
                if fruit:IsA("Part") then
                    fruit.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
                    wait(1) -- Aguarde um segundo
                end
            end
        end
    end
end

-- Função de Auto Level Max
function AutoLevelMax()
    while _G.AutoLevelMax do
        -- Código para auto level max
        -- Exemplo: Completar missões automaticamente
        local player = game.Players.LocalPlayer
        local level = player.Data.Level.Value
        if level < 1000 then -- Supondo que o nível máximo seja 1000
            -- Código para completar missões
            wait(1) -- Aguarde um segundo
        else
            _G.AutoLevelMax = false -- Pare quando atingir o nível máximo
        end
    end
end

-- Iniciar as funções
spawn(AutoFarm)
spawn(AutoFruit)
spawn(AutoLevelMax)
