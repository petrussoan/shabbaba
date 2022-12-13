game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "Loaded!";
		Text = "Z to honk [must have boombox]";
		Duration = 15;
	})

	game:GetService("Players").LocalPlayer.Character:FindFirstChildWhichIsA("Humanoid").WalkSpeed = 60
	game:GetService("Players").LocalPlayer.Character:FindFirstChildWhichIsA("Humanoid").JumpPower = 20
	game:GetService("Players").LocalPlayer.Character.Animate.walk.WalkAnim.AnimationId = "rbxassetid://3360694441"
	game:GetService("Players").LocalPlayer.Character.Animate.run.RunAnim.AnimationId = "rbxassetid://3360694441"
	game:GetService("Players").LocalPlayer.Character.Animate.fall.FallAnim.AnimationId = "rbxassetid://3360694441"
	game:GetService("Players").LocalPlayer.Character.Animate.idle.Animation1.AnimationId = "rbxassetid://3360694441"
	game:GetService("Players").LocalPlayer.Character.Animate.idle.Animation2.AnimationId = "rbxassetid://3360694441"
	game:GetService("Players").LocalPlayer.Character.Animate.jump.JumpAnim.AnimationId = "rbxassetid://3360694441"
	for i, thing in pairs(game:GetService("Players").LocalPlayer.Character:GetDescendants()) do
		if thing.ClassName == "MeshPart" then
			thing.CustomPhysicalProperties = PhysicalProperties.new(0.04, 0, 0)
		end
	end
	local r15height = "0.56"
	game:GetService("Players").LocalPlayer.Character:FindFirstChildWhichIsA("Humanoid").HipHeight = r15height



	wait(1)



	-- honk


-- removed added in the other local script












	-- invis Boombox


	local  MyStand = "Felkusama"
	local SuperJumpEnabled = false

	getgenv().Toggled = false
	local UIS = game:GetService("UserInputService")
	UIS.InputBegan:connect(function(input,gameProcessed)
		if input.UserInputType == Enum.UserInputType.Keyboard then
			if input.KeyCode == Enum.KeyCode.Q then
				if UIS:GetFocusedTextBox() == nil then
					if getgenv().Toggled == false then
						getgenv().Toggled = true
					else
						getgenv().Toggled = true
					end;end;end;end;end)

	local LocalPlayer = game:GetService("Players").LocalPlayer
	local Cookies = LocalPlayer.Character:WaitForChild("Humanoid"):LoadAnimation(game.ReplicatedStorage.ClientAnimations.Roll)
	local OriginalKeyUpValue = 0
	local Anim = Instance.new("Animation" )
	Anim.AnimationId = "rbxassetid://2788290270"
	local CoreUI = Instance.new("ScreenGui")
	CoreUI.Parent = game.CoreGui
	local SaveLocation = nil
	local RigWalk = nil
	local RigIdle = nil
	local InTimeErase = false

	local Pointing = Instance.new("Animation", game.ReplicatedStorage.ClientAnimations)
	Pointing.AnimationId = "rbxassetid://507770453"

	local Poter = LocalPlayer.Character:WaitForChild("Humanoid"):LoadAnimation(Pointing)
	Poter.Looped = true
	Poter.Priority = Enum.AnimationPriority.Action

	local WalkAnimation = Instance.new("Animation", game.ReplicatedStorage.ClientAnimations)
	WalkAnimation.AnimationId = "rbxassetid://2510198475"

	local Idle = Instance.new("Animation", game.ReplicatedStorage.ClientAnimations)
	Idle.AnimationId = "rbxassetid://507766388"

	local OldChar = LocalPlayer.Character

	function FoV()
		local fov = coroutine.wrap(function()
			local Camera = workspace.Camera
			for i = 1, 20 do
				Camera.FieldOfView = 8*i
				wait(0.01)
			end
			for i = 1, 20 do
				Camera.FieldOfView = 160-i*4.5
				wait(0.01)
			end
		end)
		fov()
	end

	local WalkSpeed = false

	function Lighting()
		if game.Lighting:FindFirstChild("ERASE") == nil then
			local sound5 = Instance.new("Sound", CoreUI)
			sound5.Volume = 0.1
			sound5.Name = "ERASE"
			sound5.Looped = true
			sound5.SoundId = "rbxassetid://3167092959"
			sound5:Play()

			game.Lighting.Sky.Parent = workspace
			game:GetObjects("rbxassetid://6546113226")[1].Parent=game.Lighting

		else
			workspace.Sky.Parent = game.Lighting
			CoreUI:FindFirstChild("ERASE"):Destroy()
			game.Lighting:FindFirstChild("ERASE"):Destroy()
		end
	end

	function TimeEraseUI()
		local sound5 = Instance.new("Sound", CoreUI)
		sound5.Volume = 0.1
		sound5.SoundId = "rbxassetid://6546128175"
		sound5:Play()

		local Image = Instance.new("ImageLabel", CoreUI)
		Image.Image = "http://www.roblox.com/asset/?id=6546043746"
		Image.BackgroundTransparency = 1
		Image.AnchorPoint = Vector2.new(0.5, 0.5)
		Image.Size = UDim2.fromScale(1, 1)
		Image.Position = UDim2.fromScale(-0.5, 0.5)
		delay(0, function()
			for i = 0, 1, 0.1 do
				Image.Position = UDim2.fromScale(-Image.Position.X.Scale+i, 0.5)
				Image.ImageTransparency = Image.ImageTransparency+i
				wait(.01)
			end
			Image:Destroy()
			sound5:Destroy()
		end)
	end


	function ModelCharacter()
		if workspace:FindFirstChild(LocalPlayer.Name.."StringKOD") == nil then
			local MODEL = Instance.new("Model", workspace)
			MODEL.Name = LocalPlayer.Name.."StringKOD"

			OldChar.Humanoid:UnequipTools()

			for i, v in pairs(OldChar:GetChildren()) do 
				if (v:IsA("BasePart")  or v:IsA("MeshPart")) and v.Parent:FindFirstChildOfClass("Humanoid") and v.Name ~= "HumanoidRootPart" then
					local Part = v:Clone()
					Part.Parent = MODEL
					Part.Name = v.Name
					Part.Material = Enum.Material.ForceField
					Part.CFrame = v.CFrame
					Part.Transparency = 0.5 
					Part.BrickColor = BrickColor.Red()
					Part.CanCollide = false
					Part.Anchored = true
					for i, v  in pairs(Part:GetChildren()) do 
						if v.ClassName ~= "SpecialMesh" then
							v:Destroy()
						end
					end
				end
			end
			local NewCharacter = game:GetObjects("rbxassetid://6547055500")[1]
			NewCharacter.Parent = MODEL
			NewCharacter.Name = "Idaro"

			workspace.Camera.CameraSubject = NewCharacter.Humanoid
			SaveLocation = OldChar.HumanoidRootPart.CFrame
			InTimeErase = true
			NewCharacter.HumanoidRootPart.CFrame = SaveLocation

			RigIdle = NewCharacter:WaitForChild("Humanoid"):LoadAnimation(Idle)
			RigIdle.Looped = true
			RigIdle.Priority = Enum.AnimationPriority.Action
			RigWalk = NewCharacter:WaitForChild("Humanoid"):LoadAnimation(WalkAnimation)
			RigWalk.Looped = true
			RigWalk.Priority = Enum.AnimationPriority.Action
			WalkSpeed = true
			RigIdle:Play()
		else
			InTimeErase = false
			WalkSpeed = false
			workspace.Camera.CameraSubject =  OldChar.Humanoid
			OldChar.HumanoidRootPart.CFrame =  workspace:FindFirstChild(LocalPlayer.Name.."StringKOD").Idaro.HumanoidRootPart.CFrame
			workspace:FindFirstChild(LocalPlayer.Name.."StringKOD"):Destroy()
		end
	end

	function Slide()
		local XD = OldChar.Humanoid:LoadAnimation(Anim)
		XD:Play()
		XD.TimePosition = 0.15
		XD.Looped = false
		XD:AdjustSpeed(1.1)
	end

	function AddVelocity(Vel, Char)
		Char.HumanoidRootPart.Velocity = Char.HumanoidRootPart.Velocity+Vel
	end

	local IsJump = false

	function Jumping()
		if IsJump == false then
			return false
		else
			return true
		end
	end

	local Mouse = LocalPlayer:GetMouse()

	assert(getrawmetatable)
	gmt = getrawmetatable(game)
	setreadonly(gmt, false)
	old = gmt.__namecall
	gmt.__namecall =
		newcclosure(
			function(self, ...)
				local args = {...}
				if tostring(args[1]) == "TeleportDetect" then
				return
			elseif tostring(args[1]) == "CHECKER_1" then
				return
			elseif tostring(args[1]) == "CHECKER" then
				return
			end

				return old(self, ...)
			end
		)


	local MoveDirection = Vector3.new(0,0,0)
	local WSpped = 0 
	local LeftSpeed = 0
	local UpSpeed = 0

	function IdleRigXD()
		if RigIdle and RigWalk.IsPlaying and WSpped == 0 and LeftSpeed == 0 and UpSpeed == 0 then
			RigIdle:Play()
			RigWalk:Stop()
		end
	end

	function WalkRigXD()
		if RigWalk and RigIdle.IsPlaying then
			RigIdle:Stop()
			RigWalk:Play()
		end
	end

	Mouse.KeyDown:Connect(function(KeyDownXD)
		if workspace:FindFirstChild(LocalPlayer.Name.."StringKOD") then
			if KeyDownXD == "w" then
				WSpped = -1
				WalkRigXD()
			elseif KeyDownXD == "a" then
				LeftSpeed = -1
				WalkRigXD()
			elseif KeyDownXD == "d" then
				LeftSpeed = 1
				WalkRigXD()
			elseif KeyDownXD == "s" then
				WSpped = 1
				WalkRigXD()
			end
		end
	end)

	Mouse.KeyUp:Connect(function(KeyDownXD)
		if KeyDownXD == "w" then
			WSpped = 0
			IdleRigXD()
		elseif KeyDownXD == "a" then
			LeftSpeed = 0
			IdleRigXD()
		elseif KeyDownXD == "d" then
			LeftSpeed = -0
			IdleRigXD()
		elseif KeyDownXD == "s" then
			WSpped = 0
			IdleRigXD()
		end
	end)

	local CD = false
	local uis = game:GetService("UserInputService")

	uis.InputBegan:Connect(function(i, XD)
		if i.KeyCode == Enum.KeyCode.Q and XD == false then
			if SuperJumpEnabled == false then
				SuperJumpEnabled = true
			elseif SuperJumpEnabled == true then
				SuperJumpEnabled = false
			end
		end
	end)

	uis.InputBegan:Connect(function(i, XD)
		if i.KeyCode == Enum.KeyCode.Space and XD == false then
			if workspace:FindFirstChild(LocalPlayer.Name.."StringKOD") == nil then
				if Jumping() == true and not Poter.IsPlaying then
					AddVelocity(OldChar.HumanoidRootPart.CFrame.LookVector*150, OldChar)
					IsJump = false
					Cookies:Stop()
					CD = true
					play(6543434995, true, true)
					Slide()
					repeat wait() until workspace:FindPartOnRayWithWhitelist(Ray.new(OldChar.HumanoidRootPart.Position, Vector3.new(0, -4 * OldChar.HumanoidRootPart.Size.y, 0)), { workspace.MAP })
					CD = false
				end
			else
				workspace:FindFirstChild(LocalPlayer.Name.."StringKOD"):FindFirstChild("Idaro").Humanoid:ChangeState(3)
			end
		end
	end)

	function StopAudio()
		OldChar.LowerTorso.BOOMBOXSOUND:Stop()
	end

	function stop(ID, Key)
		local cor = coroutine.wrap(function()
			wait(OldChar.LowerTorso.BOOMBOXSOUND.TimeLength-0.1)
			if OldChar.LowerTorso.BOOMBOXSOUND.SoundId == "rbxassetid://"..ID and OriginalKeyUpValue == Key then
				StopAudio()
			end
		end)
		cor()
	end






	if LocalPlayer.Backpack:FindFirstChild("[Boombox]") then
		local Tool = nil
		if OldChar:FindFirstChildOfClass("Tool") and LMAO == true then
			Tool = OldChar:FindFirstChildOfClass("Tool")
			OldChar:FindFirstChildOfClass("Tool").Parent = LocalPlayer.Backpack
		end
		LocalPlayer.Backpack["[Boombox]"].Parent =
			OldChar
		game.ReplicatedStorage.MainEvent:FireServer("Boombox", ID)
		OldChar["[Boombox]"].RequiresHandle = false
		if OldChar["[Boombox]"]:FindFirstChild("Handle") then
			OldChar["[Boombox]"].Handle:Destroy()
		end
		OldChar["[Boombox]"].Parent =
			LocalPlayer.Backpack
		LocalPlayer.PlayerGui.MainScreenGui.BoomboxFrame.Visible = false
		if Tool ~= true then
			if Tool then
				Tool.Parent = OldChar
			end
		end
		if STOP == true then
			OldChar.LowerTorso:WaitForChild("BOOMBOXSOUND")
			local cor = coroutine.wrap(function()
				repeat wait() until OldChar.LowerTorso.BOOMBOXSOUND.SoundId == "rbxassetid://"..ID and OldChar.LowerTorso.BOOMBOXSOUND.TimeLength > 0.01
				OriginalKeyUpValue = OriginalKeyUpValue+1
				stop(ID, OriginalKeyUpValue)
			end)
			cor()
		end
	end

	wait(1)

	Plr.Character.Humanoid:UnequipTools()
