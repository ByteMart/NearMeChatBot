# Configuration Guide for Bot `.env` File

Use the `.env` file to set the bot's required variables. Below is a detailed explanation of each variable:

## Essential Variables

* **DOMAIN**: The bot's domain (required).
* **DB\_PASS**: MySQL Database Password (required).
* **TOKEN**: The bot's token (required).
* **BOT\_USERNAME**: The username of the bot without `@` sign (required).
* **ADMIN**: The unique identifier of the bot's administrator (required).
* **SUPPORT\_USERNAME**: The username for the bot's support contact.

## Channel Configuration

* **AVATAR\_ARCHIVE**: The private channel where public avatars are saved. The bot must have admin privileges in this channel (required).
* **channel\_username**: The username of the public channel without `@` sign where users may need to join. The bot must have admin privileges in this channel (required).
* **reqChannelJoin**: Specifies if users are required to join the `channel_username` before using the bot. Set to `true` or `false` as needed. If enabled, the bot must have admin privileges in the channel (required).

## User Limits

* **daily\_view**: The number of daily views allowed per user.
* **nearby\_view**: The number of daily nearby views allowed per user.
* **daily\_message**: The number of daily messages a user can send.
* **daily\_message\_hour**: The hour at which the daily message count resets.

## Referral and Gifting Features

* **giftRef**: Enables VIP membership for invitees (`true` or `false`).
* **minRef**: Minimum required invites for an invitee to gain VIP membership.
* **enable\_gift**: Enables free gifting (`true` or `false`).
* **GIFT\_LIMIT**: Total number of gifts allowed within the specified hour.
* **GIFT\_LIMIT\_HOUR**: Time window (in hours) during which a user can request gifts.
  Example: If `GIFT_LIMIT_HOUR=3` and `GIFT_LIMIT=5`, a user can request up to 5 gifts in 3 hours.
* **GIFT\_MINUTES**: Duration of each gift in minutes.

## Subscription Pricing

Set the prices for various subscription durations (in **STAR**):

* **subscriptions\_1month\_price**: Price for a 1-month subscription.
* **subscriptions\_3month\_price**: Price for a 3-month subscription.
* **subscriptions\_6month\_price**: Price for a 6-month subscription.
* **subscriptions\_12month\_price**: Price for a 12-month subscription.

## Debugging

* **DEBUG\_BOT\_TOKEN**: Optional bot token used for debugging.

---

# Installation Guide

### System Requirements

* **Operating System**: Ubuntu Server 24.04
* **RAM**: 1 GB (2 GB Recommended)
* **CPU**: 1 core
* **Storage**: 10 GB

---

### Steps

**1. Transfer Files**

Use `scp` to transfer the `nearmechat.zip`:

```bash
scp path/to/nearmechat.zip user@server_ip:~
```

**2. Log into Server**

```bash
ssh user@server_ip
```

**3. Extract Files**

```bash
apt install unzip
unzip nearmechat.zip && cd nearmechat
```

**4. Modify `.env`**

* **TOKEN**: Obtain from [BotFather](https://t.me/BotFather)

* **Channel ID (AVATAR\_ARCHIVE)**: Use [MetaInfoBot](https://t.me/MetaInfoBot).
  Forward a message from the channel and look for:

  ```json
  { "forward_origin": { "type": "channel", "chat": { "id": -111111 } } }
  ```

* **User ID (ADMIN)**: Send a message to MetaInfoBot and look for:

  ```json
  { "from": { "id": 222222 } }
  ```

* Ensure your domain is pointed to your server IP.

**5. Run Setup Script**

```bash
chmod +x setup.sh
./setup.sh
```

**6. Update Code**

```bash
chmod +x update.sh
./update.sh
```

**7. Set Bot Commands**

* Edit `menu.txt` with format:

```text
command - description
```

* Update bot commands:

```bash
chmod +x commands.sh
./commands.sh
```

**8. Admin Menu**

Send the `/admin` command in the bot to view admin options.

---

## 💸 Get **\$200 Free Credits** on DigitalOcean

Run your bot for free — Start building now! 🚀

🔗 [https://m.do.co/c/19e0ec5ff2b1](https://m.do.co/c/19e0ec5ff2b1)

[![DigitalOcean Badge](https://web-platforms.sfo2.cdn.digitaloceanspaces.com/WWW/Badge%201.svg)](https://www.digitalocean.com/?refcode=19e0ec5ff2b1&utm_campaign=Referral_Invite&utm_medium=Referral_Program&utm_source=badge)

---

© 2025 [ByteMart.XYZ](https://bytemart.xyz) – All Rights Reserved

