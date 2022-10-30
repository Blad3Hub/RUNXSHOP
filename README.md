local request = http_request or request or (syn and syn.request)

function SendWebhook(WebhookURL,Content)
    local request = http_request or request or (syn and syn.request)
    
    request({
        Method = "POST",
        Url = _G.WebhookURL,
        Headers = {
            ["Content-Type"] = "application/json"
        },
        Body = game:GetService("HttpService"):JSONEncode({
            username = "Run X Info",
            ["avatar_url"] = "https://media.discordapp.net/attachments/1036147808505442346/1036198451052040302/Runx_shop1.jpg?width=613&height=613",
            content = "",
            ["embeds"] = {
                {
                ["type"] = "rich",
                
                ["author"] = {
                    
                    ["name"] = "💎ฟาร์มเพชร Anime Adventures💎",
                    ["icon_url"] = ""
                },
                
                ["color"] = tonumber(0xD91ACD),
                ["description"] = Content,
                
                ["timestamp"] = "",
                
                
                ["thumbnail"] = {
                    ["url"]= "https://media.discordapp.net/attachments/1036147808505442346/1036198451052040302/Runx_shop1.jpg?width=613&height=613"
                    
                },
                ["footer"]= {
                    ["text"] = "Run X Shop "..os.date("%X"),
                    ["icon_url"]= "https://media.discordapp.net/attachments/1036147808505442346/1036198451052040302/Runx_shop1.jpg?width=613&height=613"
                },
            
                }
            }
        })
    })
end
local plrLvl = tonumber(game.Players.LocalPlayer.Character.Head["_overhead"].Frame["Level_Frame"].Level.Text)
local plrExp = math.floor(game:GetService("Players").ctanxchicken["_stats"]["player_xp"].Value)
local FullplrLvl = game:GetService("Players").LocalPlayer.PlayerGui["spawn_units"].Lives.Main.Desc.Level.Text:gsub("Level","")
local plrGem = game:GetService("Players").LocalPlayer["_stats"]["gem_amount"].Value
local gemrw = game:GetService("Players").LocalPlayer.PlayerGui.Waves.HealthBar.IngameRewards.GemRewardTotal.Holder.Main.Amount.Text

_G.WantedGem = 1000 --ฟามถึงกี่เจม
_G.WebhookURL = "https://discord.com/api/webhooks/1036233511503401010/eQiLp9Z6HBvDNoGyKo6zSf53Uon3uFwc4sJOWJP72TMEFvo1uMLRjH6jlPngRayNzYca" -- ใส่ลิ้ง
while wait() do
if gemrw ~= "+500"then
    SendWebhook("https://discord.com/api/webhooks/1036233511503401010/eQiLp9Z6HBvDNoGyKo6zSf53Uon3uFwc4sJOWJP72TMEFvo1uMLRjH6jlPngRayNzYca",
    "💕**  --- RunX ● Shop --- **💕\n\n".."**┇ข้อมูลของสุดหล่อ┇**\n\n".." ● ชื่อ :".."||"..game.Players.LocalPlayer.Name.."||\n\n".." ● เลเวล : "..FullplrLvl.."\n\n".."● จำนวนเพชร : ["..plrGem.."/".._G.WantedGem.."]\n".."\nReward : \n\n"..gemrw.." 💎".."\n\n---------------------------------\n\n".."RunX ● Shop ")
    task.wait(1)
end 
end

syn.queue_on_teleport([[loadstring(game:HttpGet("https://raw.githubusercontent.com/Blad3Hub/RUNXSHOP/main/README.md"))()]])
