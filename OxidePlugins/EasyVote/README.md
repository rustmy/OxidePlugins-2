# EasyVote
EasyVote make voting easy and smooth. I think that voting shouldn't be big progress, instead i want make it smooth and fast. No permission needed, only need setup config file.
You can found EasyVote from http://oxidemod.org/plugins/easyvote.2102

# Reward variables
| Reward Variable        | Description           | Example  |
| ------------- |:-------------:| -----:|
| item.name      | Use only ITEM SHORTNAME! You get item list from [Oxide itemlist](http://docs.oxidemod.org/rust/#item-list) | supply.signal: 1 |
| addgroup      | Add a player to a group for a specific time (Request: [Timed Permissions](http://oxidemod.org/plugins/timed-permissions.1926/)) | addgroup: vip-1d |
| grantperm | Give a player a permission for a specific time (Request: [Timed Permissions](http://oxidemod.org/plugins/timed-permissions.1926/)) | grantperm: permission.use-1d |
| money | How much gave money per vote (Request: [Economics](http://oxidemod.org/plugins/economics.717/)) | money: 100 |
| rp | How much gave rp per vote (Request: [ServerRewards](http://oxidemod.org/plugins/serverrewards.1751/)) | rp: 10 |
| addlvl | How much add level per vote (Request: [xpmanager](http://oxidemod.org/plugins/xp-manager.2026/)) | addlvl: 1 |
| zlvl-wc | How much add Woodcutting level per vote (Request: [ZLevels](http://oxidemod.org/plugins/zlevels-remastered.1453/)) | zlvl-wc: 10 |
| zlvl-mg | How much add Mining level per vote (Request: [ZLevels](http://oxidemod.org/plugins/zlevels-remastered.1453/)) | zlvl-mg: 10 |
| zlvl-s | How much add Skinning level per vote (Request: [ZLevels](http://oxidemod.org/plugins/zlevels-remastered.1453/)) | zlvl-s: 10 |

# Variables
| Variable        | Description           |
| ------------- |:-------------:| -----:|
| {playername}      | User display name |
| {playerid}      | User SteamID64 |
| {value} | Value data from value |
| {value2} | Value data from value2 (Remeber split value and value2 with -) |

# Chat Commands
| Command        | Description           |
| ------------- |:-------------:| -----:|
| /vote      | Show vote link(s) |
| /reward      | Claim vote reward(s) |
| /reward list | Display what reward(s) can get |

# Configuration file
```javascript
{
  "Reward": {
    "vote1": [ // Number mean how many timed need to vote, before can get this reward.
      "supply.signal: 1" // Use Item Shortname.
    ],
    "vote3": [ // When player has voted 3 time. He got this reward and only this reward.
      "supply.signal: 1",
      "money: 250"
    ],
    "vote6": [
      "supply.signal: 1",
      "money: 500",
      "addlvl: 1"
    ]
  },
  "Settings": {
    "GlobalAnnouncment": "true", // Global announcment to all players who received rewards and how many time voted.
    "Annoucment": "true", // If true, check every time when player wake up his vote status.
    "Prefix": "<color=cyan>[EasyVote]</color>", // Can be disabled by just leaving this string empty.
    "RustServersID": "", // Found ID from "My options -> Manage Your Servers"
    "RustServersKEY": "", // Found KEY from "My options -> Manage Your Servers"
    "TopRustServersID": "", // Found ID from URL!
    "TopRustServersKEY": "" // Found KEY from Manage server!
    "BeancanID": "",
    "BeancanKEY": "",
    "HighestVoter": "false", // Take every next month highest voter and give him free rank.
    "HighestVoterRewardGroup": "hero" // Rank what highest voter will receive.
  },
  "Variables": {
  // You can add/edit variables how ever you want.
  // To add new variable, you copy and paste last line "zlvl-wc".
  // Rename it something else, and edit console command.
    "addgroup": "addgroup {playerid} {value} {value2}",
    "addlvl": "xp addlvl {playername} {value}",
    "grantperm": "grantperm {playerid} {value} {value2}",
    "money": "eco.c deposit {playerid} {value}",
    "rp": "sr add {playername} {value}",
    "zlvl-mg": "zlvl {playername} MG +{value}",
    "zlvl-s": "zlvl {playername} S +{value}",
    "zlvl-wc": "zlvl {playername} WC +{value}"
  }
}
```

# Language file
```javascript
{
  "ClaimError": "Something went wrong! We got <color=red>{0} error</color> from <color=yellow>{1}</color>. Please try again later!",
  "ClaimReward": "You just received your vote reward(s). Enjoy!",
  "EarnReward": "When you are voted. Type <color=cyan>/reward</color> to earn your reward(s)!",
  "RewardList": "<color=cyan>Player reward, when voted</color> <color=orange>{0}</color> <color=cyan>time(s).</color>",
  "Received": "You have received {0}x {1}",
  "Highest": "<color=cyan>The player with the highest number of votes per month gets a free</color> <color=yellow>{0}</color><color=cyan> rank for 1 month.</color>",
  "HighestCongrats": "<color=yellow>{0}</color> <color=cyan>was highest voter past month</color><color=cyan>. He earned free</color> <color=yellow>{1}</color> <color=cyan>rank for 1 month. Vote now to earn it next month!</color>",
  "ThankYou": "Thank you for voting {0} time(s)",
  "NoRewards": "You do not have any new rewards avaliable \n Please type <color=yellow>/vote</color> and go to the website to vote and receive your reward",
  "RemeberClaim": "You haven't yet claimed your reward from voting server! Use <color=cyan>/reward</color> to claim your reward! \n You have to claim your reward in <color=yellow>24h</color>! Otherwise it will be gone!",
  "GlobalAnnouncment": "<color=yellow>{0}</color><color=cyan> has voted </color><color=yellow>{1}</color><color=cyan> time(s) and just received their rewards. Find out where to vote by typing</color><color=yellow> /vote</color>\n<color=cyan>To see a list of avaliable rewards type</color><color=yellow> /reward list</color>",
  "money": "{0} has been desposited into your account",
  "rp": "You have gained {0} reward points",
  "addlvl": "You have gained {0} level(s)",
  "addgroup": "You have been added to group {0} {1}",
  "grantperm": "You have been given permission {0} {1}",
  "zlvl-wc": "You have gained {0} woodcrafting level(s)",
  "zlvl-mg": "You have gained {0} mining level(s)",
  "zlvl-s": "You have gained {0} skinning level(s)",
  "zlvl-c": "You have gained {0} crafting level(s)"
}
```
