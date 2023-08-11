# Strongman-Sim-Z

ROBLOX "Strongman Simulator" Script Z with LUA   |   With "Hydra Exploit UI Library" In   |   Created and Designed by  @tranquiLos
Execute The Code With Any Exploiter.





--
SCRIPT CODES





if not game:IsLoaded() then
	game.Loaded:Wait()
end
wait()
_G.On = false
_G.On2 = false
_G.auto = false
_G.multipier = 0

function RedeemCodes()
    local Codes = {
        "strongman",
        "100m",
        "Chad",
        "10m",
        "25k",
        "1500likes",
        "5000likes",
        "10000",
		"500likes"
    }
    
    for _, code in ipairs(Codes) do
        game:GetService("ReplicatedStorage").PromoCodeRequest:InvokeServer(code)
        wait(1)
    end

    return "Codes Are Injected Into Game"
end

function testinterest(part, totouch, staticnum)
    local test = part.CFrame
    part.CFrame = totouch.CFrame
    task.wait(0.2)
    part.CFrame = test
end
local HumanoidRootPart = game.Players.LocalPlayer.Character.HumanoidRootPart
local task_defer = task.defer
local pairs = pairs
local rs = game:GetService("RunService")
local area = game:GetService("Workspace").Areas["Area14_Retro"]
local fireproximityprompt = fireproximityprompt
local prox
local function GetBadges()
	for _, v in pairs(game:GetService("Workspace").BadgeColliders:GetChildren()) do
		firetouchinterest(HumanoidRootPart, v, 0)
		firetouchinterest(HumanoidRootPart, v, 1)
	end
end
local function autoworkout()
	wait(0.1)
	for i, v in pairs(game:GetService("Workspace").Areas.Area1.Gym.TrainingEquipment:GetDescendants()) do
		if v:IsA("ProximityPrompt") then
			HumanoidRootPart.CFrame = game:GetService("Workspace").Areas.Area1.Gym.TrainingEquipment.WorkoutStation.Collider.CFrame
			repeat
				wait()
				fireproximityprompt(v)
			until HumanoidRootPart.Anchored == true
		end
	end
	while _G.auto do
		task.wait()
		if not _G.multipier or _G.multipier == 0 then
			game:GetService("ReplicatedStorage").StrongMan_UpgradeStrength:InvokeServer()
		else
			game:GetService("ReplicatedStorage").StrongMan_UpgradeStrength:InvokeServer(_G.multipier)
		end
	end
end

local rs = game:GetService("RunService")
game:GetService("Workspace").PlayerDraggables[game.Players.LocalPlayer.UserId].DescendantAdded:Connect(function(added)
	if added.Name == "ExtraWeight" and _G.noweight then
		added:Destroy()
	end
end)
game:GetService("Workspace").PlayerDraggables[game.Players.LocalPlayer.UserId].DescendantAdded:Connect(function(added)
	rs.RenderStepped:Wait()
	if added:IsA("Part") and added:FindFirstChild("Coins") ~= nil then
		if not _G.On then
			return
		end
		repeat
			wait(0.1)
			firetouchinterest(added, game:GetService("Workspace").Areas["Area14_Retro"].Goal, 0)
			firetouchinterest(added, game:GetService("Workspace").Areas["Area14_Retro"].Goal, 1)
		until added == nil
	end
end)

task_defer(function()
    game:GetService("Workspace").PlayerDraggables[game.Players.LocalPlayer.UserId].DescendantAdded:Connect(function(added)
	rs.RenderStepped:Wait()
	if added:IsA("Part") and added:FindFirstChild("Coins") ~= nil then
		if not _G.On2 then
			return
		end
		repeat
			task.wait(0.1)
			testinterest(added, game:GetService("Workspace").Areas["Area14_Retro"].Goal, "static")
		until added == nil
	end
end)
end)

local oldpos = HumanoidRootPart.CFrame
HumanoidRootPart.CFrame = CFrame.new(-79.9094696, 19.8263607, 8124.82129, 1, 0, 0, 0, 1, 0, 0, 0, 1)
wait(0.25)
HumanoidRootPart.CFrame = oldpos
for _, v in pairs(area.DraggableItems:GetDescendants()) do
	if v:IsA("StringValue") and v.Name == "Title" and v.Value == "PYRAMID" then
		local part = v.Parent.InteractionPoint
		_G.Prox = v.Parent.InteractionPoint.ProximityPrompt
	end
end



local UILib = loadstring(game:HttpGet('https://raw.githubusercontent.com/StepBroFurious/Script/main/HydraHubUi.lua'))()
local Window = UILib.new("Strongman Simulator", game.Players.LocalPlayer.Name, "Kullanıcı")
local Category1 = Window:Category("Main", "http://www.roblox.com/asset/?id=8395621517")
local Category2 = Window:Category("Script", "http://www.roblox.com/asset/?id=8395621517")
local SubButton1 = Category1:Button("Auto Farming", "http://www.roblox.com/asset/?id=8395747586")
local SubButton2 = Category1:Button("Settings", "http://www.roblox.com/asset/?id=8395747586")
local SubButton3 = Category2:Button("Information", "http://www.roblox.com/asset/?id=8395747586")
local Section1 = SubButton1:Section("Farm", "Left")
local Section2 = SubButton2:Section("Humanoid Setting", "Left")
local Section3 = SubButton3:Section("Script", "Left")
local Section4 = SubButton1:Section("Codes", "Left")

Section2:Slider({Title = "Walk Speed", Description = "Setting Walkspeed For You", Default = 16, Min = 0, Max = 300}, function(value)
    game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = value
end)

Section2:Slider({Title = "Jump Power", Description = "Setting Jump Power For You", Default = 16, Min = 0, Max = 150}, function(value)
    game.Players.LocalPlayer.Character.Humanoid.JumpPower = value
end)

Section1:Toggle({Title = "Auto Farm", Description = "Auto Farming On Last Map", Default = false}, function(value)
	_G.On2 = value
	HumanoidRootPart.CFrame = CFrame.new(-79.9094696, 19.8263607, 8124.82129, 1, 0, 0, 0, 1, 0, 0, 0, 1)
	HumanoidRootPart.Anchored = false
	wait(0.1)
	task_defer(function()
		game.RunService.RenderStepped:connect(function()
			if _G.On2 then
			    workspace.Gravity = math.huge
			    HumanoidRootPart.CFrame = CFrame.new(-79.9094696, 19.8263607, 8124.82129, 1, 0, 0, 0, 1, 0, 0, 0, 1)
			    fireproximityprompt(_G.Prox, 0)
			else
			    workspace.Gravity = 196.2 
		    end
		end)
	end)
end)

Section1:Toggle({Title = "Auto Strength", Description = "Auto Strength For OutWork", Default = false}, function(value)
    _G.auto = value
    if _G.auto then
        pcall(function() game:GetService("CoreGui").PurchasePromptApp.Enabled = false end)
        task_defer(autoworkout)
    else
            pcall(function() game:GetService("CoreGui").PurchasePromptApp.Enabled = true end)
    end
end)

Section4:Button({Title = "Reedem Codes", ButtonName = "CLICK", Description = "",}, function(value)
    value = RedeemCodes()
end)

Section3:Button({Title = "Scripted For", ButtonName = "by tranquiLo", Description = "BLACKMJX",}, function(value)
    print(value)
end)
