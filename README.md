print('Yes Sam Kak MakMak ')
local placeId = game.PlaceId
if placeId == 2753915549 or placeId == 4442272183 or placeId == 7449423635 then
    BF = true
elseif placeId == 3237168 then
    OPL = true
elseif placeId == 914010731 then
    RO = true
elseif placeId == 6299805723 then
    AFS = true
elseif placeId == 4520749081 or placeId == 6381829480 or placeId == 5931540094 then
	KL = true
elseif placeId == 4042427666 then
    ANS = true
elseif placeId == 2809202155 then
    YBA = true
    print("\n game not support")
end
spawn(function()
	while wait() do 
		print("JayKung#8973 ")
	end
end)
if BF then
	repeat wait() until game:IsLoaded()
	if getgenv().Setting then else
		getgenv().Setting = {
			["Join Team"] = "Pirate", -- "Pirate","Marine"
			["Auto Farm Level"] = false,
		
			-- Setting etc
			["Select Weapon"] = "",
			["Auto Rejoin"] = false,
		
			-- Old World
			["Auto New World"] = false,
		
			-- New World
			["Auto Factory"] = false,
			["Auto third World"] = false,
		
			-- New Fighting Styles & etc
			["Auto Superhuman"] = false,
			["Auto Superhuman [Full]"] = false,
			["Auto Death Step"] = false,
			["Auto Dragon Talon"] = false,
			["Auto Electric Clow"] = false,
			["Auto Buy Legendary Sword"] = false,
			["Auto Buy Legendary Sword Hop"] = false,
			["Auto Buy Enhancement"] = false,
			["Auto Farm Select Boss Hop"] = false,
		
			-- Auto Stats
			["Melee"] = false,
			["Defense"] = false,
			["Sword"] = false,
			["Gun"] = false,
			["Demon Fruit"] = false,
		
			-- Use Candy
			["Auto Buy Exp x2"] = false,
			["Auto Buy Exp x2[ Exp Expire ]"] = false,
	
			-- Players
			["Bounty Hop"] = false
		}
	end
	
	if not game:IsLoaded() then game.Loaded:Wait() end
	repeat wait() until game.Players
	repeat wait() until game.Players.LocalPlayer
	repeat wait() until game.ReplicatedStorage
	repeat wait() until game.ReplicatedStorage:FindFirstChild("Remotes");
	repeat wait() until game.Players.LocalPlayer:FindFirstChild("PlayerGui");
	repeat wait() until game.Players.LocalPlayer.PlayerGui:FindFirstChild("Main");
	repeat wait()
		if game:GetService("Players").LocalPlayer.PlayerGui:WaitForChild("Main").ChooseTeam.Visible == true then
			if getgenv().Setting["Join Team"] == "Pirate" then
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.Size = UDim2.new(0, 10000, 0, 10000)
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.Position = UDim2.new(-4, 0, -5, 0)
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.BackgroundTransparency = 1
				wait(.5)
				game:GetService'VirtualUser':Button1Down(Vector2.new(99,99))
				game:GetService'VirtualUser':Button1Up(Vector2.new(99,99))
			elseif getgenv().Setting["Join Team"] == "Marine" then
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Marines.Frame.ViewportFrame.TextButton.Size = UDim2.new(0, 10000, 0, 10000)
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Marines.Frame.ViewportFrame.TextButton.Position = UDim2.new(-4, 0, -5, 0)
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Marines.Frame.ViewportFrame.TextButton.BackgroundTransparency = 1
				wait(.5)
				game:GetService'VirtualUser':Button1Down(Vector2.new(99,99))
				game:GetService'VirtualUser':Button1Up(Vector2.new(99,99))
			else
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.Size = UDim2.new(0, 10000, 0, 10000)
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.Position = UDim2.new(-4, 0, -5, 0)
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.BackgroundTransparency = 1
				wait(.5)
				game:GetService'VirtualUser':Button1Down(Vector2.new(99,99))
				game:GetService'VirtualUser':Button1Up(Vector2.new(99,99))
			end
		end
	until game.Players.LocalPlayer.Team ~= nil and game:IsLoaded() 
	
	wait(1)
	
	if game.CoreGui.RobloxGui:FindFirstChild("Voice Chat Ui") then game.CoreGui.RobloxGui:FindFirstChild("Voice Chat Ui"):Destroy() end
	local library = {RainbowColorValue = 0, HueSelectionPosition = 0}
	local PresetColor = Color3.fromRGB(255, 0, 0)
	local UserInputService = game:GetService("UserInputService")
	local TweenService = game:GetService("TweenService")
	local RunService = game:GetService("RunService")
	local LocalPlayer = game:GetService("Players").LocalPlayer
	local MyNameIs = LocalPlayer.Name
	local Mouse = LocalPlayer:GetMouse()
	local CloseBind = Enum.KeyCode.RightControl
	
	local ScreenGui = Instance.new("ScreenGui")
	local TabButtonLayout = Instance.new("UIListLayout")
	
	ScreenGui.Name = "Voice Chat Ui"
	ScreenGui.Parent = game.CoreGui.RobloxGui
	local uitoggled = false
	UserInputService.InputBegan:Connect(function(io, p)
		if io.KeyCode == Enum.KeyCode.RightControl then
			if uitoggled == false then
				ScreenGui.Enabled = false
				uitoggled = true
			else
				ScreenGui.Enabled = true
				uitoggled = false
			end
		end
	end)
	
	coroutine.wrap(
		function()
			while wait() do
				library.RainbowColorValue = library.RainbowColorValue + 1 / 255
				library.HueSelectionPosition = library.HueSelectionPosition + 1
	
				if library.RainbowColorValue >= 1 then
					library.RainbowColorValue = 0
				end
	
				if library.HueSelectionPosition == 80 then
					library.HueSelectionPosition = 0
				end
			end
		end
	)()
	
	local function MakeDraggable(topbarobject, object)
		local Dragging = nil
		local DragInput = nil
		local DragStart = nil
		local StartPosition = nil
	
		local function Update(input)
			local Delta = input.Position - DragStart
			local pos =
				UDim2.new(
					StartPosition.X.Scale,
					StartPosition.X.Offset + Delta.X,
					StartPosition.Y.Scale,
					StartPosition.Y.Offset + Delta.Y
				)
			object.Position = pos
		end
	
		topbarobject.InputBegan:Connect(
			function(input)
				if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
					Dragging = true
					DragStart = input.Position
					StartPosition = object.Position
	
					input.Changed:Connect(
						function()
							if input.UserInputState == Enum.UserInputState.End then
								Dragging = false
							end
						end
					)
				end
			end
		)
	
		topbarobject.InputChanged:Connect(
			function(input)
				if
					input.UserInputType == Enum.UserInputType.MouseMovement or
					input.UserInputType == Enum.UserInputType.Touch
				then
					DragInput = input
				end
			end
		)
	
		UserInputService.InputChanged:Connect(
			function(input)
				if input == DragInput and Dragging then
					Update(input)
				end
			end
		)
	end
	
	local function RippleEffect(object)
		spawn(function()
			local Ripple = Instance.new("ImageLabel")
			Ripple.Name = "Ripple"
			Ripple.Parent = object
			Ripple.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Ripple.BackgroundTransparency = 1.000
			Ripple.ZIndex = 8
			Ripple.Image = "rbxassetid://2708891598"
			Ripple.ImageTransparency = 0.800
			Ripple.ScaleType = Enum.ScaleType.Fit
			Ripple.Position = UDim2.new((Mouse.X - Ripple.AbsolutePosition.X) / object.AbsoluteSize.X, 0, (Mouse.Y - Ripple.AbsolutePosition.Y) / object.AbsoluteSize.Y, 0)
			TweenService:Create(Ripple, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Position = UDim2.new(-5.5, 0, -15, 0), Size = UDim2.new(12, 0, 30, 0)}):Play()
			wait(0.5)
			TweenService:Create(Ripple, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {ImageTransparency = 1}):Play()
			wait(0.5)
			Ripple:Destroy()
		end)
	end
	
	function library:Window(name,game)
		if getgenv().Theme ~= nil then
			ColorII = getgenv().Theme.Tab.Color
	
			ColorIII = getgenv().Theme.Line.LeftColor
			ColorIIII = getgenv().Theme.Line.RightColor
	
			ColorIIIII = getgenv().Theme.Toggle.LeftColor
			ColorIIIIII = getgenv().Theme.Toggle.RightColor
	
			ColorIIIIIII = getgenv().Theme.Slider.LeftColor
			ColorIIIIIIII = getgenv().Theme.Slider.RightColor
		else
			ColorII = Color3.fromRGB(255, 0, 0)
	
			ColorIII = Color3.fromRGB(255, 0, 0)
			ColorIIII = Color3.fromRGB(0, 0, 255)
	
			ColorIIIII = Color3.fromRGB(255, 0, 0)
			ColorIIIIII = Color3.fromRGB(0, 0, 255)
	
			ColorIIIIIII = Color3.fromRGB(255, 0, 0)
			ColorIIIIIIII = Color3.fromRGB(0, 0, 255)
		end
	
		local Main = Instance.new("Frame")
		local ShowName = Instance.new("TextLabel")
		local MainUICorner = Instance.new("UICorner")
		local TopMain = Instance.new("Frame")
		local TopMainUICorner = Instance.new("UICorner")
		local TopMainLine = Instance.new("Frame")
		local NameHub = Instance.new("TextLabel")
		local Toggleui = Instance.new("TextLabel")
		local HideTab = Instance.new("ImageButton")
		local SizeFullSection = Instance.new("Frame")
	
		Main.Name = "Main"
		Main.Parent = ScreenGui
		Main.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
		Main.ClipsDescendants = true
		Main.Position = UDim2.new(0.5, -325, 0.5, -175)
		Main.Size = UDim2.new(0, 650, 0, 425)
	
		MainUICorner.Name = "MainUICorner"
		MainUICorner.Parent = Main
	
		TopMain.Name = "TopMain"
		TopMain.Parent = Main
		TopMain.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
		TopMain.Size = UDim2.new(0, 650, 0, 30)
	
		MakeDraggable(TopMain, Main)
	
		TopMainUICorner.Name = "TopMainUICorner"
		TopMainUICorner.Parent = TopMain
	
		TopMainLine.Name = "TopMainLine"
		TopMainLine.Parent = TopMain
		TopMainLine.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
		TopMainLine.BorderSizePixel = 0
		TopMainLine.Position = UDim2.new(0, 0, 0.833333313, 0)
		TopMainLine.Size = UDim2.new(1, 0, 0, 5)
	
		ShowName.Name = "MyName"
		ShowName.Parent = Main
		ShowName.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		ShowName.BackgroundTransparency = 1.000
		ShowName.Position = UDim2.new(0, 9, 0.92, 0)
		ShowName.Size = UDim2.new(0, 160, 0, 30)
		ShowName.Font = Enum.Font.SourceSansSemibold
		ShowName.RichText =  true
		ShowName.Text = MyNameIs
		ShowName.TextColor3 = Color3.fromRGB(255, 255, 255)
		spawn(function()
			while wait() do 
				for i = 1,255 do
					ShowName.TextColor3 = Color3.fromHSV(i/255, 1, 1)
					wait()
				end
			end
		end)
		local StringSize
		if #tostring(MyNameIs) > 13 then
			StringSize = 18
		else
			StringSize = 20
		end
		ShowName.TextSize = 20.000
		ShowName.TextXAlignment = Enum.TextXAlignment.Left
	
		NameHub.Name = "NameHub"
		NameHub.Parent = TopMain
		NameHub.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		NameHub.BackgroundTransparency = 1.000
		NameHub.Position = UDim2.new(0.0507692285, 0, 0, 0)
		NameHub.Size = UDim2.new(0, 160, 0, 30)
		NameHub.Font = Enum.Font.SourceSansSemibold
		NameHub.RichText =  true
		NameHub.Text = "<font color=\"rgb(".. math.floor(ColorII.R * 255) .. "," .. math.floor(ColorII.G * 255) .. ",".. math.floor(ColorII.B * 255) ..")\"> " .. name .. " </font> Hub | " .. game
		NameHub.TextColor3 = Color3.fromRGB(255, 255, 255)
		NameHub.TextSize = 25.000
		NameHub.TextXAlignment = Enum.TextXAlignment.Left
	
		Toggleui.Name = "Toggleui"
		Toggleui.Parent = TopMain
		Toggleui.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		Toggleui.BackgroundTransparency = 1.000
		Toggleui.Position = UDim2.new(0.803076923, 0, 0, 0)
		Toggleui.Size = UDim2.new(0, 120, 0, 30)
		Toggleui.Font = Enum.Font.SourceSansSemibold
		Toggleui.Text = "[ Right Control ]"
		Toggleui.TextColor3 = Color3.fromRGB(255, 0, 0)
		Toggleui.TextSize = 20.000
	
		HideTab.Name = "HideTab"
		HideTab.Parent = TopMain
		HideTab.BackgroundTransparency = 1.000
		HideTab.Position = UDim2.new(0.0125000002, 0, 0.0670000017, 0)
		HideTab.Size = UDim2.new(0, 25, 0, 25)
		HideTab.ZIndex = 2
		HideTab.Image = "rbxassetid://3926305904"
		HideTab.ImageRectOffset = Vector2.new(484, 204)
		HideTab.ImageRectSize = Vector2.new(36, 36)
		HideTab.AutoButtonColor = false
	
		SizeFullSection.Name = "SizeFullSection"
		SizeFullSection.Parent = Main
		SizeFullSection.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		SizeFullSection.BackgroundTransparency = 1.000
		SizeFullSection.Position = UDim2.new(0.192307696, 0, 0.0933333337, 0)
		SizeFullSection.Size = UDim2.new(0, 525, 0, 340)
	
		local Taplist = Instance.new("Frame")
		local TaplistUIListLayout = Instance.new("UIListLayout")
		local TabSet = Instance.new("TextBox")
		local MainUICorner = Instance.new("UICorner")
		local BalckGrouitList = Instance.new("ScrollingFrame")
		local BalckGrouitListUICorner = Instance.new("UICorner")
		local BalckGrouitListUIListLayout = Instance.new("UIListLayout")
		
		Taplist.Name = "Taplist"
		Taplist.Parent = Main
		Taplist.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		Taplist.BackgroundTransparency = 1.000
		Taplist.Position = UDim2.new(0, 0, 0.0799999982, 0)
		Taplist.Size = UDim2.new(0, 130, 0, 345)
	
		TaplistUIListLayout.Name = "TaplistUIListLayout"
		TaplistUIListLayout.Parent = Taplist
		TaplistUIListLayout.HorizontalAlignment = Enum.HorizontalAlignment.Center
		TaplistUIListLayout.SortOrder = Enum.SortOrder.LayoutOrder
		TaplistUIListLayout.VerticalAlignment = Enum.VerticalAlignment.Center
		TaplistUIListLayout.Padding = UDim.new(0, 5)
	
		TabSet.Name = "TabSet"
		TabSet.Parent = Taplist
		TabSet.BackgroundColor3 = Color3.fromRGB(10, 10, 10)
		TabSet.Size = UDim2.new(0, 120, 0, 25)
		TabSet.Font = Enum.Font.SourceSansSemibold
		TabSet.PlaceholderText = "Search : ..."
		TabSet.Text = ""
		TabSet.TextColor3 = Color3.fromRGB(255, 0, 0)
		TabSet.PlaceholderColor3 = Color3.fromRGB(255, 0, 0)
		TabSet.TextSize = 18.000
		TabSet.ClipsDescendants = true
	
		MainUICorner.Name = "MainUICorner"
		MainUICorner.Parent = TabSet
	
		BalckGrouitList.Name = "BalckGrouitList"
		BalckGrouitList.Parent = Taplist
		BalckGrouitList.Active = true
		BalckGrouitList.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		BalckGrouitList.BackgroundTransparency = 1.000
		BalckGrouitList.BorderColor3 = Color3.fromRGB(35, 35, 35)
		BalckGrouitList.Position = UDim2.new(0, 0, 0.0799999982, 0)
		BalckGrouitList.Size = UDim2.new(0, 120, 0, 305)
		BalckGrouitList.ScrollBarThickness = 1
	
		BalckGrouitListUICorner.Name = "BalckGrouitListUICorner"
		BalckGrouitListUICorner.Parent = BalckGrouitList
	
		BalckGrouitListUIListLayout.Name = "BalckGrouitListUIListLayout"
		BalckGrouitListUIListLayout.Parent = BalckGrouitList
		BalckGrouitListUIListLayout.HorizontalAlignment = Enum.HorizontalAlignment.Center
		BalckGrouitListUIListLayout.SortOrder = Enum.SortOrder.LayoutOrder
		BalckGrouitListUIListLayout.Padding = UDim.new(0, 2)
	
		BalckGrouitListUIListLayout:GetPropertyChangedSignal("AbsoluteContentSize"):Connect(function()
			BalckGrouitList.CanvasSize = UDim2.new(0,0,0,BalckGrouitListUIListLayout.AbsoluteContentSize.Y)
		end)
	
		function library:Notification(name)
			local NotificationHold = Instance.new("TextButton")
			local NotificationFrame = Instance.new("Frame")
			local NotificationFrameUICorner = Instance.new("UICorner")
			local OkayBtn = Instance.new("TextButton")
			local OkayBtnCorner = Instance.new("UICorner")
			local OkayBtnTitle = Instance.new("TextLabel")
			local NotificationTitle = Instance.new("TextLabel")
			local NotificationDesc = Instance.new("TextLabel")
	
			NotificationHold.Name = "NotificationHold"
			NotificationHold.Parent = Main
			NotificationHold.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
			NotificationHold.BackgroundTransparency = 0.700
			NotificationHold.BorderSizePixel = 0
			NotificationHold.Size = UDim2.new(1, 0, 1, 0)
			NotificationHold.AutoButtonColor = false
			NotificationHold.Font = Enum.Font.SourceSans
			NotificationHold.Text = ""
			NotificationHold.TextColor3 = Color3.fromRGB(0, 0, 0)
			NotificationHold.TextSize = 14.000
			NotificationHold.ZIndex = 10
	
			TweenService:Create(
				NotificationHold,
				TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
				{BackgroundTransparency = 0.7}
			):Play()
	
			wait(0.4)
	
			NotificationFrame.Name = "NotificationFrame"
			NotificationFrame.Parent = NotificationHold
			NotificationFrame.AnchorPoint = Vector2.new(0.5, 0.5)
			NotificationFrame.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
			NotificationFrame.BorderSizePixel = 0
			NotificationFrame.ClipsDescendants = true
			NotificationFrame.Position = UDim2.new(0.5, 0, 0.498432577, 0)
			NotificationFrame.Size = UDim2.new(0, 0, 0, 0)
			NotificationFrame.ZIndex = 11
			NotificationFrame:TweenSize(
				UDim2.new(0, 305, 0, 283),
				Enum.EasingDirection.Out,
				Enum.EasingStyle.Quart,
				.6,
				true
			)
			NotificationFrameUICorner.Parent = NotificationFrame
	
			OkayBtn.Name = "OkayBtn"
			OkayBtn.Parent = NotificationFrame
			OkayBtn.BackgroundColor3 = Color3.fromRGB(49, 49, 49)
			OkayBtn.Position = UDim2.new(0.171131134, 0, 0.759717345, 0)
			OkayBtn.Size = UDim2.new(0, 200, 0, 42)
			OkayBtn.AutoButtonColor = false
			OkayBtn.Font = Enum.Font.SourceSans
			OkayBtn.Text = ""
			OkayBtn.TextColor3 = Color3.fromRGB(0, 0, 0)
			OkayBtn.TextSize = 14.000
			OkayBtn.ZIndex = 11
	
			OkayBtnCorner.CornerRadius = UDim.new(0, 5)
			OkayBtnCorner.Name = "OkayBtnCorner"
			OkayBtnCorner.Parent = OkayBtn
	
			OkayBtnTitle.Name = "OkayBtnTitle"
			OkayBtnTitle.Parent = OkayBtn
			OkayBtnTitle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			OkayBtnTitle.BackgroundTransparency = 1.000
			OkayBtnTitle.Size = UDim2.new(0, 200, 0, 42)
			OkayBtnTitle.Text = "Okey"
			OkayBtnTitle.Font = Enum.Font.Gotham
			OkayBtnTitle.TextColor3 = Color3.fromRGB(202, 202, 202)
			OkayBtnTitle.TextSize = 24.000
			OkayBtnTitle.ZIndex = 11
	
			NotificationTitle.Name = "NotificationTitle"
			NotificationTitle.Parent = NotificationFrame
			NotificationTitle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			NotificationTitle.BackgroundTransparency = 1.000
			NotificationTitle.Position = UDim2.new(0.0559394211, 0, 0.0652336925, 0)
			NotificationTitle.Size = UDim2.new(0, 272, 0, 26)
			NotificationTitle.ZIndex = 3
			NotificationTitle.Font = Enum.Font.Gotham
			NotificationTitle.Text = "Notification!!"
			NotificationTitle.TextColor3 = Color3.fromRGB(255, 255, 255)
			NotificationTitle.TextSize = 24.000
			NotificationTitle.ZIndex = 11
	
			NotificationDesc.Name = "NotificationDesc"
			NotificationDesc.Parent = NotificationFrame
			NotificationDesc.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			NotificationDesc.BackgroundTransparency = 1.000
			NotificationDesc.Position = UDim2.new(0.0670000017, 0, 0.218999997, 0)
			NotificationDesc.Size = UDim2.new(0, 274, 0, 146)
			NotificationDesc.Font = Enum.Font.Gotham
			NotificationDesc.TextColor3 = Color3.fromRGB(255, 255, 255)
			NotificationDesc.TextSize = 20.000
			NotificationDesc.TextWrapped = true
			NotificationDesc.TextXAlignment = Enum.TextXAlignment.Center
			NotificationDesc.TextYAlignment = Enum.TextYAlignment.Top
			NotificationDesc.ZIndex = 11
			NotificationDesc.Text = name
	
			OkayBtn.MouseEnter:Connect(
				function()
					TweenService:Create(
						OkayBtn,
						TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{BackgroundColor3 = Color3.fromRGB(37, 37, 37)}
					):Play()
				end
			)
	
			OkayBtn.MouseLeave:Connect(
				function()
					TweenService:Create(
						OkayBtn,
						TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),{BackgroundColor3 = Color3.fromRGB(34, 34, 34)}):Play()
				end
			)
	
			OkayBtn.MouseButton1Click:Connect(
				function()
					NotificationFrame:TweenSize(
						UDim2.new(0, 0, 0, 0),
						Enum.EasingDirection.Out,
						Enum.EasingStyle.Quart,
						.6,
						true
					)
					wait(0.4)
					TweenService:Create(
						NotificationHold,
						TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),{BackgroundTransparency = 1}):Play()
					wait(.3)
					NotificationHold:Destroy()
				end
			)
		end
	
		local Tabs = {}
		function Tabs:Tab(text,Real)
			if not Real or Real == nil then
				Real = false
			end
			RealName = ""
			if Real == true then
				RealName = "KakMoungMaiMee"
			elseif Real == false then
				RealName = "Tab"
			end
			local Tab = Instance.new("TextButton")
			local TabUICorner = Instance.new("UICorner")
	
			Tab.Name = RealName
			Tab.Parent = BalckGrouitList
			Tab.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
			Tab.Position = UDim2.new(0, 0, 0.137704924, 0)
			Tab.Size = UDim2.new(0, 115, 0, 25)
			Tab.Font = Enum.Font.SourceSansSemibold
			Tab.Text = text
			Tab.TextColor3 = Color3.fromRGB(109,109,109)
			Tab.TextSize = 20.000
			Tab.TextWrapped = true
			Tab.AutoButtonColor = false
			Tab.Visible = not Real
	
			TabUICorner.Name = "TabUICorner"
			TabUICorner.Parent = Tab
	
			local MainSection = Instance.new("ImageLabel")
			local SectionBorder = Instance.new("ImageLabel")
			local SectionTitle = Instance.new("TextLabel")
			local SectionContent = Instance.new("ScrollingFrame")
			local SectionContentLayout = Instance.new("UIListLayout")
	
			MainSection.Name = "MainSection"
			MainSection.Parent = SizeFullSection
			MainSection.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			MainSection.BackgroundTransparency = 1
			MainSection.Position = UDim2.new(0.0266666673, 0, 0.0343861282, 0)
			MainSection.Size = UDim2.new(0, 503, 0, 0)
			MainSection.ZIndex = 4
			MainSection.Image = "rbxassetid://3570695787"
			MainSection.ImageColor3 = Color3.fromRGB(10, 10, 10)
			MainSection.ScaleType = Enum.ScaleType.Slice
			MainSection.SliceCenter = Rect.new(100, 100, 100, 100)
			MainSection.SliceScale = 0.050
			MainSection.Visible = false
	
			SectionBorder.Name = "SectionBorder"
			SectionBorder.Parent = MainSection
			SectionBorder.BackgroundColor3 = Color3.fromRGB(255, 129, 129)
			SectionBorder.BackgroundTransparency = 1.000
			SectionBorder.Position = UDim2.new(0, -1, 0, -1)
			SectionBorder.Size = UDim2.new(1, 2, 1, 2)
			SectionBorder.ZIndex = 3
			SectionBorder.Image = "rbxassetid://3570695787"
			SectionBorder.ImageColor3 = Color3.fromRGB(255, 0, 0)
			SectionBorder.ScaleType = Enum.ScaleType.Slice
			SectionBorder.SliceCenter = Rect.new(100, 100, 100, 100)
			SectionBorder.SliceScale = 0.050
	
			SectionContent.Name = "SectionContent"
			SectionContent.Parent = MainSection
			SectionContent.Active = true
			SectionContent.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			SectionContent.BackgroundTransparency = 1.000
			SectionContent.BorderColor3 = Color3.fromRGB(27, 42, 53)
			SectionContent.BorderSizePixel = 0
			SectionContent.Position = UDim2.new(0, 0, 0.0350000001, 0)
			SectionContent.Size = UDim2.new(1, 0, 0.964999974, 0)
			SectionContent.ZIndex = 4
			SectionContent.BottomImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
			SectionContent.CanvasSize = UDim2.new(0, 0, 0, 0)
			SectionContent.ScrollBarThickness = 4
			SectionContent.TopImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
	
			function UpdateInputSearchText()
				local InputText = string.upper(TabSet.Text)
				for _,button in pairs(SectionContent:GetChildren())do
					if button:IsA("TextButton") or button:IsA("Frame") or button:IsA("TextLabel") then
						if InputText == "" or string.find(string.upper(button.Name),InputText) ~= nil then
							button.Visible = true
						else
							button.Visible = false
						end
					end
				end
			end
			TabSet.Changed:Connect(UpdateInputSearchText)
	
			SectionContentLayout.Name = "SectionContentLayout"
			SectionContentLayout.Parent = SectionContent
			SectionContentLayout.HorizontalAlignment = Enum.HorizontalAlignment.Center
			SectionContentLayout.SortOrder = Enum.SortOrder.LayoutOrder
			SectionContentLayout.Padding = UDim.new(0, 5)
	
			SectionContentLayout:GetPropertyChangedSignal("AbsoluteContentSize"):Connect(function()
				SectionContent.CanvasSize = UDim2.new(0,0,0,SectionContentLayout.AbsoluteContentSize.Y + 10 )
			end)
	
			if fspage == nil then
				fspage = true    
				MainSection.Visible = true
				TweenService:Create(MainSection, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 503, 0, 355)}):Play()
				TweenService:Create(Tab, TweenInfo.new(1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {BackgroundColor3 = Color3.fromRGB(10,10,10)}):Play()
				Tab.TextColor3 = ColorII
			end
	
			Tab.MouseButton1Click:Connect(function()
				for i, v in next, SizeFullSection:GetChildren() do
					if v.Name == "MainSection" then
						TweenService:Create(v, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 503, 0, 0)}):Play()
						v.Visible = false
					end
					MainSection.Visible = true
					TweenService:Create(MainSection, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 503, 0, 355)}):Play()
				end
				for i, v in next, BalckGrouitList:GetChildren() do
					if v.Name == "Tab" then
						TweenService:Create(v, TweenInfo.new(1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {TextColor3 = Color3.fromRGB(109,109,109)}):Play()
						TweenService:Create(v, TweenInfo.new(1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {BackgroundColor3 = Color3.fromRGB(20, 20, 20)}):Play()
					end
					TweenService:Create(Tab, TweenInfo.new(1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {TextColor3 = ColorII}):Play()
					TweenService:Create(Tab, TweenInfo.new(1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {BackgroundColor3 = Color3.fromRGB(10,10,10)}):Play()
				end
			end)
			
			HideTab.MouseButton1Click:connect(function()
				if HideTab.ImageTransparency == 0 then
					MainSection.Visible = false
					TweenService:Create(
						HideTab,
						TweenInfo.new(0.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{ImageTransparency = 0.3} -- UDim2.new(0, 128, 0, 25)
					):Play()
					TweenService:Create(
						HideTab,
						TweenInfo.new(0.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{Rotation = 90} -- UDim2.new(0, 128, 0, 25)
					):Play()
					for i,v in next,BalckGrouitList:GetChildren() do 
						if v.Name == "Tab" then
							v.Visible = false
						elseif v.Name == "KakMoungMaiMee" then
							v.Visible = true
						end
					end
				else
					MainSection.Visible = false
					TweenService:Create(
						HideTab,
						TweenInfo.new(0.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{ImageTransparency = 0} -- UDim2.new(0, 128, 0, 25)
					):Play()
					TweenService:Create(
						HideTab,
						TweenInfo.new(0.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{Rotation = 0} -- UDim2.new(0, 128, 0, 25)
					):Play()
					for i,v in next,BalckGrouitList:GetChildren() do 
						if v.Name == "Tab" then
							v.Visible = true
						elseif v.Name == "KakMoungMaiMee" then
							v.Visible = false
						end
					end
				end
			end)
	
			local TabElements = {}
	
			function TabElements:Button(text,callback)
				local NameButton = Instance.new("Frame")
				local Button = Instance.new("TextButton")
				local ButtonRounded = Instance.new("ImageLabel")
				local UICorner = Instance.new("UICorner")
				local UICorner_2 = Instance.new("UICorner")
	
				NameButton.Name = (text .. "Button")
				NameButton.Parent = SectionContent
				NameButton.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
				NameButton.Position = UDim2.new(0, 0, 0.122807018, 0)
				NameButton.Size = UDim2.new(0, 475, 0, 30)
				NameButton.ZIndex = 5
	
				Button.Name = "Button"
				Button.Parent = NameButton
				Button.BackgroundColor3 = Color3.fromRGB(255, 75, 75)
				Button.BackgroundTransparency = 1.000
				Button.BorderSizePixel = 0
				Button.ClipsDescendants = true
				Button.Position = UDim2.new(-0.000727273524, 0, 0, 0)
				Button.Size = UDim2.new(1, 0, 1, 0)
				Button.Text = text
				Button.ZIndex = 6
				Button.Font = Enum.Font.SourceSansBold
				Button.TextColor3 = Color3.fromRGB(185, 185, 185)
				Button.TextSize = 15.000
	
				ButtonRounded.Name = "ButtonRounded"
				ButtonRounded.Parent = Button
				ButtonRounded.Active = true
				ButtonRounded.AnchorPoint = Vector2.new(0.5, 0.5)
				ButtonRounded.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				ButtonRounded.BackgroundTransparency = 1.000
				ButtonRounded.Position = UDim2.new(0.5, 0, 0.5, 0)
				ButtonRounded.Selectable = true
				ButtonRounded.Size = UDim2.new(1, 0, 1, 0)
				ButtonRounded.ZIndex = 5
				ButtonRounded.Image = "rbxassetid://3570695787"
				ButtonRounded.ImageColor3 = Color3.fromRGB(255, 75, 75)
				ButtonRounded.ImageTransparency = 1.000
				ButtonRounded.ScaleType = Enum.ScaleType.Slice
				ButtonRounded.SliceCenter = Rect.new(100, 100, 100, 100)
				ButtonRounded.SliceScale = 0.050
	
				UICorner.Parent = NameButton
	
				UICorner_2.Parent = Button
	
				local Lock = Instance.new("Frame")
				local UICorner = Instance.new("UICorner")
				local lock = Instance.new("ImageButton")
	
				Lock.Name = "Lock"
				Lock.Parent = Button
				Lock.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
				Lock.BackgroundTransparency = 0.500
				Lock.Size = UDim2.new(1, 0, 1, 0)
				Lock.ZIndex = 10
				Lock.Visible = false
	
				UICorner.Parent = Lock
	
				lock.Name = "lock"
				lock.Parent = Lock
				lock.AnchorPoint = Vector2.new(0.5, 0.5)
				lock.BackgroundTransparency = 1.000
				lock.Position = UDim2.new(0.525263131, -12, 0.899999976, -12)
				lock.Size = UDim2.new(0, 0, 0, 0)
				lock.ZIndex = 10
				lock.Image = "rbxassetid://3926305904"
				lock.ImageRectOffset = Vector2.new(4, 684)
				lock.ImageRectSize = Vector2.new(36, 36)
	
				Button.MouseButton1Down:Connect(function()
					if Lock.Visible == true then
						for i = 1,3 do
							TweenService:Create(lock, TweenInfo.new(0.05, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 10}):Play()
							wait(.1)
							TweenService:Create(lock, TweenInfo.new(0.05, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = -10}):Play()
							wait(.1)
						end
						TweenService:Create(lock, TweenInfo.new(0.05, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 0}):Play()
					else
						RippleEffect(Button)
						callback(Button)
					end
				end)
	
				Button.MouseEnter:connect(function()
					TweenService:Create(
						Button,
						TweenInfo.new(.2, Enum.EasingStyle.Quad),
						{TextColor3 = Color3.fromRGB(255, 0, 0)}
					):Play()
				end)
	
				Button.MouseLeave:connect(function()
					TweenService:Create(
						Button,
						TweenInfo.new(.2, Enum.EasingStyle.Quad),
						{TextColor3 = Color3.fromRGB(185, 185, 185)}
					):Play()
				end)
	
				Button.MouseButton1Up:Connect(function()
					TweenService:Create(ButtonRounded, TweenInfo.new(0.25, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {ImageColor3 = Color3.fromRGB(255, 255, 255)}):Play()
				end)
	
				Button.InputEnded:Connect(function(input)
					if input.UserInputType == Enum.UserInputType.MouseMovement then
						TweenService:Create(ButtonRounded, TweenInfo.new(0.25, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {ImageColor3 = Color3.fromRGB(255, 255, 255)}):Play()
					end
				end)
	
				local funcbutton = {}
	
				function funcbutton:Delete()
					NameButton:Destroy()
				end
				function funcbutton:Lock()
					Lock.Visible = true
					TweenService:Create(lock, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 25, 0, 25)}):Play()
				end
				function funcbutton:Unlock()
					TweenService:Create(lock, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 0, 0, 0)}):Play()
					wait(.5)
					Lock.Visible = false
				end
				return funcbutton
			end
	
			function TabElements:Toggle(text,stats,callback)
	
				if stats == nil then
					stats = false
				end
	
				local ToggleName = Instance.new("Frame")
				local Title = Instance.new("TextLabel")
				local Toggle = Instance.new("TextButton")
				local CheckboxOutline = Instance.new("ImageLabel")
				local UIGradient = Instance.new("UIGradient")
				local CheckboxTicked = Instance.new("ImageLabel")
				local UIGradient_2 = Instance.new("UIGradient")
				local TickCover = Instance.new("Frame")
				local UICorner = Instance.new("UICorner")
	
				ToggleName.Name = (text .. "Toggle")
				ToggleName.Parent = SectionContent
				ToggleName.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
				ToggleName.Size = UDim2.new(0, 475, 0, 35)
				ToggleName.ZIndex = 5
	
				Title.Name = "Title"
				Title.Parent = ToggleName
				Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Title.BackgroundTransparency = 1.000
				Title.BorderColor3 = Color3.fromRGB(27, 42, 53)
				Title.Position = UDim2.new(0, 13, 0, 0)
				Title.Size = UDim2.new(0, 149, 0, 35)
				Title.ZIndex = 5
				Title.Font = Enum.Font.SourceSansBold
				Title.Text = text
				Title.TextColor3 = Color3.fromRGB(185, 185, 185)
				Title.TextSize = 15.000
				Title.TextXAlignment = Enum.TextXAlignment.Left
	
				Toggle.Name = "Toggle"
				Toggle.Parent = ToggleName
				Toggle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Toggle.BackgroundTransparency = 1.000
				Toggle.Size = UDim2.new(1, 0, 1, 0)
				Toggle.ZIndex = 5
				Toggle.AutoButtonColor = false
				Toggle.Font = Enum.Font.SourceSansBold
				Toggle.Text = ""
				Toggle.TextColor3 = Color3.fromRGB(255, 255, 255)
				Toggle.TextSize = 14.000
	
				CheckboxOutline.Name = "CheckboxOutline"
				CheckboxOutline.Parent = Toggle
				CheckboxOutline.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				CheckboxOutline.BackgroundTransparency = 1.000
				CheckboxOutline.Position = UDim2.new(1, -35, 0.5, -12)
				CheckboxOutline.Size = UDim2.new(0, 24, 0, 24)
				CheckboxOutline.ZIndex = 5
				CheckboxOutline.Image = "http://www.roblox.com/asset/?id=5416796047"
	
				UIGradient.Color = ColorSequence.new{ColorSequenceKeypoint.new(0.00, ColorIIIII), ColorSequenceKeypoint.new(1.00, ColorIIIIII)}
				UIGradient.Parent = CheckboxOutline
	
				CheckboxTicked.Name = "CheckboxTicked"
				CheckboxTicked.Parent = Toggle
				CheckboxTicked.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				CheckboxTicked.BackgroundTransparency = 1.000
				CheckboxTicked.Position = UDim2.new(1, -35, 0.5, -12)
				CheckboxTicked.Size = UDim2.new(0, 24, 0, 24)
				CheckboxTicked.ZIndex = 5
				CheckboxTicked.Image = "http://www.roblox.com/asset/?id=5416796675"
	
				UIGradient_2.Color = ColorSequence.new{ColorSequenceKeypoint.new(0.00, ColorIIIII), ColorSequenceKeypoint.new(1.00, ColorIIIIII)}
				UIGradient_2.Parent = CheckboxTicked
	
				TickCover.Name = "TickCover"
				TickCover.Parent = Toggle
				TickCover.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
				TickCover.BorderSizePixel = 0
				TickCover.Position = UDim2.new(1, -30, 0.5, -7)
				TickCover.Size = UDim2.new(0, 14, 0, 14)
				TickCover.ZIndex = 5
	
				UICorner.Parent = ToggleName
	
				local Lock = Instance.new("Frame")
				local UICorner = Instance.new("UICorner")
				local lock = Instance.new("ImageButton")
	
				Lock.Name = "Lock"
				Lock.Parent = Toggle
				Lock.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
				Lock.BackgroundTransparency = 0.500
				Lock.Size = UDim2.new(1, 0, 1, 0)
				Lock.ZIndex = 10
				Lock.Visible = false
	
				UICorner.Parent = Lock
	
				lock.Name = "lock"
				lock.Parent = Lock
				lock.AnchorPoint = Vector2.new(0.5, 0.5)
				lock.BackgroundTransparency = 1.000
				lock.Position = UDim2.new(0.525263131, -12, 0.899999976, -12)
				lock.Size = UDim2.new(0, 0, 0, 0)
				lock.ZIndex = 10
				lock.Image = "rbxassetid://3926305904"
				lock.ImageRectOffset = Vector2.new(4, 684)
				lock.ImageRectSize = Vector2.new(36, 36)
	
				local function SetState(state)
					if state then
						TweenService:Create(Title, TweenInfo.new(0.12, Enum.EasingStyle.Quad, Enum.EasingDirection.In), {TextColor3 = Color3.fromRGB(255, 0, 0)}):Play()
						TweenService:Create(TickCover, TweenInfo.new(0.12, Enum.EasingStyle.Quad, Enum.EasingDirection.In), {Position = UDim2.new(1, -30, 0.5, -7), Size = UDim2.new(0, 0, 0, 0)}):Play()
					elseif not state then
						TweenService:Create(Title, TweenInfo.new(0.12, Enum.EasingStyle.Quad, Enum.EasingDirection.In), {TextColor3 = Color3.fromRGB(185, 185, 185)}):Play()
						TweenService:Create(TickCover, TweenInfo.new(0.12, Enum.EasingStyle.Quad, Enum.EasingDirection.In), {Position = UDim2.new(1, -30, 0.5, -7), Size = UDim2.new(0, 14, 0, 14)}):Play()
					end
					-- callback(Toggled)
				end
	
				if stats then
					SetState(stats)
					callback(stats)
				end
	
				Toggle.MouseButton1Down:Connect(function()
					if Lock.Visible == true then
						for i = 1,3 do
							TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 10}):Play()
							wait(.1)
							TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = -10}):Play()
							wait(.1)
						end
						TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 0}):Play()
					else
						Toggled = not Toggled
						SetState(Toggled)
						callback(Toggled)
					end
				end)
	
				local functoggle = {}
	
				function functoggle:Lock()
					Lock.Visible = true
					TweenService:Create(lock, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 25, 0, 25)}):Play()
				end
				function functoggle:Unlock()
					TweenService:Create(lock, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 0, 0, 0)}):Play()
					wait(.5)
					Lock.Visible = false
				end
				return functoggle
			end
	
			function TabElements:Slider(name, minimumvalue, maximumvalue, presetvalue, precisevalue, callback)
				local SliderDragging = false
				local StartingValue = presetvalue
	
				if StartingValue == nil then
					StartingValue = presetvalue
				end
	
				local SliderName = Instance.new("Frame")
				local Title = Instance.new("TextLabel")
				local SliderBackground = Instance.new("ImageLabel")
				local SliderIndicator = Instance.new("ImageLabel")
				local UIGradient = Instance.new("UIGradient")
				local CircleSelector = Instance.new("ImageLabel")
				local UICorner = Instance.new("UICorner")
				local SliderValue = Instance.new("ImageLabel")
				local Value = Instance.new("TextBox")
	
				SliderName.Name = (name.."Slider")
				SliderName.Parent = SectionContent
				SliderName.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
				SliderName.Position = UDim2.new(0.104166672, 0, 0.445901573, 0)
				SliderName.Size = UDim2.new(0, 475, 0, 50)
				SliderName.ZIndex = 5
	
				Title.Name = "Title"
				Title.Parent = SliderName
				Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Title.BackgroundTransparency = 1.000
				Title.BorderColor3 = Color3.fromRGB(27, 42, 53)
				Title.Position = UDim2.new(0, 10, 0, 0)
				Title.Size = UDim2.new(0, 121, 0, 35)
				Title.ZIndex = 5
				Title.Font = Enum.Font.SourceSansBold
				Title.Text = name
				Title.TextColor3 = Color3.fromRGB(185, 185, 185)
				Title.TextSize = 15.000
				Title.TextXAlignment = Enum.TextXAlignment.Left
	
				SliderBackground.Name = "SliderBackground"
				SliderBackground.Parent = SliderName
				SliderBackground.BackgroundColor3 = Color3.fromRGB(55, 55, 55)
				SliderBackground.BackgroundTransparency = 1.000
				SliderBackground.Position = UDim2.new(0.0199999996, 0, 0.699999988, 0)
				SliderBackground.Size = UDim2.new(0, 450, 0, 4)
				SliderBackground.ZIndex = 5
				SliderBackground.Image = "rbxassetid://3570695787"
				SliderBackground.ImageColor3 = Color3.fromRGB(55, 55, 55)
				SliderBackground.ScaleType = Enum.ScaleType.Slice
				SliderBackground.SliceCenter = Rect.new(100, 100, 100, 100)
				SliderBackground.SliceScale = 0.150
	
				SliderIndicator.Name = "SliderIndicator"
				SliderIndicator.Parent = SliderBackground
				SliderIndicator.BackgroundColor3 = Color3.fromRGB(55, 55, 55)
				SliderIndicator.BackgroundTransparency = 1.000
				SliderIndicator.Size = UDim2.new(((StartingValue or minimumvalue) - minimumvalue) / (maximumvalue - minimumvalue), 0, 1, 0)
				SliderIndicator.ZIndex = 5
				SliderIndicator.Image = "rbxassetid://3570695787"
				SliderIndicator.ScaleType = Enum.ScaleType.Slice
				SliderIndicator.SliceCenter = Rect.new(100, 100, 100, 100)
				SliderIndicator.SliceScale = 0.150
	
				UIGradient.Color = ColorSequence.new{ColorSequenceKeypoint.new(0.00, ColorIIIIIII), ColorSequenceKeypoint.new(1.00, ColorIIIIIIII)}
				UIGradient.Parent = SliderIndicator
	
				CircleSelector.Name = "CircleSelector"
				CircleSelector.Parent = SliderIndicator
				CircleSelector.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				CircleSelector.BackgroundTransparency = 1.000
				CircleSelector.Position = UDim2.new(0.986565471, -7, 0.75, -7)
				CircleSelector.Size = UDim2.new(0, 12, 0, 12)
				CircleSelector.ZIndex = 5
				CircleSelector.Image = "rbxassetid://3570695787"
	
				UICorner.Parent = SliderName
	
				SliderValue.Name = "SliderValue"
				SliderValue.Parent = SliderName
				SliderValue.BackgroundColor3 = Color3.fromRGB(65, 65, 65)
				SliderValue.BackgroundTransparency = 1.000
				SliderValue.Position = UDim2.new(0.899999976, -7, 0.400000006, -12)
				SliderValue.Size = UDim2.new(0, 40, 0, 19)
				SliderValue.ZIndex = 5
				SliderValue.Image = "rbxassetid://3570695787"
				SliderValue.ImageColor3 = Color3.fromRGB(65, 65, 65)
				SliderValue.ScaleType = Enum.ScaleType.Slice
				SliderValue.SliceCenter = Rect.new(100, 100, 100, 100)
				SliderValue.SliceScale = 0.030
	
				Value.Name = "999 hub"
				Value.Parent = SliderValue
				Value.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Value.BackgroundTransparency = 1.000
				Value.Size = UDim2.new(1, 0, 1, 0)
				Value.ZIndex = 5
				Value.Font = Enum.Font.SourceSansBold
				Value.Text = tostring(StartingValue or precisevalue and tonumber(string.format("%.2f", StartingValue)))
				Value.TextColor3 = Color3.fromRGB(255, 255, 255)
				Value.TextSize = 14.000
	
				local Lock = Instance.new("Frame")
				local UICorner = Instance.new("UICorner")
				local lock = Instance.new("ImageButton")
	
				Lock.Name = "Lock"
				Lock.Parent = SliderName
				Lock.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
				Lock.BackgroundTransparency = 0.500
				Lock.Size = UDim2.new(1, 0, 1, 0)
				Lock.ZIndex = 10
				Lock.Visible = false
	
				UICorner.Parent = Lock
	
				lock.Name = "lock"
				lock.Parent = Lock
				lock.AnchorPoint = Vector2.new(0.5, 0.5)
				lock.BackgroundTransparency = 1.000
				lock.Position = UDim2.new(0.525263131, -12, 0.899999976, -12)
				lock.Size = UDim2.new(0, 0, 0, 0)
				lock.ZIndex = 10
				lock.Image = "rbxassetid://3926305904"
				lock.ImageRectOffset = Vector2.new(4, 684)
				lock.ImageRectSize = Vector2.new(36, 36)
	
				SliderName.MouseEnter:connect(function()
					if Lock.Visible ~= true then
						TweenService:Create(
							Title,
							TweenInfo.new(.2, Enum.EasingStyle.Quad),
							{TextColor3 = Color3.fromRGB(255, 0, 0)}
						):Play()
					end
				end)
	
				SliderName.MouseLeave:connect(function()
					if Lock.Visible ~= true then
						TweenService:Create(
							Title,
							TweenInfo.new(.2, Enum.EasingStyle.Quad),
							{TextColor3 = Color3.fromRGB(185, 185, 185)}
						):Play()
					end
				end)
	
				local function Sliding(input)
					local SliderPosition = UDim2.new(math.clamp((input.Position.X - SliderBackground.AbsolutePosition.X) / SliderBackground.AbsoluteSize.X, 0, 1), 0, 1, 0)
					TweenService:Create(SliderIndicator, TweenInfo.new(0.2, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = SliderPosition}):Play()
	
					local NonSliderPreciseValue = math.floor(((SliderPosition.X.Scale * maximumvalue) / maximumvalue) * (maximumvalue - minimumvalue) + minimumvalue)
					local SliderPreciseValue = ((SliderPosition.X.Scale * maximumvalue) / maximumvalue) * (maximumvalue - minimumvalue) + minimumvalue
	
					local SlidingValue = (precisevalue and SliderPreciseValue or NonSliderPreciseValue)
					SlidingValue = tonumber(string.format("%.2f", SlidingValue))
	
					Value.Text = tostring(SlidingValue)
					callback(SlidingValue)
				end
	
				Value.FocusLost:Connect(function()
					if not tonumber(Value.Text) then
						Value.Text = tostring(StartingValue or precisevalue and tonumber(string.format("%.2f", StartingValue)))
					elseif Value.Text == "" or tonumber(Value.Text) <= minimumvalue then
						Value.Text = minimumvalue
					elseif Value.Text == "" or tonumber(Value.Text) >= maximumvalue then
						Value.Text = maximumvalue
					end
	
					TweenService:Create(SliderIndicator, TweenInfo.new(0.2, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(((tonumber(Value.Text) or minimumvalue) - minimumvalue) / (maximumvalue - minimumvalue), 0, 1, 0)}):Play()
					callback(tonumber(Value.Text))
				end)
	
	
				CircleSelector.InputBegan:Connect(function(input)
					if input.UserInputType == Enum.UserInputType.MouseButton1 then
						if Lock.Visible == true then
							for i = 1,3 do
								TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 10}):Play()
								wait(.1)
								TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = -10}):Play()
								wait(.1)
							end
							TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 0}):Play()
						else
							SliderDragging = true
						end
					end
				end)
	
				CircleSelector.InputEnded:Connect(function(input)
					if input.UserInputType == Enum.UserInputType.MouseButton1 then
						if Lock.Visible == true then
							for i = 1,3 do
								TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 10}):Play()
								wait(.1)
								TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = -10}):Play()
								wait(.1)
							end
							TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 0}):Play()
						else
							SliderDragging = false
						end
					end
				end)
	
				CircleSelector.InputBegan:Connect(function(input)
					if input.UserInputType == Enum.UserInputType.MouseButton1 then
						if Lock.Visible == true then
							for i = 1,3 do
								TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 10}):Play()
								wait(.1)
								TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = -10}):Play()
								wait(.1)
							end
							TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 0}):Play()
						else
							Sliding(input)
						end
					end
				end)
	
				UserInputService.InputChanged:Connect(function(input)
					if SliderDragging and input.UserInputType == Enum.UserInputType.MouseMovement then
						if Lock.Visible == true then
							for i = 1,3 do
								TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 10}):Play()
								wait(.1)
								TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = -10}):Play()
								wait(.1)
							end
							TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 0}):Play()
						else
							Sliding(input)
						end
					end
				end)
				local function SetSliderValue(value)
					if Lock.Visible == true then
						for i = 1,3 do
							TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 10}):Play()
							wait(.1)
							TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = -10}):Play()
							wait(.1)
						end
						TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 0}):Play()
					else
						Value.Text = value
						TweenService:Create(SliderIndicator, TweenInfo.new(0.02, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(((tonumber(Value.Text) or minimumvalue) - minimumvalue) / (maximumvalue - minimumvalue), 0, 1, 0)}):Play()
						callback(tonumber(Value.Text))
					end
				end
				callback(StartingValue)
				local funcSli = {}
	
				function funcSli:Lock()
					Lock.Visible = true
					TweenService:Create(lock, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 25, 0, 25)}):Play()
				end
				function funcSli:Unlock()
					TweenService:Create(lock, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new...
