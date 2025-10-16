# 💎 OPC System (Online Point Currency) 🚀
**A comprehensive Lua script for the GrowSoft platform.**

This script establishes a dynamic, server-side Online Point Currency (OPC) system, featuring automated rewards, an in-game shop, player-to-player transfers, and an administrative control panel.

## ✨ Core Features

| Feature | Description | Command | Access Role |
| :--- | :--- | :--- | :--- |
| **Automated Rewards** | Earn **1 OPC** every **5 minutes** (interval is configurable). | N/A | Default |
| **In-Game Shop** | Purchase categorized items with your OPC balance. | `/opc` | Default |
| **P2P Transfer** | Send OPC directly to other online players. | `/sendopc <player> <amount>` | Default |
| **Admin Panel** | Manage shop items and set the reward interval. | `/opcadmin` | **Admin (ID 52)** |
| **Leaderboard** | View the top 25 richest players. | `/opclb` | Default |

***

## 🛠️ Commands & Usage

### 1. General Player Commands (Default Role)
| Command | Usage Example |
| :--- | :--- |
| **`/opc`** | Opens the **Online Point Market** shop dialog. |
| **`/opclb`** | Displays the OPC Leaderboard (Top 25). |
| **`/sendopc`** | ` /sendopc GrowDev 100 ` |

### 2. Administrative Tools (Developer/Admin Roles)

> [!CAUTION]
> These commands require **Developer (ID 51)** or **Admin (ID 52)** role access.

| Command | Action |
| :--- | :--- |
| **`/opcadmin`** | Opens the dedicated panel for shop and system management. |
| **`/giveopc`** | ` /giveopc TargetPlayer 500 ` (Adds OPC) |
| **`/removeopc`** | ` /removeopc TargetPlayer 500 ` (Removes OPC) |

***

## ⚙️ Administration Panel Features

The `/opcadmin` panel provides full control over the system configuration and economy:

### Item Management
-   Add or remove items from the **Starter**, **Popular**, and **Premium** shop sections.
-   Requires valid ItemID, Quantity, and Price.

### System Configuration
-   **Update Reward Interval:** Adjust the frequency of the automated OPC reward. Input the new value in **seconds**. (e.g., set to `180` for a 3-minute interval).

> [!NOTE]
> All changes made in the Admin Panel are **permanently saved** to the server's data.



The script implements a full-fledged in-game currency system for the GrowSoft platform, offering customizable functionality for player rewards, item purchasing, and administration.

1. Automated Currency System (OPC)

Automatic Rewards: Online players automatically receive 1 OPC at a set interval.

Customizable Interval: The reward frequency can be dynamically adjusted via the Admin Panel (default is 300 seconds / 5 minutes).

Reliable Tracking: Uses accurate server timers to track player online time, with mechanisms to start, pause, and clear timers upon player entry, exit, or disconnection, ensuring stability.

2. In-Game Shop (/opc)

Item Purchase: Allows players to purchase various items using their OPC balance.

Categorized Structure: The shop is organized into three main categories for better navigation: Starter, Popular, and Premium.

Confirmation Dialog: Displays a clear purchase confirmation dialog detailing the item, quantity, price, and the player's current balance.

Safety Checks: Automatically verifies the player's inventory space (MAX_INV_CHECK) before completing a purchase.

Notifications: Provides console messages, talk bubbles, and sound effects for successful or failed transactions.

3. Player-to-Player (P2P) Transfer (/sendopc)

Currency Transfer: Allows any player to send a specified amount of OPC to another currently online player.

Balance Validation: Ensures the sender has sufficient OPC before initiating the transfer.

4. Leaderboard (/opclb)

Global Ranking: Displays a list of the Top 25 players based on their total OPC balance.

Data Consistency: Utilizes a stored mapping of UserIDs to player names for accurate and persistent display on the leaderboard.

5. Dedicated Admin Panel (/opcadmin)

Access Control: Restricted to players with the Admin Role (ID 52).

Shop Item Management:

Add Item: Administrators can add new items to any of the three shop categories by specifying the ItemID, Quantity, and Price.

Remove Item: Allows administrators to remove existing items from any category directly via the panel.

System Configuration:

Reward Interval: The OPC reward interval (in seconds) can be changed and saved permanently from the panel.

Persistent Saving: All changes made to the item lists and the reward interval are permanently saved to the server data.

6. Administrative Commands (Dev Role)

Role Required: Commands are restricted to players with the Developer Role (ID 51) or higher.

/giveopc <player> <amount>: Instantly adds OPC to a target player's balance.

/removeopc <player> <amount>: Instantly subtracts OPC from a target player's balance (cannot go below zero).
