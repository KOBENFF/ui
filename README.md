local ScreenGui = Instance.new("ScreenGui")
local MainFrame = Instance.new("Frame")
local UICorner = Instance.new("UICorner")
local TabOverview = Instance.new("Frame")
local UICorner_2 = Instance.new("UICorner")
local TabLv = Instance.new("TextLabel")
local UICorner_3 = Instance.new("UICorner")
local ShowLevel = Instance.new("TextLabel")
local Beli = Instance.new("TextLabel")
local UICorner_4 = Instance.new("UICorner")
local ShowBeli = Instance.new("TextLabel")
local Fragment = Instance.new("TextLabel")
local UICorner_5 = Instance.new("UICorner")
local ShowFragment = Instance.new("TextLabel")
local View = Instance.new("TextLabel")
local HUB = Instance.new("Frame")
local UICorner_6 = Instance.new("UICorner")
local LogoHub = Instance.new("ImageLabel")
local NameHub = Instance.new("TextLabel")
local TabProfileImage = Instance.new("Frame")
local UICorner_7 = Instance.new("UICorner")
local ProfileImage = Instance.new("ImageLabel")
local ProfileName = Instance.new("TextLabel")

local UserInputService = game:GetService("UserInputService")
local TweenService = game:GetService("TweenService")
local RunService = game:GetService("RunService")
local LocalPlayer = game:GetService("Players").LocalPlayer
local Mouse = LocalPlayer:GetMouse()
function dragify(Frame, object)
	dragToggle = nil
	dragSpeed = .25
	dragInput = nil
	dragStart = nil
	dragPos = nil
	function updateInput(input)
		Delta = input.Position - dragStart
		Position =
			UDim2.new(startPos.X.Scale, startPos.X.Offset + Delta.X, startPos.Y.Scale, startPos.Y.Offset + Delta.Y)
		game:GetService("TweenService"):Create(object, TweenInfo.new(dragSpeed), {Position = Position}):Play()
	end
	Frame.InputBegan:Connect(
		function(input)
			if
				(input.UserInputType == Enum.UserInputType.MouseButton1 or
					input.UserInputType == Enum.UserInputType.Touch)
			then
				dragToggle = true
				dragStart = input.Position
				startPos = object.Position
				input.Changed:Connect(
					function()
						if (input.UserInputState == Enum.UserInputState.End) then
							dragToggle = false
						end
					end
				)
			end
		end
	)
	Frame.InputChanged:Connect(
		function(input)
			if
				(input.UserInputType == Enum.UserInputType.MouseMovement or
					input.UserInputType == Enum.UserInputType.Touch)
			then
				dragInput = input
			end
		end
	)
	game:GetService("UserInputService").InputChanged:Connect(
	function(input)
		if (input == dragInput and dragToggle) then
			updateInput(input)
		end
	end
	)
end

ScreenGui.Parent = game.CoreGui
ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

MainFrame.Name = "MainFrame"
MainFrame.Parent = ScreenGui
MainFrame.BackgroundColor3 = Color3.fromRGB(15, 15, 15)
MainFrame.BackgroundTransparency = 0.300
MainFrame.BorderColor3 = Color3.fromRGB(0, 0, 0)
MainFrame.BorderSizePixel = 0
MainFrame.Position = UDim2.new(0.128192514, 0, 0.100760885, 0)
MainFrame.Size = UDim2.new(0.702596784, 0, 0.766225994, 0)

UICorner.CornerRadius = UDim.new(0, 12)
UICorner.Parent = MainFrame

TabOverview.Name = "TabOverview"
TabOverview.Parent = MainFrame
TabOverview.BackgroundColor3 = Color3.fromRGB(21, 21, 21)
TabOverview.BackgroundTransparency = 0.500
TabOverview.BorderColor3 = Color3.fromRGB(0, 0, 0)
TabOverview.BorderSizePixel = 0
TabOverview.Position = UDim2.new(0.0227297191, 0, 0.0957831591, 0)
TabOverview.Size = UDim2.new(0.571555257, 0, 0.451872051, 0)

UICorner_2.CornerRadius = UDim.new(0, 9)
UICorner_2.Parent = TabOverview

TabLv.Name = "TabLv"
TabLv.Parent = TabOverview
TabLv.BackgroundColor3 = Color3.fromRGB(106, 0, 255)
TabLv.BorderColor3 = Color3.fromRGB(0, 0, 0)
TabLv.BorderSizePixel = 0
TabLv.Position = UDim2.new(0.0603236631, 0, 0.0789522827, 0)
TabLv.Size = UDim2.new(0.251939982, 0, 0.111181207, 0)
TabLv.Font = Enum.Font.SourceSans
TabLv.Text = "LEVEL"
TabLv.TextColor3 = Color3.fromRGB(255, 255, 255)
TabLv.TextScaled = true
TabLv.TextSize = 14.000
TabLv.TextWrapped = true

UICorner_3.CornerRadius = UDim.new(0, 60)
UICorner_3.Parent = TabLv

ShowLevel.Name = "ShowLevel"
ShowLevel.Parent = TabLv
ShowLevel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
ShowLevel.BackgroundTransparency = 1.000
ShowLevel.BorderColor3 = Color3.fromRGB(0, 0, 0)
ShowLevel.BorderSizePixel = 0
ShowLevel.Position = UDim2.new(0.0798121765, 0, 1.36561954, 0)
ShowLevel.Size = UDim2.new(0.633801222, 0, 1.09249568, 0)
ShowLevel.Font = Enum.Font.SourceSans
ShowLevel.Text = "1"
ShowLevel.TextColor3 = Color3.fromRGB(255, 255, 255)
ShowLevel.TextSize = 15.000
ShowLevel.TextXAlignment = Enum.TextXAlignment.Left

Beli.Name = "Beli"
Beli.Parent = TabOverview
Beli.BackgroundColor3 = Color3.fromRGB(106, 0, 255)
Beli.BorderColor3 = Color3.fromRGB(0, 0, 0)
Beli.BorderSizePixel = 0
Beli.Position = UDim2.new(0.371995747, 0, 0.0789522827, 0)
Beli.Size = UDim2.new(0.251939982, 0, 0.111181207, 0)
Beli.Font = Enum.Font.SourceSans
Beli.Text = "BELI"
Beli.TextColor3 = Color3.fromRGB(255, 255, 255)
Beli.TextScaled = true
Beli.TextSize = 14.000
Beli.TextWrapped = true

UICorner_4.CornerRadius = UDim.new(0, 60)
UICorner_4.Parent = Beli

ShowBeli.Name = "ShowBeli"
ShowBeli.Parent = Beli
ShowBeli.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
ShowBeli.BackgroundTransparency = 1.000
ShowBeli.BorderColor3 = Color3.fromRGB(0, 0, 0)
ShowBeli.BorderSizePixel = 0
ShowBeli.Position = UDim2.new(0.0798121765, 0, 1.36561954, 0)
ShowBeli.Size = UDim2.new(0.633801222, 0, 1.09249568, 0)
ShowBeli.Font = Enum.Font.SourceSans
ShowBeli.Text = "9999"
ShowBeli.TextColor3 = Color3.fromRGB(255, 255, 255)
ShowBeli.TextSize = 15.000
ShowBeli.TextXAlignment = Enum.TextXAlignment.Left

Fragment.Name = "Fragment"
Fragment.Parent = TabOverview
Fragment.BackgroundColor3 = Color3.fromRGB(106, 0, 255)
Fragment.BorderColor3 = Color3.fromRGB(0, 0, 0)
Fragment.BorderSizePixel = 0
Fragment.Position = UDim2.new(0.670262635, 0, 0.0728790388, 0)
Fragment.Size = UDim2.new(0.251939982, 0, 0.111181207, 0)
Fragment.Font = Enum.Font.SourceSans
Fragment.Text = "FRAGMENT"
Fragment.TextColor3 = Color3.fromRGB(255, 255, 255)
Fragment.TextScaled = true
Fragment.TextSize = 14.000
Fragment.TextWrapped = true

UICorner_5.CornerRadius = UDim.new(0, 60)
UICorner_5.Parent = Fragment

ShowFragment.Name = "ShowFragment"
ShowFragment.Parent = Fragment
ShowFragment.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
ShowFragment.BackgroundTransparency = 1.000
ShowFragment.BorderColor3 = Color3.fromRGB(0, 0, 0)
ShowFragment.BorderSizePixel = 0
ShowFragment.Position = UDim2.new(0.0798121765, 0, 1.36561954, 0)
ShowFragment.Size = UDim2.new(0.633801222, 0, 1.09249568, 0)
ShowFragment.Font = Enum.Font.SourceSans
ShowFragment.Text = "0"
ShowFragment.TextColor3 = Color3.fromRGB(255, 255, 255)
ShowFragment.TextSize = 15.000
ShowFragment.TextXAlignment = Enum.TextXAlignment.Left

View.Name = "View"
View.Parent = MainFrame
View.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
View.BackgroundTransparency = 1.000
View.BorderColor3 = Color3.fromRGB(0, 0, 0)
View.BorderSizePixel = 0
View.Position = UDim2.new(0.0355493128, 0, -0.00226128963, 0)
View.Size = UDim2.new(0.227491155, 0, 0.0982039645, 0)
View.Font = Enum.Font.SourceSans
View.Text = "OVERVIEW"
View.TextColor3 = Color3.fromRGB(255, 255, 255)
View.TextScaled = true
View.TextSize = 14.000
View.TextWrapped = true

HUB.Name = "HUB"
HUB.Parent = MainFrame
HUB.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
HUB.BackgroundTransparency = 0.500
HUB.BorderColor3 = Color3.fromRGB(0, 0, 0)
HUB.BorderSizePixel = 0
HUB.Position = UDim2.new(0.611117959, 0, 0.0630648211, 0)
HUB.Size = UDim2.new(0.353152812, 0, 0.484590381, 0)

UICorner_6.CornerRadius = UDim.new(0, 10)
UICorner_6.Parent = HUB

LogoHub.Name = "LogoHub"
LogoHub.Parent = HUB
LogoHub.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
LogoHub.BackgroundTransparency = 1.000
LogoHub.BorderColor3 = Color3.fromRGB(0, 0, 0)
LogoHub.BorderSizePixel = 0
LogoHub.Position = UDim2.new(-1.67337745e-07, 0, -0.127353966, 0)
LogoHub.Size = UDim2.new(0.999999583, 0, 0.837729216, 0)
LogoHub.Image = "rbxassetid://18777779691"

NameHub.Name = "NameHub"
NameHub.Parent = HUB
NameHub.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
NameHub.BackgroundTransparency = 1.000
NameHub.BorderColor3 = Color3.fromRGB(0, 0, 0)
NameHub.BorderSizePixel = 0
NameHub.Position = UDim2.new(0.104183145, 0, 0.611430049, 0)
NameHub.Size = UDim2.new(0.784170449, 0, 0.298166573, 0)
NameHub.Font = Enum.Font.SourceSans
NameHub.Text = "Kenon Hub Kaitun"
NameHub.TextColor3 = Color3.fromRGB(255, 255, 255)
NameHub.TextScaled = true
NameHub.TextSize = 14.000
NameHub.TextWrapped = true

TabProfileImage.Name = "TabProfileImage"
TabProfileImage.Parent = MainFrame
TabProfileImage.BackgroundColor3 = Color3.fromRGB(21, 21, 21)
TabProfileImage.BackgroundTransparency = 0.300
TabProfileImage.BorderColor3 = Color3.fromRGB(0, 0, 0)
TabProfileImage.BorderSizePixel = 0
TabProfileImage.Position = UDim2.new(0.966207027, 0, 0.584125817, 0)
TabProfileImage.Size = UDim2.new(-0.354288518, 0, 0.37515077, 0)

UICorner_7.CornerRadius = UDim.new(0, 10)
UICorner_7.Parent = TabProfileImage

ProfileImage.Name = "ProfileImage"
ProfileImage.Parent = TabProfileImage
ProfileImage.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
ProfileImage.BackgroundTransparency = 1.000
ProfileImage.BorderColor3 = Color3.fromRGB(0, 0, 0)
ProfileImage.BorderSizePixel = 0
ProfileImage.Position = UDim2.new(0.058842171, 0, 0.0678329766, 0)
ProfileImage.Size = UDim2.new(0.862538278, 0, 0.852757394, 0)
ProfileImage.Image = "https://www.roblox.com/headshot-thumbnail/image?userId=" .. game.Players.LocalPlayer.UserId .. "&width=420&height=420&format=png

dragify(MainFrame, MainFrame)

ProfileName.Name = "ProfileName"
ProfileName.Parent = ProfileImage
ProfileName.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
ProfileName.BackgroundTransparency = 1.000
ProfileName.BorderColor3 = Color3.fromRGB(0, 0, 0)
ProfileName.BorderSizePixel = 0
ProfileName.Position = UDim2.new(0.10138905, 0, 0, 0)
ProfileName.Size = UDim2.new(0.785765111, 0, 0.318181813, 0)
ProfileName.Font = Enum.Font.SourceSans
ProfileName.Text = ""..game.Players.LocalPlayer.Name
ProfileName.TextColor3 = Color3.fromRGB(255, 255, 255)
ProfileName.TextSize = 20.000
ProfileName.TextWrapped = true
