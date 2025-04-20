Requires EMCO (https://github.com/demonnic/EMCO) to be installed as well, and restart Mudlet.

Must also enable MSDP reporting for some of these on logon:

sendMSDP("REPORT","WORLD_TIME","FLYING","INVIS","STR","CLASS","ROOM_NAME","AREA_NAME","GEO","ROOM_TERRAIN","CHARACTER_NAME","FAVOR","ROOM_EXITS","VIS","BLOOD","BLOOD_MAX","AFFECTS","OPPONENT_HEALTH","OPPONENT_NAME","OPPONENT_LEVEL")

You should also be running 'config +telnetga' on each character mudside.

The prompt scripts/triggers may need disabling unless you want to try my prompt. The code anchors it to the bottom if you have the triggers set up to detect your prompt properly..

Example prompts that work (run this when connected and with msdp already set up as per above

#mana user prompts for all classes
#xp
lua send("prompt &b#STATUS-&P<&z%G&P|&W%E&P|&p%T&P|&O%z&P|&W%S&P>%l&b#XL" .. msdp.CLASS .. "-" .. msdp.CHARACTER_NAME .. "-&P<&G%h/%Hhp &C%m/%Mm &g%v/%Vmv &c%w/%Wkg &O%gg &W%a &R%A&P TNL: %X>")
lua send("fprompt &R&&FIGHTING-&P<&W%n&P|&R%c&P|&w%S&P|&OLag:&Y%L&P>%l&R&&XL" .. msdp.CLASS .. "-" .. msdp.CHARACTER_NAME .. "-&P<&G%h/%Hhp &C%m/%Mm &g%v/%Vmv TNL: %X>")

#noxp
lua send("prompt &b#STATUS-&P<&z%G&P|&W%E&P|&p%T&P|&O%z&P|&W%S&P>%l&b#" .. msdp.CLASS .. "-" .. msdp.CHARACTER_NAME .. "-&P<&G%h/%Hhp &C%m/%Mm &g%v/%Vmv &c%w/%Wkg &O%gg &W%a &R%A&P>")
lua send("fprompt &R&&FIGHTING-&P<&W%n&P|&R%c&P|&w%S&P|&OLag:&Y%L&P>%l&R&&" .. msdp.CLASS .. "-" .. msdp.CHARACTER_NAME .. "-&P<&G%h/%Hhp &C%m/%Mm &g%v/%Vmv>")
