# AH Bot Plus — Brambletown deployed configuration snapshot

Captured: 2026-10-18 (America/Chicago)
Source commit observed on the production server: `f685832994c825f90aa5a3dc0e1620aa568e875b`
Configuration source: `env/dist/etc/modules/mod_ahbot.conf`; compared against matching `.conf.dist`.

There are no local source-code modifications to this module; the deployed module source matches fork master. The priority list is configuration, not a code patch.

## Non-default configuration entries

```ini
AuctionHouseBot.Alliance.MaxItems = 35000
AuctionHouseBot.Alliance.MinItems = 25000
AuctionHouseBot.EnableSeller = true
AuctionHouseBot.GUIDs = 1007
AuctionHouseBot.Horde.MaxItems = 35000
AuctionHouseBot.Horde.MinItems = 25000
AuctionHouseBot.ItemsPerCycle = 575
AuctionHouseBot.ListProportion.ListMultipliedItemIDs = 2589:10,2592:10,4306:10,4338:10,14047:10,21877:10,33470:10,2318:10,2319:10,4234:10,4304:10,8170:10,21887:10,33568:10,2770:10,2771:10,2772:10,2775:10,2776:10,3858:10,7911:10,10620:10,23424:10,23425:10,23426:10,23427:10,36909:10,36912:10,36910:10,2835:10,2836:10,2838:10,12365:10,7912:10,765:10,785:10,2447:10,2449:10,2450:10,2452:10,2453:10,3355:10,3356:10,3357:10,3358:10,3369:10,3818:10,3819:10,3820:10,3821:10,4625:10,8153:10,8831:10,8836:10,8838:10,8839:10,8845:10,8846:10,13463:10,13464:10,13465:10,13466:10,13467:10,13468:10,22785:10,22786:10,22787:10,22789:10,22790:10,22791:10,22792:10,22793:10,22794:10,22795:10,36901:10,36902:10,36903:10,36904:10,36905:10,36906:10,36907:10,36908:10,37921:10,10938:10,10939:10,10940:10,10978:10,10998:10,11082:10,11084:10,11128:10,11134:10,11135:10,11138:10,11139:10,11174:10,11175:10,11177:10,11178:10,14343:10,16202:10,16203:10,16204:10,22445:10,22446:10,22447:10,22448:10,22449:10,34052:10,34053:10,34054:10,34055:10,34056:10,774:10,818:10,1206:10,1210:10,1529:10,1705:10,3864:10,7909:10,7910:10,12361:10,12364:10,12799:10,12800:10,21929:10,23077:10,23079:10,23107:10,23112:10,23117:10,23436:10,23437:10,23438:10,23439:10,23440:10,23441:10,36917:10,36918:10,36919:10,36920:10,36921:10,36922:10,36923:10,36924:10,36925:10,36926:10,36927:10,36928:10,36929:10,36930:10,36931:10,36932:10,36933:10,36934:10,118:5,858:5,929:5,2455:5,2456:5,3827:5,3928:5,6149:5,13443:5,13446:5,18253:5,22829:5,22832:5,22850:5,33447:5,33448:5,39671:5,40067:5,43569:5,43570:5,4371:10,4389:10,4392:10,10559:10,4407:10,4394:5,10507:5,4384:5,4363:5,4375:5,11590:5,10560:5,10561:10,10562:5,10646:5,15992:5,15993:5,15994:10,16000:5,16006:10,23784:10,23786:5,39681:5,39682:10,9061:5,12360:10,15407:10,14342:10,12810:10,12655:10,11371:5,14048:5,2997:5,23793:5,23448:5,23571:10,3486:5,7966:5,12644:5,7936:5,7935:5,7937:5,7941:5,7945:5,3853:5,3855:5,2868:5,3835:5,8175:5,8176:5,8187:5,8189:5,8191:5,8193:5,8197:5,8198:5,8203:5,8204:5,8211:5,8214:5,15564:5,4265:5,8173:5,3829:10,8956:5,13423:5,9264:5,19440:5,20452:5,12209:5,12210:5,13935:5,6887:5,5095:5,34747:5,14529:5,14530:5,8544:5,8545:5,6450:5,6451:5,3530:5,1251:5,729:10,730:10,731:10,732:10,723:10,1080:10,1081:10,2296:10,1015:10,769:5,2886:5,2924:5,3404:5,3172:10,3173:10,3174:10,5465:5,5469:5,1468:5,2251:5,22644:5,3712:10,7974:10,12207:10,31670:10,31671:10,43013:10
AuctionHouseBot.Neutral.MaxItems = 35000
AuctionHouseBot.Neutral.MinItems = 25000
```

All other present keys matched the deployed `.conf.dist` at capture time. A read-only check on 2026-10-18 confirmed that the on-disk configuration has exactly the ten overrides listed above (including all 286 multiplied-item entries); its other 438 settings match both the deployed and module-source `.conf.dist` files. This does not independently establish which values the running worldserver has loaded. Values here are documentation, **not** an installable live configuration or code patch.

## Review focus

Auction volume targets, replenishment rate, faction pool behavior, economics of multiplied items, profession and cooking quest-item stocking.

## Gate to future changes

Preserve upstream default branch. Implement subsequent code/config changes in a separate branch and PR, review CodeRabbit findings, compile/verify, test in-game, and record deployed commit/version. No production deployment or restart is part of this baseline PR.
