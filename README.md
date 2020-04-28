# Slack Admins
Slack bot to create & maintain a private "admins only" channel automatically 🎉 - think of it as like "modmails", except in Slack.

## Usage
When you first install the bot, it will create an `#admins` channel (if it already exists, it will use that, **BUT** do note that people might get kicked out from that channel, so if you have an existing `#admins` channel, it's recommended that you rename that before installing the bot in your workspace).

The bot will scan through the list of people in the workspace and select the admins and owners (collectively called "admins"). Then, it will "sync" that list with the `#admins` channel, so that any admins not already on the channel will be joined, and anyone in the channel that *isn't* an admin will be kicked out.

Once the initial synchronization is complete, it will then keep the members of the `#admin` channel and the list of workspace admins synced - this involves kicking out if someone becomes a non-admin, and being invited if someone becomes an admin.

This also works the other way around - if someone joins the channel, they will be automatically promoted to an admin (if they weren't an admin/owner already), and if someone leaves, they'll be automatically demoted to a regular user.
