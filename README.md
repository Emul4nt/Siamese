# Discord Cloud Drive Bot, aka Siamese

This is a Discord bot that allows you to split files into 10MB segments, send them as messages in a text channel, read messages from a specified channel, and rebuild a file from split messages using a JSON datasbse. Meanwhile, the bot keeps track of the splitting and rebuilding process and stores records of every entry to additionally make the end-users usage simple and efficient.

# Disclaimer

- Don't use this project in a public server, and don't use this storage to upload sensitive data, remember whatever you upload is now at the hands of discord, granted they may have a little but of trouble rebuilding it without the same algorithm, but still.. don't do that.
- **ANYONE CAN USE THIS BOT TO QUERY/UPLOAD FILES ON THE SYSTEM IT'S BEING RAN ON, DON'T PUT YOUR SYSTEM AT RISK.**

### Todo:

- ✅ Add Access Controls (Checks Usage is from bot owner)
- Add an option to encrypt files

## Installation

**1. Clone the repository**
```
git clone https://github.com/Emul4nt/Siamese
```
**2. Change directories into the repository**
```
cd Siamese
```
**3. Install the required dependencies by running the following command:**
```
pip install -r requirements.txt
```

**4. Create a new Discord bot and obtain the bot token. Refer to the Discord API documentation for instructions on how to create a bot and obtain the token.**
**5. Create a file called `.env` in the same directory as `main.py` and on the first line write `TOKEN=` and then paste your bot token right after the `=` without any spaces. Then on the second line write 'OWNER=' and then paste your discord User ID, this is to verify only you can add people to the bot's whitelist.**

## Usage

**1. Invite the bot to your Discord server using the OAuth2 URL generated for your bot. Make sure to select the necessary permissions (Read messages, Send messages, Manage channels, Manage Categories, Send Files).**
**2. Launch the bot by running the Python script:**
```
python3 main.py
```

**3. The bot will be online and ready to use.**

## Commands

### Split Command

**Syntax:** `!split <file_name>` (Full path to file)
<br>
Example of correct usage: !split /home/username/large_file.exe
Example of incorrect usage: !split ~/large_file.exe

**Description:** This command takes a `file_name` as an argument and splits the file into base64 encoded 2000 character parts. Each part is sent as a separate message in a text channel. A JSON entry is generated and put into `database.json` as well as a copy is pasted into the channel for you to send to others if they need to rebuild from your entry..


### Rebuild Command


**Syntax:** `!rebuild`

**Description:** This command prompts the user to make a selection from the list of entries it has in its `database.json` file and when selected, automatically pulls the messages and decodes them from b64 from the corresponding discord server and channel, and rebuilds the original file.

### List Command

**Syntax:** `!list`

**Description:** This command lists all the available commands in the bot along with their syntax and a brief description of how they work.

## Contributing

Contributions are welcome! If you have any suggestions, improvements, or bug fixes, feel free to open an issue or submit a pull request.

## Credits

This script was created by me, myself, and I.

## License

This project is licensed under the [MIT License](LICENSE).
