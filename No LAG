local ToDisable = {
	Textures = true,
	VisualEffects = true,
	Parts = true,
	Particles = true,
	Sky = true
}

local ToEnable = {
	FullBright = false
}

local Stuff = {}

for _, v in next, game:GetDescendants() do
	if ToDisable.Parts then
		if v:IsA("Part") or v:IsA("Union") or v:IsA("BasePart") then
			v.Material = Enum.Material.SmoothPlastic
			table.insert(Stuff, 1, v)
		end
	end
	
	if ToDisable.Particles then
		if v:IsA("ParticleEmitter") or v:IsA("Smoke") or v:IsA("Explosion") or v:IsA("Sparkles") or v:IsA("Fire") then
			v.Enabled = false
			table.insert(Stuff, 1, v)
		end
	end
	
	if ToDisable.VisualEffects then
		if v:IsA("BloomEffect") or v:IsA("BlurEffect") or v:IsA("DepthOfFieldEffect") or v:IsA("SunRaysEffect") then
			v.Enabled = false
			table.insert(Stuff, 1, v)
		end
	end
	
	if ToDisable.Textures then
		if v:IsA("Decal") or v:IsA("Texture") then
			v.Texture = ""
			table.insert(Stuff, 1, v)
		end
	end
	
	if ToDisable.Sky then
		if v:IsA("Sky") then
			v.Parent = nil
			table.insert(Stuff, 1, v)
		end
	end
end

game:GetService("TestService"):Message("Effects Disabler Script : Successfully disabled "..#Stuff.." assets / effects. Settings :")

for i, v in next, ToDisable do
	print(tostring(i)..": "..tostring(v))
end

if ToEnable.FullBright then
    local Lighting = game:GetService("Lighting")
    
    Lighting.FogColor = Color3.fromRGB(255, 255, 255)
    Lighting.FogEnd = math.huge
    Lighting.FogStart = math.huge
    Lighting.Ambient = Color3.fromRGB(255, 255, 255)
    Lighting.Brightness = 5
    Lighting.ColorShift_Bottom = Color3.fromRGB(255, 255, 255)
    Lighting.ColorShift_Top = Color3.fromRGB(255, 255, 255)
    Lighting.OutdoorAmbient = Color3.fromRGB(255, 255, 255)
    Lighting.Outlines = true
end

_G.Stop = false  --stop the script
local function FOV()
    if game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("CameraPositioner") then 
        game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("CameraPositioner"):Destroy()
    end
    local part = Instance.new("Part")
    part.Name = "CameraPositioner"
    part.Anchored = true 
    part.Parent = game.Players.LocalPlayer.Character.HumanoidRootPart
    part.CanCollide = false
    game:GetService("RunService").RenderStepped:Connect(function()
        part.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame*CFrame.new(1,-100000000,-100)
    end)
    local camera = workspace.CurrentCamera
    camera.CameraSubject = part
    for _,v in pairs(workspace:GetDescendants()) do 
    if v:IsA("ParticleEmitter") then 
        v:Destroy()
    end 
    if v:IsA("Decal") then v:Destroy() end 
    if v:IsA("BasePart") then v.Material = Enum.Material.SmoothPlastic end  
    end 
    if _G.Stop then 
        camera.CameraSubject=game.Players.LocalPlayer.Character.Humanoid
    end 
end 

FOV() 

getgenv().Resolution = {
    [".gg/scripters"] = 0.55
}

local Camera = workspace.CurrentCamera
if getgenv().gg_scripters == nil then
    game:GetService("RunService").RenderStepped:Connect(
        function()
            Camera.CFrame = Camera.CFrame * CFrame.new(0, 0, 0, 1, 0, 0, 0, getgenv().Resolution[".gg/scripters"], 0, 0, 0, 1)
        end
    )
end
getgenv().gg_scripters = "Aori0001"

loadstring(game:HttpGet('https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source'))()

game.Lighting.FogEnd = 9999999999 -- stops fog (annoying)
	wait(1)
	for i,v in pairs(game:GetService("Lighting"):GetChildren()) do
        if v:IsA("PostEffect") then
            v:Destroy()
        end
	    end
	wait(1)
	game.Lighting.Blur.Size = 0 -- stops blur (cancer)

gethui().VulkanUI.AspectFrame.DragFrame.Contents.Pages.Console.Parent = nil
gethui().VulkanUI.AspectFrame.DragFrame.Contents.Buttons.ScrollingFrame.Console.Parent = nil
