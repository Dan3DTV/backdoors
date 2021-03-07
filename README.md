## Welcome!

This is a large backdoor explanation document that I have written to help others learn about backdoors and how to remove them. Backdoors are currently becoming more and more popular and they are in 90% (don't fact-check) of the models in the [library](https://www.roblox.com/library) and toolbox.

#### Who am I?

To get started, lets talk about me. I am [Dan_PanMan](https://www.roblox.com/users/282028881/profile/), the creator of [GameGuard Antivirus](https://www.roblox.com/library/5121131624) that has been trusted and used by the developer community. I have been around backdoors for around 2 years, cracked over 70 serversides, and helped a ton of users with conserns. I hope to make this document be useful for all types of users in the developer community.

## Types of viruses

Let's talk about all of the viruses and learn all the types.

### PurchasePrompt Spam

![image](https://user-images.githubusercontent.com/40477254/110251800-d9e4fb00-7f47-11eb-8ba2-5f0bff3bb27d.png)

This is a **common** virus which is **extremely** easy to remove. Such viruses look like this:
```lua
while wait() do
    local id = 1234
    script.Parent = game.ServerScriptService
    local market = game:GetService("MarketplaceService")
    for i, v in pairs(game.Players:GetChildren()) do
        market:PromptPurchase(v, id)
    end
end
```
<h6>A common PurchasePrompt spam virus.</h6>

As you can see, it is a while true do loop that spams :PromptPurchase() to every player in the game. 

#### How to remove

This is how you can remove such purchase prompt virus.

1. Go into the game settings
2. Click on the "Security" tab
3. Turn off "Allow Third Party Sales"

![image](https://user-images.githubusercontent.com/40477254/110251662-27ad3380-7f47-11eb-895f-5b54ccca9d95.png)

### Fire/Vaccine/InFeCtioN/more

These are **extremely common** viruses which are **easy** to remove.
Their general purpose is to lag and 
