If you have any contributions (new urls, previously unknown parameters, etc.), feel free to submit an issue or pull request and I will be sure to credit you. **Feel like helping? Don't forget to check the CONTRIBUTE.md guide**

The main goal of this project is to document endpoints in the RotMG appspot API. All links (at least the ones we can find / have access to), old or new, are posted here.

## Root URL
- https://realmofthemadgodhrd.appspot.com
- https://realmofthemadgod.appspot.com (used before kabam account migration)
- http://rot.mg (redirect to https://www.realmofthemadgod.com/)

## Subdomains
- [http://play.realmofthemadgod.com](https://web.archive.org/web/20160630000841/http://play.realmofthemadgod.com/) (used by kabam till 2016 for unknown purpose)
- http://remaster.realmofthemadgod.com
- http://unity.realmofthemadgod.com

## Testing Links
- https://rotmghrdtesting.appspot.com (old kabam test server used for account migration testing)
- https://rotmgtesting.appspot.com (the current rotmg testing server)
- https://realmtesting2.appspot.com ("hidden" testing server for private testers)
- https://test.realmofthemadgod.com
- https://test2.realmofthemadgod.com
- https://test3.realmofthemadgod.com
- https://rotmgtesting3.appspot.com
- https://testing.realmofthemadgod.com

Directories marked with an asterisk (*) are internal server urls and will always return ``<Failure/>``

Endpoints without any listed arguments could still take certain parameters, but they might not be listed here yet due to incompletedness.

Please note that DECA can add or remove links at any time.

**Known URL parameters** (Sorted by key:value, or example value)
- `game_net`:`rotmg`
- `game_net_user_id`: _empty_
- `ignore`:`23424` _random number from 1000 to 999999_ (used for cache busting)
- `gameClientVersion`:`X31.2.3` (current game version)
- `languageType`:`en`
- `guid`:`example@mail.com` (email)
- `password`:`password123`

``/``
 * ``logowtext.png``
 * ``realmlogo.png``
 * ``version.txt`` => time (unix time)
 * ``servers.txt``
 * ``crossdomain.xml``
 * ``draw.html``
 * ``draw/html``
 * ``TMLoader{version}.swf``
 * ``TextureMaker{version}.swf``
 * ``AGCloader{version}.swf``
 * ``client``
 * ``AssembleeGameClient{version}.swf``
 * ``playerProductInstall.swf``
 * ``UGDTermsofUse.html``
 * ``kongregate.html``
 * ``xd.html``
 * ``PrivacyPolicy.html``
 * ``kabam.html``
 * ``app.yaml``
 * ``index.yaml``
 * ``dispatch.yaml``
 * ``cron.yaml``
 * ``dos.yaml``
 * ``queue.yaml``
 * ``legacy``

``app/``
 * ``globalNews``
 * ``getLanguageStrings`` => languageType (en)
 * ``init`` => platform (standalonewindows64 or standalonewindows), key (seems to be hardcoded - 9KnJFxtTvLu2frXv for windows), guid, password
 * ``publicStaticData`` => dataType (powerUpSettings)

``package/``
 * ``getPackages`` => guid, password, version (seems to accept any float like 1.0)

``mysterybox/``
 * ``getBoxes`` => guid, password, version (seems to accept any float like 1.0)

``credits/``
 * ``getoffers`` => guid, password
 * ``pwpurchase`` => iframeUrl (json with these params: token, production)
 * ``add`` => tok, exp, guid, provider, jwt, price, paymentid
 * ``done``
 * ``error``
 * ``kabamadd`` => naid, signedRequest, createdat (removed)
 * ``token`` => guid, password

``picture/`` => Seems to redirect to google login now
 * ``list`` => myGUID, guid, dataType, tags, offset, num
 * ``get`` => id, time
 * ``save``
 * ``delete`` => id, guid, password

``images/``
 * ``DecaLogoWhite.png``
 * ``kabamLogo192x97.png``

``css/``
 * ``rotmg.common.css``

``js/``
 * ``rotmg.UrlLib.js``
 * ``rotmg.Paymentwall.js``
 * ``jquery-1.8.0.min.js``
 * ``rotmg.Xsolla.js``
 * ``AC_OETags.js``
 * ``rotmg.Paymentwall.js``
 * ``rotmg.SalesForce.js``
 * ``rotmg.Client.js``

``admin/`` => Takes you to google sign in

``data/``
 * => prints a message saying you are forbidden to access this page

``log/``
 * ``logFteStep`` => game_net_user_id, game_net, play_platform, guid, password, fteStepCompleted (used for tracking tutorial progress, removed)
 * ``logGameModePlayed`` => seasonID, gameMode (Legacy or Challenger), guid, password

``server/`` => all of these urls are internal
 * ``list``
 * ``add``
 * ``remove``

``account/``
 * ``register`` => newPassword, entrytag, newGUID, name(not needed), isAgeVerified, guid, signedUpKabamEmail (0 or 1)
 * ``verify`` => guid, password (used by Muledump)
 * ``verifyage`` => guid, password, ignore, isAgeVerified, gameClientVersion
 * ``acceptTOS`` => guid, password
 * ``changeEmail`` => guid, password, newGuid
 * ``playFortuneGame`` => choice, status, currency (2 for fortune tokens or 0 for gold)
 * ``rp`` => a, b
 * ``login``
 * ``setName`` => guid, password, name
 * ``validateEmail`` (removed, changed to isEmailVerified)
 * ``supportVerify`` => guid, password, secret
 * ``*addStar``
 * ``*addIgnore``
 * ``purchaseCharSlot`` => guid, password
 * ``*purchaseVaultChest``
 * ``purchaseSkin`` => guid, password, skinType
 * ``purchaseMysteryBox`` => guid, password, boxId, quantity, price, currency
 * ``purchasePackage`` => guid, password, boxId, quantity, price, currency
 * ``getOwnedPetSkins`` => guid, password
 * ``getBeginnerPackageTimeLeft`` => guid, password (removed)
 * ``sendVerifyEmail`` => guid, password
 * ``forgotPassword`` => guid
 * ``changePassword`` => newPassword, guid, password
 * ``getCredits`` => guid, password
 * ``ban`` => Returns internal error
 * ``v`` => a, b(Getting the captcha); a, action, g-recaptcha-response(Submitting the captcha)
 * ``*claimLoginReward``
 * ``saveSecurityQuestions`` => guid, password, answers (encoded in base64 and split by a pipe operator [|])
 * ``forgotpasswordPage`` => links to a page where you enter your email
 * ``isEmailVerified`` => guid, password
 * ``signupDecaEmail`` => notifyMe (1 or 0), guid, password, email
 * ``spammer`` => Returns internal error
 * ``servers`` => guid, password
 * ``list`` => guid, password, type(1:ignored or 0:locked)

``supportCampaign/``
 * ``claim`` => guid, password
 * ``unlock`` => guid, password
 * ``donate`` => guid, password, amount
 * ``status`` => guid, password
 * ``create``
 * ``getinfo``
 * ``getUnitySupporters`` => guid, password, page
 
``fame/``
 * ``list`` => timespan (week, month, all), &charId, &accountId
 * ``challengerSeasonList`` => guid, password
 * ``challengerLeaderboard`` => accountId, charId, timespan (same as fame/list)
 * ``challengerAccountLeaderboard`` => accountId, charId, timespan (same as fame/list)

``dailyLogin/``
 * ``fetchCalendar`` => guid, password

``season/``
 * ``getSeasons`` => guid, password, gameClientVersion

``dailyquest/``
 * ``resetDailyQuests`` => guid, password (returns <Error>Server error<Error/>)
 * ``resetDailyQuestsAdmin`` => guid, password (requires admin account)

``char/``
 * ``list`` => guid, password, [challenger (false/true)][muleDump (true/false)]
 * ``fame`` => accountId, charId
 * ``*purchase``
 * ``*get``
 * ``*reskin``
 * ``*create``
 * ``*update``
 * ``purchaseClassUnlock`` => guid, password, game_net_user_id, game_net, play_platform, do_login, classType
 * ``delete`` => guid, password, charId, reason (seems to be always 1)

``inGameNews/``
 * ``getNews``
 
 ``unityNews/``
* ``getNews``


``friends/``
 * ``requestFriend`` => guid, targetName, password
 * ``getList`` => guid, password
 * ``getRequests`` => guid, password
 * ``acceptRequest`` => guid, targetName, password
 * ``rejectRequest`` => guid, targetName password
 * ``removeFriend`` => guid, targetName, password
 * ``blockRequest`` => guid, targetName, password

``pet/``
 * ``*feed``
 * ``*fuse``
 * ``*createPet``
 * ``*yardupgrade``

``news/`` => Takes you to google sign in

``arena/``
 * ``getRecords`` => type (weekly, personal, alltime), guid, password
 * ``getPersonalBest`` => guid, password

``guild/``
 * ``*changeRank``
 * ``*removeMember``
 * ``*create``
 * ``getBoard`` => guid, password
 * ``setBoard`` => guid, password, board
 * ``listMembers`` => guid, password, num, offset
 * ``*purchase``

``kabam/``
 * ``getcredentials`` => userId, signedRequest, entrytag
 * ``link`` => kabamemail, kabampassword, email, password
 * ``verify`` => kabamemail, kabampassword

``migrate/``
 * ``doMigration`` => guid, password
 * ``progress`` => guid
 * ``userAccountReset`` => guid, password (returns Failure, testing environment only)

``steamworks/``
 * ``finalizePurchase`` => appid, orderid, authorized (1 or 0)
 * ``getcredentials`` => userId
 * ``purchaseOffer`` => steamid, data
 * ``register`` => newGUID, newPassword, entrytag (disabled)
 * ``link`` (disabled)
 * ``getoffers``

``kongregate/``
 * ``getcredentials`` => userId, gameAuthToken
 * ``register`` => userId, username, gameAuthToken, newGUID, newPassword, entrytag
 * ``link`` (disabled)
 * ``internalRegister`` => userId, username, gameAuthToken, guid
 * ``getoffers``
 * ``callback`` 
 * May be related: https://docs.kongregate.com/docs/server-side-http#section-callback-format

``clientError/``
 * ``add`` => text, guid

``ugc/`` (User Generated Content)
 * ``save`` => guid, password, name, description, width, height, mapjm, tags, totalObjects, totalTiles, thumbnail, overwrite (on or off) (seems to always return <Error>Invalid permissions</Error>)
 * ``*get``

``sfx/``
 * => too many mp3 files to list (you can find these in pserver sources)
 * See: https://realmofthemadgod.fandom.com/wiki/Sounds
 
``music/``
 * ``sorc.mp3`` => main theme for RotMG
 
``build/``

``survey/``
 * ``add`` => Returns 500 error
 * ``*delete``

``events/``

``exalt/``

``platforms/``
 * ``kabam`` => Error 405. Method GET not allowed.

``cronJob/`` => Takes you to google sign in

``eventlog/`` => Access is forbidden

``hotkeyz/`` => Access is forbidden

``topz/`` => Access is forbidden

``rpcz/`` => Access is forbidden

## Unknown urls

Payment url: http://www.realmofthemadgod.com/?user_id=email&status=done&invoice_id=111111111
