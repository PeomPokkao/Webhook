_G.P = true
repeat wait(300)
x = "https://discord.com/api/webhooks/1189784944512344074/ScClwE2IpUlwUOMyuqp09EEap3I9hlIeyOxXaFkZv0cJw5cnVKeEOF_mzicUd0v_rJNF"
local HttpService = game:GetService("HttpService");
game:GetService("Players").LocalPlayer.PlayerGui.Main.AwakeningToggler.Visible = true
local function Fornum(number)
   local i, k, j = tostring(number):match("(%-?%d?)(%d*)(%.?.*)")
   return i..k:reverse():gsub("(%d%d%d)", "%1,"):reverse()..j
end
function unequip() --- equip tool
   game.Players.LocalPlayer.Character.Humanoid:UnequipTools()
end
unequip()
BuyDragonTalon = tonumber(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDragonTalon",true))
HasTalon = ""
if BuyDragonTalon then
   if BuyDragonTalon == 1 then
      HasTalon = "DragonTalon,"
   end
end

BuySuperhuman = tonumber(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySuperhuman",true))
HasSuperhuman = ""
if BuySuperhuman then
   if BuySuperhuman == 1 then
      HasSuperhuman = "Superhuman"
   end
end

BuySharkmanKarate = tonumber(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate",true))
if BuySharkmanKarate then
   if BuySharkmanKarate == 1 then
      HasKarate = "SharkmanKarate"
   end
end

BuyDeathStep = tonumber(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep",true))
HasDeathStep = ""
if BuyDeathStep then
   if BuyDeathStep == 1 then
      HasDeathStep = "DeathStep"
   end
end

BuyElectricClaw = tonumber(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw",true))
HasElectricClaw = ""
if BuyElectricClaw then
   if BuyElectricClaw == 1 then
      HasElectricClaw = "ElectricClaw"
   end
end

BuyGodhuman = tonumber(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyGodhuman",true))
HasGodhuman = ""
if BuyGodhuman then
   if BuyGodhuman == 1 then
      HasGodhuman = "Godhuman"
   end
end

UseMelee = "Now Have"
UseSword = "Now Have"
UseGun = "Now Have"
for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
   if v.ClassName == "Tool" and v.ToolTip == "Melee" then
      UseMelee = v.Name
   elseif v.ClassName == "Tool" and v.ToolTip == "Sword" then
      UseSword = v.Name
   elseif v.ClassName == "Tool" and v.ToolTip == "Gun" then
      UseGun = v.Name
   else
   end
end

UseAcc = "Now Have"
for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do 
   if v.ClassName == "Accessory" and v:FindFirstChild("IsAccessory") then
      UseAcc = v.Name
   end
end

local gg = {}
for i, v in pairs(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("getInventoryFruits")) do 
   table.insert(gg,v.Name.." : "..v.Price)
end

FruitInevtory = ""
for i,v in pairs(gg) do
    FruitInevtory = FruitInevtory.. v..'\n'
end

local Common = {}
local Uncommon = {}
local Rare = {}
local Legendary = {}
local Mythical = {}
for i,v in pairs(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("getInventoryWeapons")) do
   if v.Rarity == 0 then
      table.insert(Common,v.Name)
   elseif v.Rarity == 1 then
      table.insert(Uncommon,v.Name)
   elseif v.Rarity == 2 then
      table.insert(Rare,v.Name)
   elseif v.Rarity == 3 then
      table.insert(Legendary,v.Name)
   elseif v.Rarity == 4 then
      table.insert(Mythical,v.Name)
   end
end

pcall(function()
   for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
      if v:IsA("Tool") and v.ToolTip == "Sword" or v.ToolTip == "Gun" and v:FindFirstChild("Rarity") then
         if v.Rarity.Value == 0 then
            table.insert(Common,v.Name)
         elseif  v.Rarity.Value == 1 then
            table.insert(Uncommon,v.Name)
         elseif  v.Rarity.Value == 2 then
            table.insert(Rare,v.Name)
         elseif  v.Rarity.Value == 3 then
            table.insert(Legendary,v.Name)
         elseif  v.Rarity.Value == 4 then
            table.insert(Mythical,v.Name)
         end
      end
   end
end)

pcall(function()
   for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
      if v:IsA("Tool") and v.ToolTip == "Sword" or v.ToolTip == "Gun" and v:FindFirstChild("Rarity") then
         if v.Rarity.Value == 0 then
            table.insert(Common,v.Name)
         elseif  v.Rarity.Value == 1 then
            table.insert(Uncommon,v.Name)
         elseif  v.Rarity.Value == 2 then
            table.insert(Rare,v.Name)
         elseif  v.Rarity.Value == 3 then
            table.insert(Legendary,v.Name)
         elseif  v.Rarity.Value == 4 then
            table.insert(Mythical,v.Name)
         end
      end
   end
end)

local Commonz = ""
local Uncommonz = ""
local Rarez = ""
local Legendaryz = ""
local Mythicalz = ""
for i,v in pairs(Common) do Commonz = Commonz.. v..'\n'end
for i,v in pairs(Uncommon) do Uncommonz = Uncommonz.. v..'\n'end
for i,v in pairs(Rare) do Rarez = Rarez.. v..'\n'end
for i,v in pairs(Legendary) do Legendaryz = Legendaryz.. v..'\n'end
for i,v in pairs(Mythical) do Mythicalz = Mythicalz.. v..'\n'end

local awake = {}
local awakez =  ""
for i, v in pairs(game:GetService("Players").LocalPlayer.PlayerGui.Main.AwakeningToggler.TopContainer.Frame:GetChildren()) do 
   if v:IsA('ImageButton') then
      if  v.Name == 'Template' then
      else
         table.insert(awake,v.Name) 
      end
   end
end
local awakez =  ""
for i,v in pairs(awake) do
   awakez = awakez..v.."✅".."\n"
end

unequip()
function SendMessage(Webhook)
   local re
   if syn then
       re = syn.request 
   else
       re = request
   end
       re({
       Url = Webhook,
       Method = "POST",
       Headers = {
           ["Content-Type"] = "application/json"
       },
       Body = game:GetService("HttpService"):JSONEncode({
       ["content"] = "@everyone",
       ["username"] = "xSoku Hub - Webhook",
       ["avatar_url"] = "https://media.discordapp.net/attachments/1030725412579459152/1032899489335365632/O.jpg?width=394&height=700",
           ["embeds"] = {
           {
           ["author"] = {
                   ["name"] = "xSoku Webhook Status",
                   ["icon_url"] = 'https://media.discordapp.net/attachments/1030725412579459152/1032899489335365632/O.jpg?width=394&height=700',
           },
           ["fields"] = {
               {
                   ["name"] = "User Name",
                   ["value"] = '||'..game.Players.localPlayer.Name..'||',
                   ['inline'] = true
               },
               
               {
                   ["name"] = "Level",
                   ["value"] = Fornum(game:GetService("Players").localPlayer.Data.Level.value),
                   ['inline'] = true
               },

               {
                   ["name"] = "Fragments",
                   ["value"] = "ƒ"..Fornum(game:GetService("Players").localPlayer.Data.Fragments.value),
                   ['inline'] = true
               },

               {
                   ["name"] = "Bounty/Honor",
                   ["value"] = Fornum(game:GetService("Players").localPlayer.leaderstats["Bounty/Honor"].value),
                   ['inline'] = true
               },

               {
                   ["name"] = "Beli",
                   ["value"] = "$"..Fornum(game:GetService("Players").localPlayer.Data.Beli.value),
                   ['inline'] = true
               },

               {
                   ["name"] = "Race",
                   ["value"] = game:GetService("Players").localPlayer.Data.Race.value,
                   ['inline'] = true
               },

               {
                   ["name"] = "Devil Fruit",
                   ["value"] = game:GetService("Players").localPlayer.Data.DevilFruit.value,
                   ['inline'] = true
               },

               {
                ["name"] = "Fighting Style",
                ["value"] = UseMelee,
                ['inline'] = true
               },

               {
                ["name"] = "Sword",
                ["value"] = UseSword,
                ['inline'] = true
               },

               {
                ["name"] = "Gun",
                ["value"] = UseGun,
                ['inline'] = true
               },

               {
                ["name"] = "Accessory",
                ["value"] = UseAcc,
                ['inline'] = true
               },

               {
                ["name"] = "Awakened",
                ["value"] = "```\n"..awakez.."```",
                ['inline'] = true
               },

               {
                   ["name"] = "Stat",
                   ["value"] = "```css\nMelee : "..game:GetService("Players").localPlayer.Data.Stats.Melee.Level.Value.."\nDefense : "..game:GetService("Players").localPlayer.Data.Stats.Defense.Level.Value.."\nSword : "..game:GetService("Players").localPlayer.Data.Stats.Sword.Level.Value.."\nGun : "..game:GetService("Players").localPlayer.Data.Stats.Gun.Level.Value.."\nDemon Fruit : "..game:GetService("Players").localPlayer.Data.Stats["Demon Fruit"].Level.Value.."```",
                   ['inline'] = true
               },

               {
                ["name"] = "Common 🔵",
                ["value"] = "```css\n"..Commonz.."```",
                ['inline'] = true
               },
               
               {
                ["name"] = "Uncommon 🟢",
                ["value"] = "```css\n"..Uncommonz.."```",
                ['inline'] = true
               },
               
               {
                ["name"] = "Rare 🟡",
                ["value"] = "```css\n"..Rarez.."```",
                ['inline'] = true
               },

               {
                ["name"] = "Legendary 🟣",
                ["value"] = "```css\n"..Legendaryz.."```",
                ['inline'] = true
               },

               {
                ["name"] = "Mythical 🔴",
                ["value"] = "```css\n"..Mythicalz.."```",
                ['inline'] = true
               },

               {
                  ["name"] = "Fruit In Inventory",
                  ["value"] = "```css\n"..FruitInevtory.."```",
                  ['inline'] = true
                 },

               {
                ["name"] = "All Fighting Style",
                ["value"] = "```css\n"..HasTalon.."\n"..HasSuperhuman.."\n"..HasDeathStep.."\n"..HasElectricClaw.."\n"..HasGodhuman.."\n".."```",
                ['inline'] = true
               },
           },
           ["color"] = tonumber(0x017ffc),
           ["footer"] = {["text"] = "all by 9pasa"}
            
           }
   }   
       })
   
   })
end
SendMessage(x)
game:GetService("Players").LocalPlayer.PlayerGui.Main.AwakeningToggler.Visible = false

until _G.P == false
