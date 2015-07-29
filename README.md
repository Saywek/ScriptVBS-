# ScriptVBS-
SCRIPTVBS
echo # ScriptVBS- >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/Saywek/ScriptVBS-.git
git push -u origin master



Set objShell = WScript.CreateObject("WScript.Shell") 
ss= objShell.RegRead ("HKEY_CURRENT_USER\Software\Skype\Phone\SkypePath") 
ss= """" + ss + """" 
'Add Block rule 
objShell.run "netsh advfirewall firewall add rule name=""SkypeBlockTCP"" dir=out action=block program=" + ss + " enable=yes protocol=any profile=any" 
'Add Allow rule 
objShell.run "netsh advfirewall firewall add rule name=""SkypeAllowToProxy"" dir=out action=allow program=" + ss + " enable=yes remoteip=127.0.0.1" 
'Turn On firewall 
objShell.run "Netsh advfirewall set allprofiles state on" 
msgbox "IP sécurisé" 


