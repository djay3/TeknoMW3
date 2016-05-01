------------------------------------------------------------------
| TeknoMW3 2.7 *final release* - Modern Warfare 3 Offline MOD    |
|                       www.teknogods.com                        |
------------------------------------------------------------------


We hope you'll enjoy this fine release! It took months to pull it
off. - We basically had to write some missing pieces of the game,
add a lot of extra services and code to handle them. 

Our goal was to make it easier to play the game on LAN parties
or wherever a proper internet connection is a problem.

Don't forget to donate if you would like to keep us supporting
this Modern Warefare 3 MOD!

                                             Regards & Enjoy
                                                   -+-
                                             TeknoGods Staff



                         Requirements:
------------------------------------------------------------------
1. .NET Framework 4.0
   http://www.microsoft.com/download/en/details.aspx?id=17851
2. Original Modern Warfare 3 1.0-1.4.382 update
3. Original IW5SP.exe, IW5Server.exe and IW5MP.exe
4. No pirated versions


                    Known bugs / TODO List:
------------------------------------------------------------------

1. FIX: When you're starting a dedicated server without specifying an
   unique & free "net_queryPort", which is 27015 by default, the game
   wont bother to check if its taken or not. In case it's already taken
   it simply wont start the query service, making your server useless
   and impossible to connect to. We stronlgy suggest creating a separate
   shortcut for each dedicated server that you want to run. Specify
   different "net_queryPort" in each one:
   Shortcut 1)
   +set net_queryPort 55100
   Shortcut 2)
   +set net_queryPort 55200
   * We blame IW for this bug. We know how to fix this.
2. TODO: Mod support
3. TODO: In-game console
4. TODO: 1.5 support



                           Change Log:
------------------------------------------------------------------
  Current version (2.7.0.1):
------------------------------------------------------------------

2.7.0.1 *final release*
- Disabled folder check
- Stability fixes

2.7.0 *final release*
- Master server moved to an official host
- Minor security tweaks


------------------------------------------------------------------
  Previous versions:
------------------------------------------------------------------

2.6.3 *beta*
- BUGFIX: Ini file "ExternalIP" setting (from [Network] section)
  should no longer get overwritten by UPnP router result.
- BUGFIX: Team Auto Balance is now properly initialized. By default
  its enabled. Yuo can disable it via server.cfg:
  seta scr_teambalance 0
- ADDED: ui_hud_obituaries, waypointiconheight and waypointiconwidth
  dvars are no longer protected (server must be running though).
- ADDED: global ban list. Disabled by default. To enable add
  an uption to the ini file under [Network]:
  GlobalBans=true
- ADDED: "dvarinfo" command to the dedicated server. It enables
  debug printouts for the dvars (their current value + default)
  * this wont work from rcon
- ADDED: "rcon_full_access" dvar. It gives you a full access to
  raw server commands via RCON. Set it in server.cfg like:
  seta rcon_full_access "1"

  The carrier command is 'set @' for example:
  rcon set @quit         --this will shut down the server
  rcon set @say hi all   --this will say 'hi all' to everyone

  When "rcon_full_access" is not set, or set to "0", there is
  still a feature that can be used for server-chat. Carrier 
  command is 'set #say', for example:
  rcon set #say hello all, this is server admin.

2.6.2 *beta*
- BUGFIX: Direct connect should work again.

2.6.1 *beta*
- BUGFIX: WinXP missing API crash
- BUGFIX: Game crash when connecting to server
- BUGFIX: Lowered UDP traffic on dedicated servers

2.6:
- BUGFIX: INI file now has a special option under [Network]:
  NetWorkInterface=x
  Where x is your prefered adapter, by default its 255 which means
  the game will bind on all adapters. If you can't see some hamachi
  or LAN game, set the adapter that binds to that network.
  NetworkInterfaceList is information only. Check it.
- BUGFIX: Dedicated server doesnt crash anymore when offline or on
  slow / lagged internet connection.
- ADDED: INI option under [Network]:
  OnlineMode=false/true (default true)
  It can make your server invisible to the master server.
- BUGFIX: Servers can be properly passworded now.
- BUGFIX: 2 player disconnect. Now external ip is cloned
  from internal ip or randomly generated (client). This
  fixes the disconnect problem. If you'd like to set a custom
  external ip, there is a new INI option under [Network]:
  ExternalIP=x.x.x.x
- BUGFIX: IW guys left a nasty bug in the game code. The randomize
  cryptotable used to encrypt rcon protocol using securityID.
  If the securityID is 'unlucky' enough, it would encrypt some
  random character of your password to become a ';' character
  which is safety-checked in the console func, and disregarded
  as 'command reminator'. End result: your password '1234' can
  be encrypted as 'fb;e' and while being passed through console
  end up being sent as 'fb', decrypted on the server as '12'.
  '12' obviosly wouldnt match '1234' sooo you'd never be able
  to log in. Well, this is fixed now.
  TL;DR: rcon should work every time now
- ADDED: secure ban list. New ban list is located at:
  .\main\permanent_ex.ban
  To un-ban, you need to manually find the entry and remove it.
- ADDED: Favorite/History/Official server lists
- BUGFIX: Server list shouldnt crash anymore *I hope*
- BUGFIX: Loader shouldn't crash when executed twice.

2.5.3 HOTFIX:
- Fixed UDP packed sending bug / 100% cpu use for the server.

2.5.2 HOTFIX:
- Fixed few bugs related to the internet server list fetching.

2.5:
- Enabled Internet Server List - You can now browse online servers
  Requirements for the server: NAT out the net_masterServerPort in
  order to make your server visible to the clients.
- CPU usage drastically decreased. No more 100% core use.
- Minor stability fixes, more to come soon.

2.4:
- Fixed Windows Server 2003/2008 crash bug (DEP related)
- Minor protocol security improvements
 
2.3:
- Added dedicated server launcher 'TeknoMW3_dedicated.exe' for
  linux(wine)/windows.
- Removed admin requirements from running the loader.
- Added domain support now, you can use IP addresses or domains.
- FOV restricted to 80.
- INI no longer gets written over each time game is ran.

2.2:
- Dedicated servers have now lowered CPU requirements to 1Ghz.

2.1:
- Fixed a bug in Loader where it couldn't read process memory sometimes
- Fixed a bug in loader where it would take IP as Dedicated server port
- Fixed a bug where it would require all game executables to be present.
- Lighter process starting.

2.0:
- Dedicated Servers support
  * You can now start a dedicated server when totally offline.
  * The games are now ranked
  * Support for future DLC maps!
  * Server will be visible on server browser / LAN tab. If you wish to connect
    directly use GUI to setup IP and use F12 in game to connect. (works over
    the internet)
- Multiplayer support
  * You can now play using custom classes
  * Theater works
  * The game works totally offline (No need Steam or Demonware connection)
- Profile dumper support
  * If you copied our release to your MW3 game in the Steam folder, you can now
    import your online Demonware profile to play offline. However it will update
    separately from that point.
    Run multiplayer mode using steam -> Alt+Tab back to desktop -> run teknowm3
    loader -> click Profile dumper
  * Your Steam ID can be automatically obtained and saved to the teknogods.ini

1.3:
- SteamID generation failed with ID "/" when ID was not present and progress
  was not saved. This is now fixed and autodetected.
- Multilanguage problems now fixed, French language works fine.

1.2:
- New advanced patching code to prevent timeouts.
- All IP ranges now work.
- IP Box recoded for better usability.
- Bug that caused Client to die on startup is now fixed.
- .NET 4.0 Problems should now be gone.
- Added FOV (65-120) support under settings.
- Now checks for updates on each startup to keep users up-to-date.
- Added "TeknoGods Coop" over the multiplayer text to make it more clear.
- Lot of small bug fixes on loader.
- Version 1.4 of the game now works properly.
- Fixed "," issues with foreign language Windows.
- Added notice when joining game that makes troubleshooting easier
- Added notice when host and client have same IDs.
- Launcher now requires admin rights in order to run.

Hotfix:
- LAN hosts have now better connectivity





                            Setup:
------------------------------------------------------------------
1. Copy TeknoMW3.exe, TeknoMW3.dll to your game folder.
2. Run TeknoMW3.exe
3. On first run select nickname and fov



             Usage for Dedicated server launcher:
------------------------------------------------------------------
1. Put 'TeknoMW3_dedicated.exe' to your game folder (where 'iw5mp_server.exe' is)
2. Create shortcut or launch using command lines
3. In the shortcut / command line, feel free to add any params you 
   would normally use with dedicated server
4. Make sure the "net_masterServerPort" is NAT'ed out (it's UDP)
   for example: you're starting dedicated server with:
   +set net_masterServerPort 13337
   Make sure 13337 port will be correctly NAT'ed to your PC's 
   internal IP - otherwise no client will see your server on the
   server list.



                  Usage for MP Direct Connect:
------------------------------------------------------------------
1. Press Multiplayer
2. Enter Server IP and Port
3. Press Start (Direct Connect)
4. In game press F12 to connect.


                        Usage for MP LAN:
------------------------------------------------------------------
1. Press Multiplayer
2. Press Start (LAN Game)
3. In game go to Options -> Dedicated Server and Enable "Enable Server Browser"
4. Go back to main menu -> server browser -> LAN tab
5. Select some server
5. Join the game (double click or click connect)


                   Usage for Dedicated Server:
------------------------------------------------------------------
1. Edit your \players2\server.cfg (if needed)
2. Press Multiplayer
3. Enter server port of your choosing

   NOTE!: The port must be availble, if you enter some used port
          the server will start, but you wont be able to join.

3. Press Start Dedicated Server
4. Select map by using "map" command, for example map map_village
   or start map rotation
5. Tell clients to join


                   Usage for Singleplayer Host:
------------------------------------------------------------------
1. Press Singleplayer
2. Press Start as host
3. In game press "TeknoGods Coop" to host


                  Usage for Singleplayer Client:
------------------------------------------------------------------
1. Click Singleplayer
2. Enter IP Address
3. Press Start as client
4. In game click on "TeknoGods Coop" to join


                 Usage for getting Steam profile:
------------------------------------------------------------------
1. See Setup
2. Run Modern Warfare 3 Multiplayer from Steam
3. Press the "profile dumper" button in the TeknoMW3 loader GUI
4. Follow instructions
5. Done!

                             Note:
------------------------------------------------------------------
- This release is not intended for piracy usage!
- You must always use the launcher to run the game.


                            Support:
------------------------------------------------------------------
This release is beta quality. If something breaks, review any
pertinent comments on teknogods.com, then email me as a last resort.
Include all log files and a detailed description of problem and
how to reproduce it.



                        Special thanks:
------------------------------------------------------------------
Testers: Happy, Obso, MG, DinoSuperG, Lisfx, Crazycat, Simon,
         MWatts, Moosey




                    End User License Agreement:
------------------------------------------------------------------

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
“AS IS”  AND ANY  EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
LIMITED TO,  THE IMPLIED  WARRANTIES OF MERCHANTABILITY AND FITNESS
FOR  A  PARTICULAR  PURPOSE  ARE  DISCLAIMED. IN NO EVENT SHALL THE
COPYRIGHT OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT,
INCIDENTAL, SPECIAL, EXEMPLARY,OR CONSEQUENTIAL DAMAGES (INCLUDING,
BUT NOT  LIMITED TO,  PROCUREMENT  OF SUBSTITUTE GOODS OR SERVICES;
LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
CAUSED  AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT
LIABILITY,  OR TORT  (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN
ANY WAY OUT  OF THE USE  OF THIS  SOFTWARE,  EVEN IF ADVISED OF THE
POSSIBILITY OF SUCH DAMAGE.


                              Creds:
------------------------------------------------------------------
               Smurfette <smurfette@teknogods.com>
                  Reaver <reaver@teknogods.com>
                              Simon
            
               Questions or comments are welcomed!