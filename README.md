local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/shlexware/Orion/main/source')))()
local Window = OrionLib:MakeWindow({Name = "AutoFarmOPL", HidePremium = false, SaveConfig = true, ConfigFolder = "OrionTest"})

local Cache = { DevConfig = {} };

Cache.DevConfig["ListOfBox"] = {"Common Box", "Uncommon Box", "Rare Box", "Ultra Rare Box"};
Cache.DevConfig["ListOfDrink"] = {"Cider+", "Lemonade+", "Juice+", "Smoothie+"};
Cache.DevConfig["ListOfDrinkFormMixer"] = {"Cider", "Lemonade", "Juice", "Smoothie", "Milk", "Golden Apple"};




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
game.Workspace.Spawns.Spawn4.CFrame = CFrame.new(-1558, 215, 9935)
game.Workspace.Spawns.Spawn5.CFrame = CFrame.new(-1558, 215, 9935)
game.Workspace.Spawns.Spawn6.CFrame = CFrame.new(-1558, 215, 9935)
game.Workspace.Spawns.Spawn7.CFrame = CFrame.new(-1558, 215, 9935)
game.Workspace.Spawns.Spawn8.CFrame = CFrame.new(-1558, 215, 9935)
game.Workspace.Spawns.Spawn9.CFrame = CFrame.new(-1558, 215, 9935)
game.Workspace.Spawns.Spawn10.CFrame = CFrame.new(-1558, 215, 9935)

  	end    
})

Tab:AddButton({
	Name = "Set Position(เลือกที่เกิดเอง)",
	Callback = function()
local Content = game.Players.LocalPlayer.Character.HumanoidRootPart.Position;
    

game.Workspace.Spawns.Spawn1.CFrame = CFrame.new(Content)
game.Workspace.Spawns.Spawn2.CFrame = CFrame.new(Content)
game.Workspace.Spawns.Spawn3.CFrame = CFrame.new(Content)
game.Workspace.Spawns.Spawn4.CFrame = CFrame.new(Content)
game.Workspace.Spawns.Spawn5.CFrame = CFrame.new(Content)
game.Workspace.Spawns.Spawn6.CFrame = CFrame.new(Content)
game.Workspace.Spawns.Spawn7.CFrame = CFrame.new(Content)
game.Workspace.Spawns.Spawn8.CFrame = CFrame.new(Content)
game.Workspace.Spawns.Spawn9.CFrame = CFrame.new(Content)
game.Workspace.Spawns.Spawn10.CFrame = CFrame.new(Content)

  	end    
})

Tab:AddButton({
	Name = "Reset Position",
	Callback = function()
game.Workspace.Spawns.Spawn1.CFrame = CFrame.new(-8, 213.710159, -296)
game.Workspace.Spawns.Spawn2.CFrame = CFrame.new(-128, 213.710159, -753)
game.Workspace.Spawns.Spawn3.CFrame = CFrame.new(45, 221.710159, -72)
game.Workspace.Spawns.Spawn4.CFrame = CFrame.new(-237, 222.710159, -1108)
game.Workspace.Spawns.Spawn5.CFrame = CFrame.new(-206, 221.710159, -110.5)
game.Workspace.Spawns.Spawn6.CFrame = CFrame.new(-76, 212.710159, -892)
game.Workspace.Spawns.Spawn7.CFrame = CFrame.new(-428, 213.710159, -154)
game.Workspace.Spawns.Spawn8.CFrame = CFrame.new(-127, 217, -983.200012)
game.Workspace.Spawns.Spawn9.CFrame = CFrame.new(720, 237, 1191.80005)
game.Workspace.Spawns.Spawn10.CFrame = CFrame.new(-1281.5, 213.710159, -1353)

  	end    
})

Tab:AddToggle({
	Name = "Start Autodie",
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
	Name = "Save Zone",
	Callback = function()
      		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(Vector3.new(100000, 3500, 80000));
    local Base = Instance.new("Part", game.Workspace);
    Base.Size = Vector3.new(50, 1, 50);
    Base.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame + Vector3.new(0, -3, 0);
    Base.Anchored = true;
  	end    
})

players = {}

for i,v in pairs(game:GetService("Players"):GetChildren()) do

   table.insert(players,v.Name)

end

Tab:AddDropdown({
	Name = "Select Player",
	Default = "",
	Options = players,
	Callback = function(SelectPlayer)
		Select = SelectPlayer
	end    
})



Tab:AddButton({
	Name = "Teleport To Player",
	Callback = function()
      		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Players[Select].Character.HumanoidRootPart.CFrame
  	end    
})

Tab:AddToggle({
	Name = "Auto Teleport",
	Default = false,
	Callback = function(ATP)
		AutoTeleport = ATP
	end    
})

spawn(function()

while wait() do

if AutoTeleport then

pcall(function()

game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Players[Select].Character.HumanoidRootPart.CFrame * CFrame.new(0,30,0)

end)

end

end

end)


Tab:AddToggle({
	Name = "Bring Player",
	Default = false,
	Callback = function(BP)
		BringPlayer = BP
	end    
})

spawn(function()

while wait() do

if BringPlayer then

pcall(function()

game.Players[Select].Character.HumanoidRootPart.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame * CFrame.new(0,0,-3)

end)

end

end

end)
--------------------------------------
local Tab2 = Window:MakeTab({
	Name = "Auto Quest",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})



local Section = Tab2:AddSection({
	Name = "Auto Compass"
})

Tab2:AddToggle({
	Name = "Auto Sam Quest",
	Default = false,
	Callback = function(ASQ)
		AutoSamQuest = ASQ
	end    
})

spawn(function()
    while wait() do
        pcall(function()
            if not AutoSamQuest then return end;
            game.Workspace.Merchants.QuestMerchant.Clickable.Retum:FireServer("Claim1");
        end)
    end
end);


Tab2:AddToggle({
	Name = "Auto Compass Quest",
	Default = false,
	Callback = function(ASQ)
		AutoCompassQuest = ASQ
	end    
})

spawn(function()
    while wait() do
        pcall(function()
            if not AutoCompassQuest then return end;
            local Compass = game.Players.LocalPlayer.Backpack:FindFirstChild("Compass");
            local Compass2 = game.Players.LocalPlayer.Character:FindFirstChild("Compass");
            if Compass or Compass2 then
                local OldPostiton = game.Players.LocalPlayer.Character.HumanoidRootPart.Position;
                game.Players.LocalPlayer.Character.Humanoid:UnequipTools();
                Compass.Parent = game.Players.LocalPlayer.Character;
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(Compass.Poser.Value);
                Compass:Activate();
                wait(1);
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(OldPostiton);
            end
        end)
    end
end);

Tab2:AddToggle({
	Name = "Auto Unbox Box",
	Default = false,
	Callback = function(AUB)
		AutoUnboxBox = AUB
	end    
})


spawn(function()
    while wait() do
        pcall(function()
            if not AutoUnboxBox then return end;
            for _, Value in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
                if table.find(Cache.DevConfig["ListOfBox"], Value.Name) then
                    game.Players.LocalPlayer.Character.Humanoid:UnequipTools();
                    Value.Parent = game.Players.LocalPlayer.Character;
                    Value:Activate();
                end
            end
        end)
    end
end);


local Section = Tab2:AddSection({
	Name = "Drink"
})




local Cache = { DevConfig = {} };

Cache.DevConfig["ListOfDrink"] = {"Cider+", "Lemonade+", "Juice+", "Smoothie+"};
Cache.DevConfig["ListOfDrinkFormMixer"] = {"Cider", "Lemonade", "Juice", "Smoothie", "Milk", "Golden Apple"};



Tab2:AddDropdown({
	Name = "Select Drink",
	Default = "",
	Options = Cache.DevConfig["ListOfDrink"],
	Callback = function(SD)
		SelectDrink = SD
	end    
})

Tab2:AddTextbox({
	Name = "Amount Drink",
	Default = "1",
	TextDisappear = true,
	Callback = function(AD)
		AmountDrink = AD
	end	  
})

Tab2:AddButton({
	Name = "Buy Drink",
	Callback = function()
        if not AmountDrink or not string.match(AmountDrink, "%d+") or tonumber(string.match(AmountDrink, "%d+")) < 0 then return end;
        for _ = 1, tonumber(string.match(AmountDrink, "%d+")) do
            game.Workspace.Merchants.BetterDrinkMerchant.Clickable.Retum:FireServer(SelectDrink)
        end
  	end    
})

Tab2:AddToggle({
	Name = "Auto Drink",
	Default = false,
	Callback = function(ADK)
		AutoDrink = ADK
	end    
})

spawn(function()
    while wait() do
        pcall(function()
            if not AutoDrink then return end;
            for _, Value in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
                if table.find(Cache.DevConfig["ListOfDrink"], Value.Name) then
                    game.Players.LocalPlayer.Character.Humanoid:UnequipTools();
                    Value.Parent = game.Players.LocalPlayer.Character;
                    Value:Activate();
                end
            end
        end)
    end
end);

Tab2:AddToggle({
	Name = "Auto Drop Drink",
	Default = false,
	Callback = function(ADD)
		AutoDropDrink = ADD
	end    
})

spawn(function()
    while wait() do
        pcall(function()
            if not AutoDropDrink then return end;
            for _, Value in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
                if table.find(Cache.DevConfig["ListOfDrink"], Value.Name) then
                    game.Players.LocalPlayer.Character.Humanoid:UnequipTools();
                    Value.Parent = game.Players.LocalPlayer.Character;
                    Value.Parent = game.Workspace;
                end
            end
        end)
    end
end);

--------------------------------------

local Tab3 = Window:MakeTab({
	Name = "setting",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})

local Section = Tab3:AddSection({
	Name = "Hit Box"
})

Tab3:AddTextbox({
	Name = "Hit Box Size",
	Default = "",
	TextDisappear = true,
	Callback = function(HBZ)
		HitBoxSIZE = HBZ
	end	  
})

Tab3:AddToggle({
	Name = "Start Hit Box",
	Default = false,
	Callback = function(HP)
		HITBOXEIEI = HP
	end    
})


spawn(function()
    while wait() do
        pcall(function()
            if not HITBOXEIEI then return end;
            local HitBox = HitBoxSIZE
            for _, v in pairs(game.Players:GetChildren()) do
                if v.Character:FindFirstChild("HumanoidRootPart") and v.Name ~= game.Players.LocalPlayer.Name then
                    v.Character.HumanoidRootPart.Size = Vector3.new(HitBox, HitBox, HitBox);
                    v.Character.HumanoidRootPart.Transparency = 0.9;
                    v.Character.HumanoidRootPart.BrickColor = BrickColor.new("Really blue");
                    v.Character.HumanoidRootPart.Material = "Neon";
                    v.Character.HumanoidRootPart.CanCollide = false;
                end
            end
        end)
    end
end)

local Section = Tab3:AddSection({
	Name = "Auto Attack"
})


Tab3:AddTextbox({
	Name = "Weapon Name",
	Default = "",
	TextDisappear = true,
	Callback = function(WPN)
		WeaponName = WPN
	end	  
})

local value = WeaponName;
while wait(3) do
	if value ~= WeaponName then
		value = WeaponName;
	else
		break;
	end
end;
for _, Value in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
	if Value.ClassName == "Tool" and string.match(string.lower(Value.Name), string.lower(value)) then
		return [WeaponName]:SetValue(Value.Name);
	end
end;
for _, Value in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
	if Value.ClassName == "Tool" and string.match(string.lower(Value.Name), string.lower(value)) then
		return [WeaponName]:SetValue(Value.Name);
	end
end;

Tab3:AddToggle({
	Name = "Equip Weapon",
	Default = false,
	Callback = function(EQW)
		EquipWeapon = EQW
	end    
})

spawn(function()
    while wait() do
        pcall(function()
            if not EquipWeapon or not game.Players.LocalPlayer.Backpack:FindFirstChild(WeaponName) then return end;
            if game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool") and game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool").Name ~= WeaponName then
                game.Players.LocalPlayer.Character.Humanoid:UnequipTools();
            end
            game.Players.LocalPlayer.Backpack[WeaponName].Parent = game.Players.LocalPlayer.Character;
        end)
    end
end);

Tab3:AddToggle({
	Name = "Activate Weapon",
	Default = false,
	Callback = function(ATW)
		ActivateWeapon = ATW
	end    
})

spawn(function()
    while wait() do
        pcall(function()
            if not ActivateWeapon or not game.Players.LocalPlayer.Character:FindFirstChild(WeaponName) then return end;
            game.Players.LocalPlayer.Character[WeaponName]:Activate();
        end)
    end
end);

Tab3:AddToggle({
	Name = "Click On Screen",
	Default = false,
	Callback = function(COS)
		ClickOnScreenEE = COS
	end    
})

spawn(function()
    while wait() do
        pcall(function()
            if not ClickOnScreenEE then return end;
            game:GetService("VirtualUser"):ClickButton1(Vector2.new(99999, 99999));
        end)
    end
end);


local Section = Tab3:AddSection({
	Name = "Other"
})

Tab3:AddToggle({
	Name = "Auto Spawn When Dead",
	Default = false,
	Callback = function(ASWD)
		AutoSpawnWhenDead = ASWD
	end    
})

spawn(function()
    while wait() do
        pcall(function()
            if not AutoSpawnWhenDead or not game.Players.LocalPlayer.PlayerGui.Load.Frame.Visible then return end;
            wait(3);
            firesignal(game.Players.LocalPlayer.PlayerGui.Load.Frame.Load.MouseButton1Click);
        end)
    end
end);

Tab3:AddToggle({
	Name = "Auto Rejoin When Disconnect",
	Default = false,
	Callback = function(ARWD)
		AutoRejounWhenDisconnect = ARWD
	end    
})

spawn(function()
	if AutoRejounWhenDisconnect then
		repeat wait() until game:GetService("CoreGui"):FindFirstChild("promptOverlay", true) and game:GetService("CoreGui"):FindFirstChild("promptOverlay", true):FindFirstChild("ErrorPrompt");
		repeat
			game:GetService("TeleportService"):Teleport(game.PlaceId);
			wait(5);
 	until not game.Players;
	end
end)



-----------------------------------

local Tab4 = Window:MakeTab({
	Name = "Credit",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})

local Section = Tab4:AddSection({
	Name = "by peet😎"
})

local Section = Tab4:AddSection({
	Name = "พี่มาคกาก"
})

local Section = Tab4:AddSection({
	Name = "พี่เตอร์แก่"
})

local Section = Tab4:AddSection({
	Name = "Copy kang kung"
})
