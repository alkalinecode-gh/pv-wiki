# Proxy

{{% hint info %}}
When the server is being hit with a **DDoS attack**, the scope in which it affects gameplay is often very limited. We want to keep our in-game chat and Discord channels engaging and helpful, and reports of only minor network incidents are not beneficial to this. For this reason, we would greatly appreciate it if you **only report increased lag when it persists over a long period of time and multiple proxies**, and to do so via the proper communication channel; **creating a ticket in our Discord server** - please keep discussions about lag out of chat and #general!

Additionally, not sending any reports via **#tickets** may result in server administrators not knowing about the issue, thus being unable to help resolve it. A **#ticket** in this scenario would be appreciated so we can swiftly solve any ongoing connection issues.
{{% /hint %}}

{{% details "General Description" open %}}
## What is it
A **proxy** routes your connection to the backend servers running **PureVanilla**, instead of connecting you directly to the server running **PureVanilla**.

## How this benefits us
We must use **proxies** because the **Minecraft protocol** does not support server switching when being connected to a server, which would make our **multi-gamemode multi-instance** scheme not viable.

The **proxy** internally simulates a normal Minecraft server but routes the packets to the end server dynamically based on the **gamemode** you play.

Additionally, the use of **proxies** hides the backend server **IPs**, preventing **DDoS attacks** to core infrastructure, and making the proxies, which are more abundant, the only user-facing (network-wise) element of the server.

## How this benefits you
In addition to the **reliability improvements** mentioned above, we host multiple **proxies** all around the world which use **datacenter-grade connections** to route your connection between the **proxy** and the backend server, lowering the overall **latency** for your connection.
{{% /details %}}

## Location list
{{% hint warning %}}
Please, keep the default ``play.purevanilla.co`` address (or other ``*.purevanilla.co`` addresses not listed below) on your server list, and avoid sharing forced addresses with other players without advising them of their __caveats__.
- We might decide to drop support for any given location at any time, causing that IP to stop working
- Forced locations do not support failover, meaning, if that location is down, a healthy location won't be provided (giving worse results than the default IP)
{{% /hint %}}
We continuously add and remove **locations** based on server popularity all around the world.
|Country|Region|City|IP|Count  |
|--|--|--|--|--|
|🇩🇪 DE| Central | Frankfurt | ``eu.purevanilla.co`` | 2 |
|🇺🇸 US| Central | Dallas | ``us.purevanilla.co``<br>``central.us.purevanilla.co`` | 1 |
|🇺🇸 US| West | Hillsboro | ``us.purevanilla.co``<br>``west.us.purevanilla.co`` | 2 |
|🇺🇸 US| East | Vint Hill / Ashburn | ``us.purevanilla.co``<br>``east.us.purevanilla.co`` | 1 |
|🇦🇺 AU| Australia | Sydney | ``au.purevanilla.co`` | 1 |
|🇸🇬 SG| Southeast Asia | Singapore | ``sg.purevanilla.co`` | 1 |

You can consult their **status** and precise **location** from our [**status page**](https://purevanilla.co/status).


## Location resolution
When using any address ending in ``*.purevanilla.co``, you'll be connected to the closest **proxy location** (using Google Cloud datacenter sibling locations) to you. If there are multiple suitable proxies for your location, the traffic will be equally balanced between all of them, and the one you connect to is recomputed every **5 minutes**, with equal chances every time.

This means, if you **relog 5 minutes after first logging in**, you may or may not be connected to the same **proxy**. This also means, if any portion of the proxies close to you are performing below expectations, reconnecting may solve any apparent performance issues.

This also means using any ``*.purevanilla.co`` will result in the exact same **performance** and **balancing algorithm** (e.g. ``a.purevanilla.co`` and ``b.purevanilla.co`` behave the same).

## Forced connection
**It is not advised** to use or share a forced location IP with anyone, as the automatic IP ``play.purevanilla.co`` will ensure the best possible connection in most cases. Please, refrain from sharing forced locations with other players without advising them to keep the default ``play.purevanilla.co`` address on their server list.

## DDoS mitigation
All our providers have **DDoS mitigation services** which we are using, but **PureVanilla** has grown so popular certain attacks may be able to temporarily affect the connection to some of the proxies. These attacks are usually detected within minutes and the server is usually back online in a couple minutes. If it isn't, **relogging every 5 minutes** may improve your connection due to the **location resolution algorithm** described above.