# Servers

Servers are a large part of Mindustry in that they offer the ability to play the game with other people. There are two main types of servers; dedicated servers and local LAN servers. 

## Dedicated Servers

Dedicated servers are standalone, headless versions of the game that are focused only on providing a means for people to play Multiplayer. They are usually run on a computer as a separate program rather than in-game, and are operated from the terminal. These are usually stronger than a local LAN server as they have more resources available to them to support more than two or three players, and can be run 24/7. They are also more versatile and powerful in that they have many commands to provide the administrator with more control over it, and they can easily be modded to fit the administrator's needs. 

You can connect to one using the "Join Game" button under the "Play" menu. Unlike local LAN servers, you will have to enter the host's IP address and port. Also unlike local LAN servers, once you add a server, it will automatically show up on your server list when you open it, and the game will automatically check the server's status.

To establish a dedicated server, a dedicated Linux or Windows machine is **highly** recommended.

1. If you haven't already, install Java.
2. Download the desired server release from [itch.io](https://anuke.itch.io/mindustry) or [Github releases](https://github.com/Anuken/Mindustry/releases). The filename should be `server.jar` or `server-release.jar`, although if you are on Windows it may only show as `server` or `server-release`.
3. Move the server file to your desired folder. It is recommended to place it in a new directory on your desktop.
4. Open a new terminal window(CMD if you are on windows). Use the command "[cd](https://www.digitalcitizen.life/command-prompt-how-use-basic-commands/)" to navigate into the directory you placed the server file in, ex `cd Desktop` then `cd Server`. Run `java -jar [server].jar`, replacing \[server] with the name of your server file.
5. Your server should start. Type `help` for a list of all console commands. If you get a message similar to "Unable to access file server.jar" you are likely in the wrong directory.
6. Start hosting a map with the command `host <mapname> [mode]`.
7. If you are using Windows to run your server, use your favorite search engine to look up how to add rules to your Windows Firewall, as it blocks the necessary port most of the time. Make sure to allow **port 6567 TCP and UDP**.
8. To close the server, either close the terminal window or press Ctrl+C on the terminal window.

Unless you have already enabled port forwarding, your dedicated server can only be connected to by clients within your local network. If you want to make your server globally available, read below.

### What is an IP and how do I find out what mine is?

In simplified terms, an IP address is a number that identifies your computer on the internet. You can connect to someone's Mindustry server if you know their IP address. There are two types; a **public** and a **local** address.

- For a **local IP**, when for example you would like to play with a friend on the same network as yours, each device has its own way of showing it. You can Google how to do it for your device, e.g. "find local ip on Mac".
- For a **public IP**, you can simply Google "what is my ip".

### Running A Dedicated Server At Home

Most of the time, this is what you should remember; **never share your public IP with the public if you're hosting from your home, unless you acknowledge the implications of doing so!** Your public IP is tied to your household, and if it falls into the wrong hands, and when put into the wrong hands, can open up your network to vulnerabilities and dangers. **Exercise caution, do your research, and use a VPN or webhost if possible.**

It is also recommended and that you use a domain name or DNS service to mask your IP for public servers for ease of use, or even better, use a cloud service e.g. Amazon AWS or a dedicated server/VM from a hosting provider such as Linode or DigitalOcean, which is much safer. **Do your research**, and determine which option best fits your needs.

1. Find the make/model of your router. This is usually on a sticker on the bottom or back of the router.
2. Use your favorite search engine to search "port forward ASUS RT-ACRH17" and use the guide to foward **port 6567 TCP and UDP**. These instructions are different for every router, so be sure to read your guide thoroughly!
3. You can use a service such as [You Get Signal](https://www.yougetsignal.com/tools/open-ports/) to check if you have done your portforwarding correctly. 

## Local LAN & Steam Servers

A local LAN or Steam server is a server that is built into the game, and can be started using the "Host Multiplayer Game" button in the in-game menu. It is meant to be simple and straightforward, for sessions between a few players under a LAN network (aka in your household's WiFi network). It is not really meant for several players, as it takes more and more resources from your device to be able to use it that way; for that you will need a dedicated server mentioned above. It can only run when the game is open, and is immediately terminated when it is closed.

You can connect to one using the "Join Game" button under the "Play" menu. Unlike dedicated servers, your device will automatically find the host device and it will ususally appear in the server list without you having to enter the host's IP address in.

## Dedicated Server Commands

$serverCommands

## Dedicated Server Configuration Options

$serverConfigs
