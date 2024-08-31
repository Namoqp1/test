_G.Dun = true
local mobd = workspace.DunMob:GetChildren()
weapon1 = "HeavenKatana"
weapon2 = "Rumble"
_G.Weapon1 = weapon1
_G.Weapon2 = weapon2




spawn(function()
    if _G.Dun then
        while _G.Dun and task.wait() do
            for _,v in pairs(mobd) do
            if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") then
                  repeat 
                      task.wait()
                        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,-35,0) * CFrame.Angles(math.rad(90),0,0)
                  until not _G.Dun or v.Humanoid.Health <= 0
               end
            end
         end
      end
   end)




spawn(function()
    if _G.Dun then
        while _G.Dun and task.wait(.5) do
            game.Players.LocalPlayer.Character.Humanoid:EquipTool(game:GetService("Players").LocalPlayer.Backpack:FindFirstChild(weapon1))
        end
    end
end)



spawn(function()
    if _G.Dun then
        while _G.Dun and task.wait(.5) do
            game.Players.LocalPlayer.Character.Humanoid:EquipTool(game:GetService("Players").LocalPlayer.Backpack:FindFirstChild(weapon2))
        end
    end
end)



spawn(function()
    pcall(function()
        while wait() do
        if _G.Dun then
local args = {
    [1] = _G.Weapon1,
    [2] = "z"
}

game:GetService("ReplicatedStorage"):WaitForChild("Remote"):WaitForChild("Action"):FireServer(unpack(args))
end
end
end)
end)



spawn(function()
    pcall(function()
        while wait() do
        if _G.Dun then
local args = {
    [1] = _G.Weapon1,
    [2] = "v"
}

game:GetService("ReplicatedStorage"):WaitForChild("Remote"):WaitForChild("Action"):FireServer(unpack(args))
end
end
end)
end)




spawn(function()
    pcall(function()
        while wait() do
        if _G.Dun then
local args = {
    [1] = _G.Weapon2,
    [2] = "z"
}

game:GetService("ReplicatedStorage"):WaitForChild("Remote"):WaitForChild("Action"):FireServer(unpack(args))
end
end
end)
end)

