## How to create a dedicated server

1. Find the make of your router. This is usually sticker on the bottom or back of the router.
2. Use your favorite search engine to search 'port forward <routerMakeNameHere>' and use the guide to foward ports *6567 TCP and UDP*. **These instructions are different for every router.**
3. Use your favorite search engine to search how to add rules to your firewall(windows firewall is on by default), allow *6567 TCP and UDP*.
4. Grab the [newest server.jar from itch.io](https://anuke.itch.io/mindustry). If you're running Windows, double-click `run-server.bat`. Otherwise, navigate to its location with command prompt and run `java -jar server.jar` to start the program.
5. Type `host` into the server console to begin hosting with a specific map and gamemode. You can ensure it is working if [this site](https://www.yougetsignal.com/tools/open-ports/) reports that port `6567` is open.
6. (Optional) Consider using a service like https://noip.com/ to share your server address more easily.
