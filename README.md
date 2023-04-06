local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/shlexware/Orion/main/source')))()
local Window = OrionLib:MakeWindow({Name = "AutoFarmOPL", HidePremium = false, SaveConfig = true, ConfigFolder = "OrionTest"})

local Tab = Window:MakeTab({
	Name = "Auto Farm Beri",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})

local Section = Tab:AddSection({
	Name = "Player 1"
})

OrionLib:MakeNotification({
	Name = "Title!",
	Content = "Notification content... what will it say??",
	Image = "rbxassetid://4483345998",
	Time = 5
})

Tab:AddButton({
	Name = "Set Position",
	Callback = function()
game.Workspace.Spawns.Spawn1.CFrame = CFrame.new(-1558, 215, 9935)
game.Workspace.Spawns.Spawn2.CFrame = CFrame.new(-1558, 215, 9935)
game.Workspace.Spawns.Spawn3.CFrame = CFrame.new(-1558, 215, 9935)
game.Workspace.Spawns.Spawn10.CFrame = CFrame.new(-1558, 215, 9935)
game.Workspace.Spawns.Spawn4.CFrame = CFrame.new(-1558, 215, 9935)
game.Workspace.Spawns.Spawn5.CFrame = CFrame.new(-1558, 215, 9935)
game.Workspace.Spawns.Spawn6.CFrame = CFrame.new(-1558, 215, 9935)
game.Workspace.Spawns.Spawn7.CFrame = CFrame.new(-1558, 215, 9935)
game.Workspace.Spawns.Spawn8.CFrame = CFrame.new(-1558, 215, 9935)
game.Workspace.Spawns.Spawn9.CFrame = CFrame.new(-1558, 215, 9935)
  	end    
})

Tab:AddToggle({
	Name = "Start Autodei",
	Default = false,
	Callback = function(Value)
	AuTODie = Value 
	if Value then
for _ = 1, 12 do
            game.Players.LocalPlayer.Character.Drown:FireServer("NOPLS");
        end
    end
	end    
})



spawn(function()
    while wait() do
        pcall(function()
            if not AuTODie or not game.Players.LocalPlayer.PlayerGui.Load.Frame.Visible then return end;
            wait(3);
            firesignal(game.Players.LocalPlayer.PlayerGui.Load.Frame.Load.MouseButton1Click);
            repeat wait() until not game.Players.LocalPlayer.PlayerGui.Load.Frame.Visible;
            wait(3);
            repeat
                game.Players.LocalPlayer.Character.Drown:FireServer("NOPLS");
                wait(0.1);
            until game.Players.LocalPlayer.PlayerGui.Load.Frame.Visible;
        end)
    end
end);

local Section2 = Tab:AddSection({
	Name = "Player 2"
})

Tab:AddButton({
	Name = "TP",
	Callback = function()
      		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1558, 215, 9935);
  	end    
})
