# Autokick
AutoKick help you set (for example) the maintenance break to server!
When AutoKick is Enabled, only players that has auth level can join to the server. Auth2 can join to the server always, but you can also allow Auth1 join too!
You can found Autokick from http://oxidemod.org/plugins/autokick.2138/

If you dont know how oxidemod permission work, you can found all help here,
http://oxidemod.org/threads/using-oxides-permission-system.8296/

# Permissions
| Permission        | Description           |
| ------------- |:-------------:| -----:|
| autokick.use | Allow use autokick commands |
| autokick.join | Allowed to join server when autokick is enabled |

# Chat Commands
| Command        | Description  |
| ------------- |:-------------:| -----:|
| /autokick (on/off) | Enable/Disable Autokick |
| /autokick kick | When autokick is Enabled. Use this command to kick online players |
| /autokick set [message] | Set new kick message | 
| /autokick message | See current kick message |

# Configuration file
```javascript
{
  "Settings": {
    "Enabled": "false", // When true, Autokick is enabled. Can be change by edit it from config or use ingame command /ak on
    "KickMessage": "You have automaticly kicked, Server is on maintenance break!", // Kick message. Can be change by edit it from config or use ingame command /ak set [message]
    "Prefix": "[#cyan][AutoKick][/#]" // Autokick Prefix. Can be disabled by leave this string empty.
  }
}
```

# Language file
```javascript
{
  "Toggle": "Autokick is [#yellow]{0}[/#]",
  "KickHelp": "When Autokick is [#yellow]{0}[/#], use [#yellow]{1}[/#] to kick all online players.",
  "Kicked": "All online players has been kicked! Except players that have [#yellow]{0}[/#] permission or is admin.",
  "Set": "Message is now setted to \"[#yellow]{0}[/#]\"",
  "Message": "AutoKick message is \"[#yellow]{0}[/#]\"",
  "ToggleHint": "Autokick must be [#yellow]{0}[/#], before can execute [#yellow]{1}[/#] command!",
  "Usage": "[#cyan]Usage:[/#] [#silver]{0}[/#] [#grey]{1}[/#]"
}
```
