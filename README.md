# What is this?
This is a ROBLOX Teleport Anti-Cheat bypass, (meant for exploiting)

# How do I use this?
Simply, get the coordinates you wanna teleport to (Vector3, not a CFrame), and replace the parameters at the bottom with the coordinates.

# Script
```lua
--0xPeeps Teleport Bypass! (Works with most likely any game)--
local plr = game:service"Players".LocalPlayer;
local tween_s = game:service"TweenService";
local info = TweenInfo.new(5,Enum.EasingStyle.Quad); --Everytime I tried going under 5, I got kicked/detected
function tp(...)
   local tic_k = tick();
   local params = {...};
   local cframe = CFrame.new(params[1],params[2],params[3]);
   local tween,err = pcall(function()
       local tween = tween_s:Create(plr.Character["HumanoidRootPart"],info,{CFrame=cframe});
       tween:Play();
   end)
   if not tween then return err end
end
tp(position/coords go here!);
```

# How do I get Vector3 coordinates?
Heres a method of collection, that works for the popular ROBLOX Exploit, SynapseX. This script copies your current Vector3 coordinates to your clipboard, so all you have to do is stand where you want to teleport later on, & execute the script.
```lua
local plr = game:service"Players".LocalPlayer;
syn.write_clipboard(tostring(plr.Character["HumanoidRootPart"].Position));
```
