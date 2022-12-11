-- Gui to Lua
-- Version: 3.2

-- Instances:

local ScreenGui = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local UICorner = Instance.new("UICorner")
local P90AutoFarm = Instance.new("TextButton")
local buttonCorner = Instance.new("UICorner")
local ShotGUnAutofarm = Instance.new("TextButton")
local buttonCorner_2 = Instance.new("UICorner")
local GlockAutofarm = Instance.new("TextButton")
local buttonCorner_3 = Instance.new("UICorner")
local SMGAutoFarm = Instance.new("TextButton")
local buttonCorner_4 = Instance.new("UICorner")

--Properties:

ScreenGui.Parent = game.CoreGui
ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

Frame.Parent = ScreenGui
Frame.BackgroundColor3 = Color3.fromRGB(45, 48, 53)
Frame.BorderSizePixel = 0
Frame.Position = UDim2.new(0.316494167, 0, 0.516826928, 0)
Frame.Size = UDim2.new(0, 347, 0, 290)

UICorner.Parent = Frame

P90AutoFarm.Name = "P90 AutoFarm"
P90AutoFarm.Parent = Frame
P90AutoFarm.BackgroundColor3 = Color3.fromRGB(157, 150, 66)
P90AutoFarm.Position = UDim2.new(0.0299186595, 0, 0.0633057728, 0)
P90AutoFarm.Size = UDim2.new(0, 325, 0, 32)
P90AutoFarm.AutoButtonColor = false
P90AutoFarm.Font = Enum.Font.Gotham
P90AutoFarm.Text = "P90 AutoFarm"
P90AutoFarm.TextColor3 = Color3.fromRGB(255, 255, 255)
P90AutoFarm.TextSize = 14.000

buttonCorner.CornerRadius = UDim.new(0, 3)
buttonCorner.Name = "buttonCorner"
buttonCorner.Parent = P90AutoFarm

ShotGUnAutofarm.Name = "ShotGUn Autofarm"
ShotGUnAutofarm.Parent = Frame
ShotGUnAutofarm.BackgroundColor3 = Color3.fromRGB(157, 150, 66)
ShotGUnAutofarm.Position = UDim2.new(0.0299186595, 0, 0.211581647, 0)
ShotGUnAutofarm.Size = UDim2.new(0, 325, 0, 32)
ShotGUnAutofarm.AutoButtonColor = false
ShotGUnAutofarm.Font = Enum.Font.Gotham
ShotGUnAutofarm.Text = "ShotGun Autofarm"
ShotGUnAutofarm.TextColor3 = Color3.fromRGB(255, 255, 255)
ShotGUnAutofarm.TextSize = 14.000

buttonCorner_2.CornerRadius = UDim.new(0, 3)
buttonCorner_2.Name = "buttonCorner"
buttonCorner_2.Parent = ShotGUnAutofarm

GlockAutofarm.Name = "Glock Autofarm"
GlockAutofarm.Parent = Frame
GlockAutofarm.BackgroundColor3 = Color3.fromRGB(157, 150, 66)
GlockAutofarm.Position = UDim2.new(0.0299186595, 0, 0.377098888, 0)
GlockAutofarm.Size = UDim2.new(0, 325, 0, 32)
GlockAutofarm.AutoButtonColor = false
GlockAutofarm.Font = Enum.Font.Gotham
GlockAutofarm.Text = "Glock Autofarm"
GlockAutofarm.TextColor3 = Color3.fromRGB(255, 255, 255)
GlockAutofarm.TextSize = 14.000

buttonCorner_3.CornerRadius = UDim.new(0, 3)
buttonCorner_3.Name = "buttonCorner"
buttonCorner_3.Parent = GlockAutofarm

SMGAutoFarm.Name = "SMG AutoFarm"
SMGAutoFarm.Parent = Frame
SMGAutoFarm.BackgroundColor3 = Color3.fromRGB(157, 150, 66)
SMGAutoFarm.Position = UDim2.new(0.0299186595, 0, 0.539167881, 0)
SMGAutoFarm.Size = UDim2.new(0, 325, 0, 32)
SMGAutoFarm.AutoButtonColor = false
SMGAutoFarm.Font = Enum.Font.Gotham
SMGAutoFarm.Text = "SMG AutoFarm"
SMGAutoFarm.TextColor3 = Color3.fromRGB(255, 255, 255)
SMGAutoFarm.TextSize = 14.000

buttonCorner_4.CornerRadius = UDim.new(0, 3)
buttonCorner_4.Name = "buttonCorner"
buttonCorner_4.Parent = SMGAutoFarm

-- Scripts:

local function AXRV_fake_script() -- P90AutoFarm.LocalScript 
	local script = Instance.new('LocalScript', P90AutoFarm)

	script.Parent.MouseButton1Click:Connect(function()
		repeat
			wait()
		until game:IsLoaded()
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(465.91626, 48.0685081, -622.589539)
		fireclickdetector(game:GetService("Workspace").Ignored.Shop["[P90] - $1000"].ClickDetector)
		wait(1)
		fireclickdetector(game:GetService("Workspace").Ignored.Shop["[P90] - $1000"].ClickDetector)
		wait(1)
		fireclickdetector(game:GetService("Workspace").Ignored.Shop["[P90] - $1000"].ClickDetector)
	
		if workspace.Players[game.Players.LocalPlayer.Name]:FindFirstChild("[P90]") then
			workspace.Players[game.Players.LocalPlayer.Name]:FindFirstChild("[P90]").Name = "[P900]"
		else
			game.Players.LocalPlayer.Backpack["[P90]"].Parent = workspace.Players[game.Players.LocalPlayer.Name]
			game.workspace.Players[game.Players.LocalPlayer.Name]:FindFirstChild("[P90]").Name = "[P900]"
		end
	
		function Buy()
			fireclickdetector(workspace.Ignored.Shop["120 [P90 Ammo] - $60"].ClickDetector)
		end
	
		local timer = 0
		local ATM = "nil"
		local GetAmmoOrReload = false
		local Cash = false
	
		function GetCash()
			for i, v in pairs(workspace.Ignored.Drop:GetChildren()) do
				if
					v.Name == "MoneyDrop" and
					(workspace.Players[game.Players.LocalPlayer.Name].HumanoidRootPart.Position - v.Position).Magnitude < 12
				then
					Cash = true
					fireclickdetector(v.ClickDetector)
					wait(1)
					Cash = false
				end
			end
		end
	
		function getATM()
			for i, v in pairs(workspace.Cashiers:GetChildren()) do
				if v:WaitForChild("Humanoid").Health > 0 then
					local cf = v.Head.CFrame
					local lv = cf.lookVector
					game.workspace.Players[game.Players.LocalPlayer.Name].HumanoidRootPart.CFrame =
						cf + (lv * Vector3.new(0, 0, -3))
					game.ReplicatedStorage.MainEvent:FireServer("UpdateMousePos", v.Head.Position)
					return v
				end
			end
		end
	
		ATM = getATM()
	
		function reload(name, gun)
			local A_1 = "Reload"
			local A_2 = game:GetService("Workspace").Players[name][gun]
			local Event = game:GetService("ReplicatedStorage").MainEvent
			Event:FireServer(A_1, A_2)
		end
	
		game:GetService("RunService").Heartbeat:Connect(
		function()
			GetCash()
			game.Players.LocalPlayer.Character.Humanoid:ChangeState(11)
			if timer == 0 and Cash == false then
				if game.Players.LocalPlayer.DataFolder.Inventory["[P90]"].Value == "0" and GetAmmoOrReload == false then
					timer = 10
					GetAmmoOrReload = true
					local part = workspace.Ignored.Shop["120 [P90 Ammo] - $60"].Head
					game.workspace.Players[game.Players.LocalPlayer.Name].HumanoidRootPart.CFrame =
						CFrame.new(part.CFrame.X, part.CFrame.Y + 4, part.CFrame.Z)
					game.workspace.Players[game.Players.LocalPlayer.Name]["[P900]"].Parent =
						game.Players.LocalPlayer.Backpack
					wait(2)
					for i = 1, 10 do
						game.workspace.Players[game.Players.LocalPlayer.Name].HumanoidRootPart.CFrame =
							CFrame.new(
								part.CFrame.X + math.random(1, 2),
								part.CFrame.Y + math.random(1, 2),
								part.CFrame.Z + math.random(1, 2)
							)
						print "e"
						Buy()
						wait(1)
					end
					game.Players.LocalPlayer.Backpack["[P900]"].Parent =
						game.workspace.Players[game.Players.LocalPlayer.Name]
					timer = 0
					GetAmmoOrReload = false
					local cf = ATM.Head.CFrame
					local lv = cf.lookVector
					game.workspace.Players[game.Players.LocalPlayer.Name].HumanoidRootPart.CFrame =
						cf + (lv * Vector3.new(0, 0, -3))
				end
				if
					game.workspace.Players[game.Players.LocalPlayer.Name]:WaitForChild("[P900]").Ammo.Value == 0 and
					GetAmmoOrReload == false
				then
					GetAmmoOrReload = true
					reload(game.Players.LocalPlayer.Name, "[P900]")
					wait(2)
					GetAmmoOrReload = false
				else
					for i, v in pairs(workspace.Cashiers:GetChildren()) do
						if v:WaitForChild("Humanoid").Health > 0 then
							if GetAmmoOrReload == false then
								if ATM.Humanoid.Health > 0 then
									game:GetService("VirtualUser"):Button1Down(Vector2.new(0, 0, 0))
									local cf = ATM.Head.CFrame
									local lv = cf.lookVector
									game.workspace.Players[game.Players.LocalPlayer.Name].HumanoidRootPart.CFrame =
										cf + (lv * Vector3.new(0, 0, -3))
								end
							end
						end
					end
				end
				for i, v in pairs(workspace.Cashiers:GetChildren()) do
					if v:WaitForChild("Humanoid").Health > 0 then
						if ATM.Humanoid.Health < 0 and GetAmmoOrReload == false then
							timer = 10
							wait(0.1)
							if GetAmmoOrReload == false then
								local cf = ATM.Head.CFrame
								local lv = cf.lookVector
								game.workspace.Players[game.Players.LocalPlayer.Name].HumanoidRootPart.CFrame =
									cf + (lv * Vector3.new(0, 0, -3))
	
								ATM = getATM()
							end
							timer = 0
						end
					end
				end
			end
		end)
	end)
end
coroutine.wrap(AXRV_fake_script)()
local function RGLI_fake_script() -- ShotGUnAutofarm.LocalScript 
	local script = Instance.new('LocalScript', ShotGUnAutofarm)

	script.Parent.MouseButton1Click:Connect(function()
		if game.Players.LocalPlayer.Character.Animate:FindFirstChild("idle") then
			game.Players.LocalPlayer.Character.Animate.idle:Destroy()
		end
		local me = game:service'Players'.LocalPlayer
		local plr = game.Players.LocalPlayer
		local savedarmourpos = plr.Character.HumanoidRootPart.Position
		local toolname = "[Shotgun] - $1250"
		plr.Character.HumanoidRootPart.CFrame = CFrame.new(game.Workspace.Ignored.Shop[toolname].Head.Position)
		wait(.1)
		fireclickdetector(game.Workspace.Ignored.Shop[toolname].ClickDetector)
		wait(.1)
		fireclickdetector(game.Workspace.Ignored.Shop[toolname].ClickDetector)
		wait(.1)
		fireclickdetector(game.Workspace.Ignored.Shop[toolname].ClickDetector)
		wait(.1)
		fireclickdetector(game.Workspace.Ignored.Shop[toolname].ClickDetector)
		wait(.1)
		fireclickdetector(game.Workspace.Ignored.Shop[toolname].ClickDetector)
		wait(.1)
		fireclickdetector(game.Workspace.Ignored.Shop[toolname].ClickDetector)
		wait(.1)
		me.Character.Humanoid:EquipTool(me.Backpack:FindFirstChild("[Shotgun]"))
		wait(0.001)
		plr.Character.HumanoidRootPart.CFrame = CFrame.new(savedarmourpos)
		plr.Character.HumanoidRootPart.CFrame = CFrame.new(savedarmourpos)
		function bypass()
			local oh1 = CFrame.new(169.126266, -121.450089, 182.002182)
			local oh2 = game:GetService("Players")
			local oh3 = oh2.LocalPlayer.Character.HumanoidRootPart
	
	
			oh3.CFrame = oh1
			wait(1.5)
		end
		repeat
			wait()
		until game:IsLoaded()
	
		if workspace.Players[game.Players.LocalPlayer.Name]:FindFirstChild("[Shotgun]") then
			workspace.Players[game.Players.LocalPlayer.Name]:FindFirstChild("[Shotgun]").Name = "[Drxco]"
	
			function Buy()
				fireclickdetector(workspace.Ignored.Shop["20 [Shotgun Ammo] - $60"].ClickDetector)
				fireclickdetector(workspace.Ignored.Shop["20 [Shotgun Ammo] - $60"].ClickDetector)
			end
	
			local ATM = "nil"
			local idk = false
			local dineros = false
			local lol = 0
	
			function GetATM()
				bypass()
				for i, v in pairs(workspace.Cashiers:GetChildren()) do
					if v:WaitForChild("Humanoid").Health > 0 then
						local cf = v.Open.CFrame
						local lv = cf.lookVector
						game.workspace.Players[game.Players.LocalPlayer.Name].HumanoidRootPart.CFrame = cf + (lv * Vector3.new(0, 0, -2))
						game.ReplicatedStorage.MainEvent:FireServer("UpdateMousePos", v.Open.Position)
						return v
					end
				end
			end
	
			function GETMONEY()
				for i, v in pairs(workspace.Ignored.Drop:GetChildren()) do
					if v.Name == "MoneyDrop" and (workspace.Players[game.Players.LocalPlayer.Name].HumanoidRootPart.Position - v.Position).Magnitude < 25
					then
						dineros = true
						fireclickdetector(v.ClickDetector)
						wait(0.7)
						dineros = false
					end
				end
			end
	
			ATM = GetATM()
	
			function reload(name, gun)
				local XD1 = "Reload"
				local XD2 = game:GetService("Workspace").Players[name][gun]
				local Event = game:GetService("ReplicatedStorage").MainEvent
				Event:FireServer(XD1, XD2)
			end
			game:GetService("RunService").Heartbeat:Connect(function()
				GETMONEY()
				game.Players.LocalPlayer.Character.Humanoid:ChangeState(11)
				if lol == 0 and dineros == false then
					if game.Players.LocalPlayer.DataFolder.Inventory["[Shotgun]"].Value == "0" and idk == false then
						lol = 10
						idk = true
						local part = workspace.Ignored.Shop["20 [Shotgun Ammo] - $60"].Head
						game.workspace.Players[game.Players.LocalPlayer.Name].HumanoidRootPart.CFrame =
							CFrame.new(part.CFrame.X, part.CFrame.Y + 4, part.CFrame.Z)
						game.workspace.Players[game.Players.LocalPlayer.Name]["[Drxco]"].Parent =
							game.Players.LocalPlayer.Backpack
						wait(2)
						for i = 1, 10 do
							game.workspace.Players[game.Players.LocalPlayer.Name].HumanoidRootPart.CFrame =
								CFrame.new(
									part.CFrame.X + math.random(1, 2),
									part.CFrame.Y + math.random(1, 2),
									part.CFrame.Z + math.random(1, 2)
								)
							Buy()
							wait(0.5)
						end
						game.Players.LocalPlayer.Backpack["[Drxco]"].Parent =
							game.workspace.Players[game.Players.LocalPlayer.Name]
						lol = 0
						idk = false
						local cf = ATM.Open.CFrame
						local lv = cf.lookVector
						game.workspace.Players[game.Players.LocalPlayer.Name].HumanoidRootPart.CFrame =
							cf + (lv * Vector3.new(0, 0, -2))
					end
					if
						game.workspace.Players[game.Players.LocalPlayer.Name]:WaitForChild("[Drxco]").Ammo.Value == 4 and
						idk == false
					then
						idk = true
						reload(game.Players.LocalPlayer.Name, "[Drxco]")
						wait(0.5)
						idk = false
					else
						for i, v in pairs(workspace.Cashiers:GetChildren()) do
							if v:WaitForChild("Humanoid").Health > 0 then
								if idk == false then
									if ATM.Humanoid.Health > 0 then
										game:GetService("VirtualUser"):Button1Down(Vector2.new(0, 0, 0))
										local cf = ATM.Open.CFrame
										local lv = cf.lookVector
										game.workspace.Players[game.Players.LocalPlayer.Name].HumanoidRootPart.CFrame =
											cf + (lv * Vector3.new(0, 0, -2))
									end
								end
							end
						end
					end
					for i, v in pairs(workspace.Cashiers:GetChildren()) do
						if v:WaitForChild("Humanoid").Health > 0 then
							if ATM.Humanoid.Health < 0 and idk == false then
								lol = 10
								wait(0.1)
								if idk == false then
									local cf = ATM.Open.CFrame
									local lv = cf.lookVector
									game.workspace.Players[game.Players.LocalPlayer.Name].HumanoidRootPart.CFrame =
										cf + (lv * Vector3.new(0, 0, -2))
	
									ATM = GetATM()
								end
								lol = 0
							end
						end
					end
				end
			end)
		end
	end)
end
coroutine.wrap(RGLI_fake_script)()
local function MLBO_fake_script() -- GlockAutofarm.LocalScript 
	local script = Instance.new('LocalScript', GlockAutofarm)

	script.Parent.MouseButton1Click:Connect(function()
		if game.Players.LocalPlayer.Character.Animate:FindFirstChild("idle") then
			game.Players.LocalPlayer.Character.Animate.idle:Destroy()
		end
		local me = game:service'Players'.LocalPlayer
		local plr = game.Players.LocalPlayer
		local savedarmourpos = plr.Character.HumanoidRootPart.Position
		local toolname = "[Glock] - $300"
		plr.Character.HumanoidRootPart.CFrame = CFrame.new(game.Workspace.Ignored.Shop[toolname].Head.Position)
		wait(.1)
		fireclickdetector(game.Workspace.Ignored.Shop[toolname].ClickDetector)
		wait(.1)
		fireclickdetector(game.Workspace.Ignored.Shop[toolname].ClickDetector)
		wait(.1)
		fireclickdetector(game.Workspace.Ignored.Shop[toolname].ClickDetector)
		wait(.1)
		fireclickdetector(game.Workspace.Ignored.Shop[toolname].ClickDetector)
		wait(.1)
		fireclickdetector(game.Workspace.Ignored.Shop[toolname].ClickDetector)
		wait(.1)
		fireclickdetector(game.Workspace.Ignored.Shop[toolname].ClickDetector)
		wait(.1)
		me.Character.Humanoid:EquipTool(me.Backpack:FindFirstChild("[Glock]"))
		wait(0.001)
		plr.Character.HumanoidRootPart.CFrame = CFrame.new(savedarmourpos)
		plr.Character.HumanoidRootPart.CFrame = CFrame.new(savedarmourpos)
		function bypass()
			local oh1 = CFrame.new(169.126266, -121.450089, 182.002182)
			local oh2 = game:GetService("Players")
			local oh3 = oh2.LocalPlayer.Character.HumanoidRootPart
	
	
			oh3.CFrame = oh1
			wait(1.5)
		end
		repeat
			wait()
		until game:IsLoaded()
	
		if workspace.Players[game.Players.LocalPlayer.Name]:FindFirstChild("[Glock]") then
			workspace.Players[game.Players.LocalPlayer.Name]:FindFirstChild("[Glock]").Name = "[Glock]"
		else
			game.Players.LocalPlayer.Backpack["[Glock]"].Parent = workspace.Players[game.Players.LocalPlayer.Name]
			game.workspace.Players[game.Players.LocalPlayer.Name]:FindFirstChild("[Glock]").Name = "[Glock]"
		end
	
		function Buy()
			fireclickdetector(workspace.Ignored.Shop["25 [Glock Ammo] - $60"].ClickDetector)
		end
	
		local timer = 0
		local ATM = "nil"
		local GetAmmoOrReload = false
		local Cash = false
	
		function GetCash()
			for i, v in pairs(workspace.Ignored.Drop:GetChildren()) do
				if
					v.Name == "MoneyDrop" and
					(workspace.Players[game.Players.LocalPlayer.Name].HumanoidRootPart.Position - v.Position).Magnitude < 12
				then
					Cash = true
					fireclickdetector(v.ClickDetector)
					wait(1)
					Cash = false
				end
			end
		end
	
		function getATM()
			for i, v in pairs(workspace.Cashiers:GetChildren()) do
				if v:WaitForChild("Humanoid").Health > 0 then
					local cf = v.Head.CFrame
					local lv = cf.lookVector
					game.workspace.Players[game.Players.LocalPlayer.Name].HumanoidRootPart.CFrame =
						cf + (lv * Vector3.new(0, 0, -3))
					game.ReplicatedStorage.MainEvent:FireServer("UpdateMousePos", v.Head.Position)
					return v
				end
			end
		end
	
		ATM = getATM()
	
		function reload(name, gun)
			local A_1 = "Reload"
			local A_2 = game:GetService("Workspace").Players[name][gun]
			local Event = game:GetService("ReplicatedStorage").MainEvent
			Event:FireServer(A_1, A_2)
		end
	
		game:GetService("RunService").Heartbeat:Connect(function()
			GetCash()
			game.Players.LocalPlayer.Character.Humanoid:ChangeState(11)
			if timer == 0 and Cash == false then
				if game.Players.LocalPlayer.DataFolder.Inventory["[Glock]"].Value == "0" and GetAmmoOrReload == false then
					timer = 10
					GetAmmoOrReload = true
					local part = workspace.Ignored.Shop["25 [Glock Ammo] - $60"].Head
					game.workspace.Players[game.Players.LocalPlayer.Name].HumanoidRootPart.CFrame =
						CFrame.new(part.CFrame.X, part.CFrame.Y + 4, part.CFrame.Z)
					game.workspace.Players[game.Players.LocalPlayer.Name]["[Glock]"].Parent =
						game.Players.LocalPlayer.Backpack
					wait(2)
					for i = 1, 10 do
						game.workspace.Players[game.Players.LocalPlayer.Name].HumanoidRootPart.CFrame =
							CFrame.new(
								part.CFrame.X + math.random(1, 2),
								part.CFrame.Y + math.random(1, 2),
								part.CFrame.Z + math.random(1, 2)
							)
						print "e"
						Buy()
						wait(1)
					end
					game.Players.LocalPlayer.Backpack["[Glock]"].Parent =
						game.workspace.Players[game.Players.LocalPlayer.Name]
					timer = 0
					GetAmmoOrReload = false
					local cf = ATM.Head.CFrame
					local lv = cf.lookVector
					game.workspace.Players[game.Players.LocalPlayer.Name].HumanoidRootPart.CFrame =
						cf + (lv * Vector3.new(0, 0, -3))
				end
				if
					game.workspace.Players[game.Players.LocalPlayer.Name]:WaitForChild("[Glock]").Ammo.Value == 0 and
					GetAmmoOrReload == false
				then
					GetAmmoOrReload = true
					reload(game.Players.LocalPlayer.Name, "[Glock]")
					wait(2)
					GetAmmoOrReload = false
				else
					for i, v in pairs(workspace.Cashiers:GetChildren()) do
						if v:WaitForChild("Humanoid").Health > 0 then
							if GetAmmoOrReload == false then
								if ATM.Humanoid.Health > 0 then
									game:GetService("VirtualUser"):Button1Down(Vector2.new(0, 0, 0))
									local cf = ATM.Head.CFrame
									local lv = cf.lookVector
									game.workspace.Players[game.Players.LocalPlayer.Name].HumanoidRootPart.CFrame =
										cf + (lv * Vector3.new(0, 0, -3))
								end
							end
						end
					end
				end
				for i, v in pairs(workspace.Cashiers:GetChildren()) do
					if v:WaitForChild("Humanoid").Health > 0 then
						if ATM.Humanoid.Health < 0 and GetAmmoOrReload == false then
							timer = 10
							wait(0.1)
							if GetAmmoOrReload == false then
								local cf = ATM.Head.CFrame
								local lv = cf.lookVector
								game.workspace.Players[game.Players.LocalPlayer.Name].HumanoidRootPart.CFrame =
									cf + (lv * Vector3.new(0, 0, -3))
	
								ATM = getATM()
							end
							timer = 0
						end
					end
				end
			end
		end
		)
	end)
end
coroutine.wrap(MLBO_fake_script)()
local function JHRFUC_fake_script() -- SMGAutoFarm.LocalScript 
	local script = Instance.new('LocalScript', SMGAutoFarm)

	script.Parent.MouseButton1Click:Connect(function()
		if game.Players.LocalPlayer.Character.Animate:FindFirstChild("idle") then
			game.Players.LocalPlayer.Character.Animate.idle:Destroy()
		end
		local me = game:service'Players'.LocalPlayer
		local plr = game.Players.LocalPlayer
		local savedarmourpos = plr.Character.HumanoidRootPart.Position
		local toolname = "[SMG] - $750"
		plr.Character.HumanoidRootPart.CFrame = CFrame.new(game.Workspace.Ignored.Shop[toolname].Head.Position)
		wait(.1)
		fireclickdetector(game.Workspace.Ignored.Shop[toolname].ClickDetector)
		wait(.1)
		fireclickdetector(game.Workspace.Ignored.Shop[toolname].ClickDetector)
		wait(.1)
		fireclickdetector(game.Workspace.Ignored.Shop[toolname].ClickDetector)
		wait(.1)
		fireclickdetector(game.Workspace.Ignored.Shop[toolname].ClickDetector)
		wait(.1)
		fireclickdetector(game.Workspace.Ignored.Shop[toolname].ClickDetector)
		wait(.1)
		fireclickdetector(game.Workspace.Ignored.Shop[toolname].ClickDetector)
		wait(.1)
		me.Character.Humanoid:EquipTool(me.Backpack:FindFirstChild("[SMG]"))
		wait(0.001)
		plr.Character.HumanoidRootPart.CFrame = CFrame.new(savedarmourpos)
		plr.Character.HumanoidRootPart.CFrame = CFrame.new(savedarmourpos)
		function bypass()
			local oh1 = CFrame.new(169.126266, -121.450089, 182.002182)
			local oh2 = game:GetService("Players")
			local oh3 = oh2.LocalPlayer.Character.HumanoidRootPart
	
	
			oh3.CFrame = oh1
			wait(1.5)
		end
		repeat
			wait()
		until game:IsLoaded()
	
		if workspace.Players[game.Players.LocalPlayer.Name]:FindFirstChild("[SMG]") then
			workspace.Players[game.Players.LocalPlayer.Name]:FindFirstChild("[SMG]").Name = "[SMG]"
		else
			game.Players.LocalPlayer.Backpack["[SMG]"].Parent = workspace.Players[game.Players.LocalPlayer.Name]
			game.workspace.Players[game.Players.LocalPlayer.Name]:FindFirstChild("[SMG]").Name = "[SMG]"
		end
	
		function Buy()
			fireclickdetector(workspace.Ignored.Shop["80 [SMG Ammo] - $60"].ClickDetector)
		end
	
		local timer = 0
		local ATM = "nil"
		local GetAmmoOrReload = false
		local Cash = false
	
		function GetCash()
			for i, v in pairs(workspace.Ignored.Drop:GetChildren()) do
				if
					v.Name == "MoneyDrop" and
					(workspace.Players[game.Players.LocalPlayer.Name].HumanoidRootPart.Position - v.Position).Magnitude < 12
				then
					Cash = true
					fireclickdetector(v.ClickDetector)
					wait(1)
					Cash = false
				end
			end
		end
	
		function getATM()
			for i, v in pairs(workspace.Cashiers:GetChildren()) do
				if v:WaitForChild("Humanoid").Health > 0 then
					local cf = v.Head.CFrame
					local lv = cf.lookVector
					game.workspace.Players[game.Players.LocalPlayer.Name].HumanoidRootPart.CFrame =
						cf + (lv * Vector3.new(0, 0, -3))
					game.ReplicatedStorage.MainEvent:FireServer("UpdateMousePos", v.Head.Position)
					return v
				end
			end
		end
	
		ATM = getATM()
	
		function reload(name, gun)
			local A_1 = "Reload"
			local A_2 = game:GetService("Workspace").Players[name][gun]
			local Event = game:GetService("ReplicatedStorage").MainEvent
			Event:FireServer(A_1, A_2)
		end
	
		game:GetService("RunService").Heartbeat:Connect(function()
			GetCash()
			game.Players.LocalPlayer.Character.Humanoid:ChangeState(11)
			if timer == 0 and Cash == false then
				if game.Players.LocalPlayer.DataFolder.Inventory["[SMG]"].Value == "0" and GetAmmoOrReload == false then
					timer = 10
					GetAmmoOrReload = true
					local part = workspace.Ignored.Shop["80 [SMG Ammo] - $60"].Head
					game.workspace.Players[game.Players.LocalPlayer.Name].HumanoidRootPart.CFrame =
						CFrame.new(part.CFrame.X, part.CFrame.Y + 4, part.CFrame.Z)
					game.workspace.Players[game.Players.LocalPlayer.Name]["[SMG]"].Parent =
						game.Players.LocalPlayer.Backpack
					wait(2)
					for i = 1, 10 do
						game.workspace.Players[game.Players.LocalPlayer.Name].HumanoidRootPart.CFrame =
							CFrame.new(
								part.CFrame.X + math.random(1, 2),
								part.CFrame.Y + math.random(1, 2),
								part.CFrame.Z + math.random(1, 2)
							)
						print "e"
						Buy()
						wait(1)
					end
					game.Players.LocalPlayer.Backpack["[SMG]"].Parent =
						game.workspace.Players[game.Players.LocalPlayer.Name]
					timer = 0
					GetAmmoOrReload = false
					local cf = ATM.Head.CFrame
					local lv = cf.lookVector
					game.workspace.Players[game.Players.LocalPlayer.Name].HumanoidRootPart.CFrame =
						cf + (lv * Vector3.new(0, 0, -3))
				end
				if
					game.workspace.Players[game.Players.LocalPlayer.Name]:WaitForChild("[SMG]").Ammo.Value == 0 and
					GetAmmoOrReload == false
				then
					GetAmmoOrReload = true
					reload(game.Players.LocalPlayer.Name, "[SMG]")
					wait(2)
					GetAmmoOrReload = false
				else
					for i, v in pairs(workspace.Cashiers:GetChildren()) do
						if v:WaitForChild("Humanoid").Health > 0 then
							if GetAmmoOrReload == false then
								if ATM.Humanoid.Health > 0 then
									game:GetService("VirtualUser"):Button1Down(Vector2.new(0, 0, 0))
									local cf = ATM.Head.CFrame
									local lv = cf.lookVector
									game.workspace.Players[game.Players.LocalPlayer.Name].HumanoidRootPart.CFrame =
										cf + (lv * Vector3.new(0, 0, -3))
								end
							end
						end
					end
				end
				for i, v in pairs(workspace.Cashiers:GetChildren()) do
					if v:WaitForChild("Humanoid").Health > 0 then
						if ATM.Humanoid.Health < 0 and GetAmmoOrReload == false then
							timer = 10
							wait(0.1)
							if GetAmmoOrReload == false then
								local cf = ATM.Head.CFrame
								local lv = cf.lookVector
								game.workspace.Players[game.Players.LocalPlayer.Name].HumanoidRootPart.CFrame =
									cf + (lv * Vector3.new(0, 0, -3))
	
								ATM = getATM()
							end
							timer = 0
						end
					end
				end
			end
		end
		)
	end)
end
coroutine.wrap(JHRFUC_fake_script)()
