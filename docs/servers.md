# Servers

Servers are a large part of Mindustry in that they offer the ability to play the game with other people. There are two main types of servers; dedicated servers and local LAN servers.

## Dedicated Servers

Dedicated servers are standalone, headless versions of the game that are focused only on providing a means for people to play Multiplayer. They are usually run on a computer as a separate program rather than in-game, and are operated from the terminal. These are usually stronger than a local LAN server as they have more resources available to them to support more than two or three players. They are also more versatile and powerful in that they have many commands to provide the administrator with more control over it, and they can easily be modded to fit the administrator's needs. 

To establish a dedicated server, a dedicated Linux or Windows machine is **highly** recommended.

1. If you haven't already, install at least JRE and JDK 8.
2. Download the desired server release from [itch.io](itch.io), or compile one yourself. 
3. Open a terminal or TTY session then change `cd` to the directory the JAR is placed in.
4. Run `java -jar server.jar` using Command Prompt (on Windows) or your favorite terminal (on Linux and Mac). The commands are explained in the `help` command.
3. If you are using Windows to run your server, use your favorite search engine to look up how to add rules to your Windows Firewall, as it blocks that port most of the time. Make sure to allow **port 6567 TCP and UDP**.

If you want your server to be publicly available around the world, then read the following. If not, then you are done! Before starting though, be sure that you have permission to your router's admin settings. 

Most importantly, **never share your public IP with the public, unless you acknowledge the implications of doing so!** Your public IP is tied to your household, and if it falls into the wrong hands, it can be used to **easily** find your approximate location, even down to the city or block you live in. There is more that can happen; such as DoS attacks, data and information exploitation and collection, and unwanted access to other open ports in your network. **Exercise caution, do your research, and use a VPN if possible.**

If you would like to host a public server for public use, it is recommended that you use a domain name or DNS service to mask your IP a little bit, or use a cloud service e.g. Amazon AWS which is much safer. Again **do your research**.

1. Find the make/model of your router. This is usually on a sticker on the bottom or back of the router.
2. Use your favorite search engine to search 'port forward [your router make/model/name here]' and use the guide to foward **port 6567 TCP and UDP**. These instructions are different for every router, so be sure to read your guide thoroughly!
3. You can use a service such as [You Get Signal](https://www.yougetsignal.com/tools/open-ports/) to check if you have done your portforwarding correctly. 
