local GUI = Instance.new("ScreenGui")
local OpenUi = Instance.new("ImageButton")
local UICorner = Instance.new("UICorner")
local MainFrame = Instance.new("Frame")
local UICorner_2 = Instance.new("UICorner")
local Logo = Instance.new("ImageLabel")
local NameHub = Instance.new("TextLabel")
local GeneralTab = Instance.new("TextButton")
local Page1 = Instance.new("ScrollingFrame")
local ProfileName = Instance.new("TextLabel")
local ProfileImage = Instance.new("ImageLabel")
local UICorner_3 = Instance.new("UICorner")
local Page2 = Instance.new("ScrollingFrame")
local locallv = Instance.new("TextLabel")
local localrace = Instance.new("TextLabel")
local localbeli = Instance.new("TextLabel")
local localDevil = Instance.new("TextLabel")
local CalseUI = Instance.new("ImageButton")
local UICorner_4 = Instance.new("UICorner")
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
GUI.Name = "GUI"
GUI.Parent = game.CoreGui
GUI.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

OpenUi.Name = "OpenUi"
OpenUi.Parent = GUI
OpenUi.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
OpenUi.BorderColor3 = Color3.fromRGB(0, 0, 0)
OpenUi.BorderSizePixel = 0
OpenUi.Position = UDim2.new(0.0557823181, 0, 0.0779944062, 0)
OpenUi.Size = UDim2.new(0.0883723348, 0, 0.155777574, 0)
OpenUi.Image = "rbxassetid://15640661640"

UICorner.CornerRadius = UDim.new(0, 50)
UICorner.Parent = OpenUi

MainFrame.Name = "MainFrame"
MainFrame.Parent = OpenUi
MainFrame.BackgroundColor3 = Color3.fromRGB(13, 13, 13)
MainFrame.BorderColor3 = Color3.fromRGB(0, 0, 0)
MainFrame.BorderSizePixel = 0
MainFrame.Position = UDim2.new(1.69351482, 0, -0.447033942, 0)
MainFrame.Size = UDim2.new(6.70469475, 0, 5.08903551, 0)

UICorner_2.CornerRadius = UDim.new(0, 10)
UICorner_2.Parent = MainFrame

Logo.Name = "Logo"
Logo.Parent = MainFrame
Logo.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Logo.BackgroundTransparency = 1.000
Logo.BorderColor3 = Color3.fromRGB(0, 0, 0)
Logo.BorderSizePixel = 0
Logo.Position = UDim2.new(0.0265957452, 0, 0.00787401572, 0)
Logo.Size = UDim2.new(0.101063833, 0, 0.133858263, 0)
Logo.Image = "rbxassetid://16663324629"

NameHub.Name = "Name Hub"
NameHub.Parent = MainFrame
NameHub.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
NameHub.BackgroundTransparency = 1.000
NameHub.BorderColor3 = Color3.fromRGB(0, 0, 0)
NameHub.BorderSizePixel = 0
NameHub.Position = UDim2.new(0.143617019, 0, 0, 0)
NameHub.Size = UDim2.new(0.25, 0, 0.133858263, 0)
NameHub.Font = Enum.Font.SourceSans
NameHub.Text = "Attack Hub I "
NameHub.TextColor3 = Color3.fromRGB(255, 255, 255)
NameHub.TextScaled = true
NameHub.TextSize = 14.000
NameHub.TextWrapped = true

GeneralTab.Name = "GeneralTab"
GeneralTab.Parent = MainFrame
GeneralTab.BackgroundColor3 = Color3.fromRGB(16, 16, 16)
GeneralTab.BorderColor3 = Color3.fromRGB(0, 0, 0)
GeneralTab.BorderSizePixel = 0
GeneralTab.Position = UDim2.new(0.409574479, 0, 0.032214772, 0)
GeneralTab.Size = UDim2.new(0.182205766, 0, 0.0780214593, 0)
GeneralTab.Font = Enum.Font.SourceSans
GeneralTab.Text = "General"
GeneralTab.TextColor3 = Color3.fromRGB(255, 255, 255)
GeneralTab.TextScaled = true
GeneralTab.TextSize = 14.000
GeneralTab.TextWrapped = true

Page1.Name = "Page1"
Page1.Parent = MainFrame
Page1.Active = true
Page1.BackgroundColor3 = Color3.fromRGB(16, 16, 16)
Page1.BorderColor3 = Color3.fromRGB(0, 0, 0)
Page1.BorderSizePixel = 0
Page1.Position = UDim2.new(0.0265958253, 0, 0.145370483, 0)
Page1.Size = UDim2.new(0.450492531, 0, 0.821030021, 0)

ProfileName.Name = "ProfileName"
ProfileName.Parent = Page1
ProfileName.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
ProfileName.BackgroundTransparency = 1.000
ProfileName.BorderColor3 = Color3.fromRGB(0, 0, 0)
ProfileName.BorderSizePixel = 0
ProfileName.Position = UDim2.new(0.0356802382, 0, 0.138594255, 0)
ProfileName.Size = UDim2.new(0.642244279, 0, 0.0513555445, 0)
ProfileName.Font = Enum.Font.SourceSans
ProfileName.Text = "Name :"..game.Players.LocalPlayer.Name
ProfileName.TextColor3 = Color3.fromRGB(255, 255, 255)
ProfileName.TextSize = 18.000
ProfileName.TextWrapped = true
ProfileName.TextXAlignment = Enum.TextXAlignment.Left

ProfileImage.Name = "ProfileImage"
ProfileImage.Parent = Page1
ProfileImage.BackgroundColor3 = Color3.fromRGB(255, 85, 127)
ProfileImage.BorderColor3 = Color3.fromRGB(0, 0, 0)
ProfileImage.BorderSizePixel = 0
ProfileImage.Position = UDim2.new(0.0359028354, 0, -0.000995887443, 0)
ProfileImage.Size = UDim2.new(0, 69, 0, 63)
ProfileImage.Image = "https://www.roblox.com/headshot-thumbnail/image?userId=" .. game.Players.LocalPlayer.UserId .. "&width=420&height=420&format=png"

UICorner_3.CornerRadius = UDim.new(0, 50)
UICorner_3.Parent = ProfileImage
dragify(MainFrame, MainFrame)
Page2.Name = "Page2"
Page2.Parent = MainFrame
Page2.Active = true
Page2.BackgroundColor3 = Color3.fromRGB(16, 16, 16)
Page2.BorderColor3 = Color3.fromRGB(0, 0, 0)
Page2.BorderSizePixel = 0
Page2.Position = UDim2.new(0.538215816, 0, 0.141433507, 0)
Page2.Size = UDim2.new(0.427159727, 0, 0.821029961, 0)

locallv.Name = "locallv"
locallv.Parent = Page2
locallv.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
locallv.BackgroundTransparency = 1.000
locallv.BorderColor3 = Color3.fromRGB(0, 0, 0)
locallv.BorderSizePixel = 0
locallv.Position = UDim2.new(0.0835677236, 0, 0.00164613186, 0)
locallv.Size = UDim2.new(0.642244279, 0, 0.0513555445, 0)
locallv.Font = Enum.Font.SourceSans
locallv.Text = "Level : "..game:GetService("Players").LocalPlayer.Data.Level.Value
locallv.TextColor3 = Color3.fromRGB(255, 255, 255)
locallv.TextSize = 18.000
locallv.TextWrapped = true
locallv.TextXAlignment = Enum.TextXAlignment.Left

localrace.Name = "localrace"
localrace.Parent = Page2
localrace.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
localrace.BackgroundTransparency = 1.000
localrace.BorderColor3 = Color3.fromRGB(0, 0, 0)
localrace.BorderSizePixel = 0
localrace.Position = UDim2.new(0.0835677236, 0, 0.0724840015, 0)
localrace.Size = UDim2.new(0.642244279, 0, 0.0513555445, 0)
localrace.Font = Enum.Font.SourceSans
localrace.Text = "Race : "..game:GetService("Players").LocalPlayer.Data.Race.Value
localrace.TextColor3 = Color3.fromRGB(255, 255, 255)
localrace.TextSize = 18.000
localrace.TextWrapped = true
localrace.TextXAlignment = Enum.TextXAlignment.Left

localbeli.Name = "localbeli"
localbeli.Parent = Page2
localbeli.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
localbeli.BackgroundTransparency = 1.000
localbeli.BorderColor3 = Color3.fromRGB(0, 0, 0)
localbeli.BorderSizePixel = 0
localbeli.Position = UDim2.new(0.0835677236, 0, 0.146611065, 0)
localbeli.Size = UDim2.new(0.642244279, 0, 0.0513555445, 0)
localbeli.Font = Enum.Font.SourceSans
localbeli.Text = "Beli : "..game:GetService("Players").LocalPlayer.Data.Beli.Value
localbeli.TextColor3 = Color3.fromRGB(255, 255, 255)
localbeli.TextSize = 18.000
localbeli.TextWrapped = true
localbeli.TextXAlignment = Enum.TextXAlignment.Left

localDevil.Name = "localDevil"
localDevil.Parent = Page2
localDevil.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
localDevil.BackgroundTransparency = 1.000
localDevil.BorderColor3 = Color3.fromRGB(0, 0, 0)
localDevil.BorderSizePixel = 0
localDevil.Position = UDim2.new(0.0835677236, 0, 0.22864534, 0)
localDevil.Size = UDim2.new(0.642244279, 0, 0.0513555445, 0)
localDevil.Font = Enum.Font.SourceSans
localDevil.Text = "Fragments : "..game:GetService("Players").LocalPlayer.Data.Fragments.Value
localDevil.TextColor3 = Color3.fromRGB(255, 255, 255)
localDevil.TextSize = 18.000
localDevil.TextWrapped = true
localDevil.TextXAlignment = Enum.TextXAlignment.Left

CalseUI.Name = "CalseUI"
CalseUI.Parent = MainFrame
CalseUI.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
CalseUI.BorderColor3 = Color3.fromRGB(0, 0, 0)
CalseUI.BorderSizePixel = 0
CalseUI.Position = UDim2.new(-0.259288669, 0, 0.0664862916, 0)
CalseUI.Size = UDim2.new(0.155851468, 0, 0.219915196, 0)
CalseUI.Image = "rbxassetid://15640661640"

UICorner_4.CornerRadius = UDim.new(0, 50)
UICorner_4.Parent = CalseUI

local function LZTULYY_fake_script()
	local script = Instance.new('LocalScript', CalseUI)

	local function KOBEN ()
		script.Parent.Parent.Parent.MainFrame.Visible = false
	end
	script.Parent.MouseButton1Click:Connect(KOBEN)
end
coroutine.wrap(LZTULYY_fake_script)()
local function DBLY_fake_script()
	local script = Instance.new('LocalScript', OpenUi)

	local function Ruok1 ()
		script.Parent.MainFrame.Visible = true
	end
	script.Parent.MouseButton1Click:Connect(Ruok1)
end
coroutine.wrap(DBLY_fake_script)()
