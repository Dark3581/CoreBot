<div id="top"></div>

[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]

<!-- PROJECT LOGO -->
<br />
<div align="center">
  <img src="https://cdn.discordapp.com/attachments/849289892068065310/954062297003860028/logo.png" alt="Logo" width="80" height="80">

  <h3 align="center">Core Bot</h3>

  <p align="center">
    Packed with features, highly customisable through our config file, easy to setup, and everything you could need for your server!
    <br />
    <br />
  </p>
</div>

<!-- ABOUT THE PROJECT -->
## About The Project

Core Bot is a multipurpose discord bot, to serve all users with many features to easily setup and manage your servers, as well as providing some fun commands for the members of your server. It was intended to be used in all types of discords, development, game servers, community servers, etc. We hope to bring you a free, reliable and up to date bot to fulfill your needs.

Some of the features:
* Economy System (Balance, Pay, Coinflip, etc)
* Moderation Commands (kick, ban, mute, globalban, etc)
* Giveaway System
* Announcement Embeds
* Dropdown Role Selection
* Autoroles

<!-- GETTING STARTED -->
## Getting Started

### Prerequisites

This is an example of how to list things you need to use the software and how to install them.
* NodeJS >= v16.13.0
* npm
  ```sh
  npm install npm@latest -g
  ```

### Installation

1. Clone the repo or download the files
   ```sh
   git clone https://github.com/neurondevelopment/CoreBot.git
   ```
2. Install NPM packages
   ```sh
   npm install
   ```
3. Fill in the information in `config.json`, the following fields are required for the bot to start
   ```js
   token serverID
   ```
4. Invite or reinvite the bot with the following link, replace YOURCLIENTID with the Client ID of your bot
   ```
   https://discord.com/api/oauth2/authorize?client_id=YOURCLIENTID&permissions=8&scope=applications.commands%20bot
   ```
5. In the discord developer dashboard, where you created your bot and got its token, scroll down to 'Privileged Gateway Intents' and tick the SERVER MEMBERS intent.
6. Starting the bot
   ```sh
   node .
   ```
   **OR**
   
   ```sh
   node index.js
   ```

### Dropdown Roles
They can be set / updated by running the `/sync` command


Dropdown Roles can be found in /db/dropdownRoles.json

```js
"123456789": { // Enter the channel ID for the embed to be sent to
        "message": "Get your roles below", // Message on the embed
        "roles": {
            "roleName": { // The name of the role shown in the dropdown menu
                "description": "description",
                "emoji": "",
                "roles": [""] // The roles that this option will provide, specify the role IDs
            }
        },
        "donttouch": "" // Message ID of the embed, will be filled out automatically by the bot
    }
```
<br>

### Tickets
They can be set / updated by running the `/sync` command

Tickets can be found in /db/tickets.json

```js
{
    "exampleTicket": { // Name of the ticket, will be shown on the embed
        "donttouch": "", // Message ID of the embed, will be filled out automatically by the bot
        "messageChannelID": "", // The ID of the channel that the embed will be sent to
        "categoryID": "", // The ID of the category that tickets will be added to
        "supportroles": [""], // The support roles for this ticket type, will be able to claim tickets. Specify their Role IDs
        "message": "Welcome to your ticket {[USER]}", // Message sent when the ticket is opened, use {[USER]} to ping the user
        "closeMessage": "Your ticket has been closed", // Message sent to the user via DMs when their ticket is closed
        "embed": {
            "description": "This is an example ticket, click the button below to create!",
            "colour": "AQUA",
            "image": ""
        },
        "button": {
            "label": "Open Ticket",
            "buttonStyle": "SECONDARY",
            "emoji": "🎫"
        }
    }
}
```
### Global Commands
Some users may find they need to use global commands instead of guild commands, so that they can use the commands in multiple servers. Below is a simple guide for that, just note that any updates to commands will take ~1 hour to update in discord's cache when using global commands.

In the index.js, replace `Routes.applicationGuildCommands(client.user.id, serverID)` with `Routes.applicationCommands(client.user.id)`, make sure you don't accidentally remove the comma after it either. 


<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE` for more information.

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/neurondevelopment/CoreBot.svg?style=for-the-badge
[contributors-url]: https://github.com/neurondevelopment/CoreBot/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/neurondevelopment/CoreBot.svg?style=for-the-badge
[forks-url]: https://github.com/neurondevelopment/CoreBot/network/members
[stars-shield]: https://img.shields.io/github/stars/neurondevelopment/CoreBot.svg?style=for-the-badge
[stars-url]: https://github.com/neurondevelopment/CoreBot/stargazers
[issues-shield]: https://img.shields.io/github/issues/neurondevelopment/CoreBot.svg?style=for-the-badge
[issues-url]: https://github.com/neurondevelopment/CoreBot/issues
[license-shield]: https://img.shields.io/github/license/neurondevelopment/CoreBot.svg?style=for-the-badge
[license-url]: https://github.com/neurondevelopment/CoreBot/blob/main/LICENSE


