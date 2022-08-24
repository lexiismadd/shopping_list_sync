# Todoist Alexa Shopping List sync
Sync Todoist Alexa Shopping List with HA Shopping List

This is a fork of MrLemur's original code found at https://community.home-assistant.io/t/sync-your-alexa-todoist-shopping-list-to-the-home-assistant-shopping-list.  All credit to MrLemur for doing the hard work.
All I did was update it with my limited python knowledge to use async calls instead of task.executor.


## What does this setup do?

Sync a list from Todoist to the Home Assistant shopping list component. If you sync Alexa to Todoist, you can have Home Assistant and Alexa share the contents of the shopping list.

This script provides a service to sync the HA shopping list with the Todoist list. The Todoist list will overwrite the one stored by HA. When an item is checked or added to the HA list, it will be updated on the Todoist list. Optionally if you setup webhooks from Todoist, you can have HA sync the shopping list automatically whenever something changes.

### Requirements

1. [pyscript](https://github.com/custom-components/pyscript): Pyscript adds rich Python scripting to HASS (enable the global HASS variable when setting up)
2. [Todoist API key](https://todoist.com/prefs/integrations)
3. Todoist project ID (when on your Alexa Shopping List project, use the ID at the end of the URL)

### Installation

1. Copy the file 'pyscript/shopping_list_sync.py' to your config/pyscript/ folder
2. Copy the file 'pyscript_modules/write_file.py' to your config/pyscript_modules/ folder
3. Restart pyscript

Run the service pyscript.sync_shopping_list from developer tools.

You should now have a synced list. Note this will remove everything you have in the current shopping list, so add the items to Todoist first.

To make sure newly added items from Todoist are added to HA, follow MrLemur's instructions at https://community.home-assistant.io/t/sync-your-alexa-todoist-shopping-list-to-the-home-assistant-shopping-list
