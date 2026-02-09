# Persistent Player Profiles (PPP)

> **Track and explore player stats, kills, playtime, and connections across Arma Reforger servers**

[![Website](https://img.shields.io/badge/Website-ppp.flabby.dev-blue?style=flat-square)](https://ppp.flabby.dev)
[![Discord](https://img.shields.io/badge/Discord-flabby.dev/discord-7289DA?style=flat-square&logo=discord&logoColor=white)](https://flabby.dev/discord)
[![Mod Version](https://img.shields.io/badge/Mod%20Version-1.8.0-green?style=flat-square)](https://reforger.armaplatform.com/workshop/664E179167426778-PlayerProfilesbyflabby)

Persistent Player Profiles is a comprehensive stat tracking system for Arma Reforger that records and displays player statistics including kills, deaths, playtime, chat messages, connections, and gameplay sessions.

---

## 🖥️ For Server Owners

### Why Use PPP?

- **Player Retention** - Players love seeing their stats and progression
- **Community Building** - Leaderboards and Discord integration foster competition
- **Administration Tools** - Track player activity, connections, and behavior
- **Customizable** - Full control over what data is tracked and displayed

### 🚀 Quick Setup

#### 1. Install the Mod

1. Visit the [PPP Mod on Arma Reforger Workshop](https://reforger.armaplatform.com/workshop/664E179167426778-PlayerProfilesbyflabby) (or search "Persistent Player Profiles")
2. Subscribe to the mod
3. Add the mod to your server's mod list
4. Restart your server

**Note:** The mod will automatically create a configuration file at `$profile:PersistantPlayerProfileCFG.json` on first run.

#### 2. Create Server Account

1. Visit [ppp.flabby.dev](https://ppp.flabby.dev)
2. Create an account and link your Discord
3. Wait for staff approval
4. Contact project staff to register your server

#### 3. Configure the Mod

The mod will automatically create a configuration file:
```
$profile:PersistantPlayerProfileCFG.json
```

Default backend URL: `https://profiles-backend.flabby.dev/`

Your server will receive API credentials automatically upon first connection.

#### 4. Configure Web Settings

Once your server is registered:
1. Log in to [ppp.flabby.dev](https://ppp.flabby.dev)
2. Navigate to your server tools page: `/server/YOUR_SERVER_ID/tools`
3. Configure settings:
   - **Visibility Settings** - Control what players can see
   - **Discord Webhooks** - Set up event notifications (kills, connections, mission starts)
   - **Discord Integration** - Link your Discord server ID for bot commands
   - **Stats Update Delay** - Configure how often stats refresh

### 📡 Data Collection

The mod automatically collects and sends:

- **Player Connections** - Connection/disconnection events with timestamps
- **Playtime** - Periodic updates every 5 minutes (configurable)
- **Kills & Deaths** - Complete kill feed with weapon, faction, coordinates
- **Chat Messages** - In-game chat for moderation and history
- **Mission Starts** - Server mission changes and details

All data is batched and sent efficiently to minimize server load.

### 🎛️ Server Configuration Options

#### Visibility Settings
- `playerCanSeeChats` - Allow players to view their chat history
- `playerCanSeeConnections` - Show connection logs on player profiles
- `playerCanSeeSessions` - Display session details to players
- `serverProfileIncludesKills` - Include kill stats in profiles
- `serverProfileIncludesChats` - Include chat history in profiles
- `serverProfileIncludesConnections` - Show connection logs

#### Discord Webhook Settings

Configure real-time notifications to Discord channels:

**Kills Webhook**
- Player names
- Timestamps
- Weapon information
- Profile links
- Friendly fire indicators

**Connections/Disconnections Webhook**
- Player names
- Timestamps
- Duration of sessions
- Profile links

**Mission Starts Webhook**
- Mission details
- Timestamps
- Server information

#### Discord Bot Integration
- Set your Discord server ID
- Set channel ID for leaderboards
- Configure leaderboard refresh time (in minutes)
- Players can use `/myprofile` to view their stats
- `/leaderboard` shows top players by kills or playtime

### 🔧 Technical Details

**Batch API Endpoint**: `POST /batch`
- Maximum batch size: 100 items per request
- Automatic credential management
- Efficient queuing system (max 500 items)
- Automatic retry logic

**API Authentication**:
- `x-api-access-id` header
- `x-api-access-key` header
- Credentials provisioned automatically

**Mod Version**: 1.8.0

**Backend**: Node.js/Express with MySQL database

**Frontend**: SvelteKit with responsive design

### 📊 Admin Web Interface

Access your server management panel at:
```
https://ppp.flabby.dev/server/YOUR_SERVER_ID/tools
```

Features:
- Real-time statistics dashboard
- Player lookup and management
- Webhook configuration and testing
- Visibility settings control
- Server profile customization
- Leaderboard management

### 🛠️ Troubleshooting

**Server not collecting data?**
- Check mod is installed and loaded
- Verify configuration file exists
- Check server logs for PPP errors
- Ensure server has internet connectivity

**Players not seeing their stats?**
- Verify player has created and linked their account
- Check visibility settings are enabled
- Ensure player has played on your server
- Stats may take a few minutes to appear (check statsUpdateDelay setting)

**Discord bot not working?**
- Verify Discord server ID is correct
- Check bot has proper permissions in your Discord
- Ensure server is linked in web interface

### 📞 Support

For server setup assistance or technical support:
- Join our Discord: [flabby.dev/discord](https://flabby.dev/discord)
- Contact project maintainers through the website

---

## 🏗️ Development

This project consists of four main components:

### Components

1. **Frontend** (`frontend/`) - SvelteKit web application
2. **Backend** (`backend/`) - Node.js/Express API server  
3. **Mod** (`mod/`) - Arma Reforger mod (Enforce Script)
4. **Discord Bot** (`discord/`) - Discord.js bot for profile commands

### Technologies

- Frontend: SvelteKit, TypeScript, Bulma CSS
- Backend: Node.js, Express, MySQL
- Mod: Enforce Script (Arma Reforger)
- Discord: Discord.js

---

## 🏷️ Tags

`arma-reforger` `player-stats` `stat-tracking` `game-server-mod` `discord-bot` `player-profiles` `kill-tracker` `playtime-tracker` `gaming-statistics` `server-mod` `arma` `reforger` `multiplayer` `gaming` `stats` `leaderboards` `discord-integration` `player-tracking` `session-tracking` `game-analytics` `server-administration` `community-tools` `open-source` `sveltekit` `nodejs` `mysql` `typescript` `bohemia-interactive` `persistent-data` `game-mod`
