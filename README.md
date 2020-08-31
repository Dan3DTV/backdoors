### Whats a backdoor?
Roblox backdoors are malicious scripts that load up modules into your game, which usually end up giving a group of "hackers" server-sided access to your game. Don't worry if you don't know what any of that means - we will go over it.
### Where backdoors come from?
Backdoors can come from anywhere. They mostly, though, come from free models and plugins. A skid will usually infect it with a malicious script, then bot it to the front page so more vulnerable people see it and insert it into their game.

They also come from plugins. When you install a shady plugin and go into a game, the plugin will insert a script into your game that loads up their backdoor. They can also make it impossible to delete.

They also come from .exe / .dmg files. You may ask how - well, the file may get into your place's XML and insert the malicious script from there. It is uncommon, but I have seen it happen.

Those places are the most common to see backdoors in. Make sure to use products only from trusted developers.
### How to detect a backdoor

Backdoors, if in the right hands, are easy to detect. They almost always can be found by pressing "Ctrl + Shift + F" and typing in `require`. If no script is flagged, then try searching for `getfenv` insead. There is no other possible way to load up a backdoor without using one of these methods. 

If, for example, the script is inserted into every game you made and you didn't use free models, it is most definetely a plugin causing this problem. Look through ALL of your plugins, if it looks suspicious (e.g. 100 thousand sales and 10 favorites/likes, or the owner is a default avatar) make sure to look through it's source for any script insertions and `getfenv`s or `require`s. If you track down the culprit, uninstall and report the plugin so moderators can take down the plugin.

An example of a backdoor loader:
#### getfenv

```lua
getfenv['\114\101\113\117\105\114\101'](1234) -- "1234" is the ID to the loader of the backdoor. The '\114\101\113\117\105\114\101' is the bytecode of require.
```

#### require

```lua
require(1234) -- This is easier to detect as a backdoor.
```

#### Hexadecimals

Instead of putting the raw ID into `require` (e.g. 1234), they sometimes use [hexadecimals](https://en.wikipedia.org/wiki/Hexadecimal).  

Heres an example of a hexadecimal loader:

```lua
require(0x4D2) -- Loads up the ID: 1234. To decode a hexadecimal: Copy the hexadecimal, into the studio command bar do:
print(0x4D2) -- Prints out the decoded ID.
```
For easier detection, use a [plugin](https://devforum.roblox.com/t/1k-gameguard-anti-virus-v2-alpha/607865) that I have created just for that.

### Track down the source of the backdoor

If you are curious (like me) you would always want to see what is under the hood. You can easily track down the source of the loader, to see if it actually IS a backdoor or not, or to see what the skid has skidded.
First, find the **ID of the backdoor**. This was explained in "How to detect a backdoor".
After you located the ID, put this code into the command bar in Studio:
```lua
game:GetObjects('rbxassetid://ID HERE')[1].Parent = workspace -- replace "ID HERE" with the ID you copied.
```
Then, open up Workspace. You should see a ModuleScript named MainModule.
