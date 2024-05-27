# Why 
The audio bot is needed to create a seamless audio-to-wiki pipeline, so that pirates and partners can add to wiki wit their voice. The audio-to-wiki pipeline is used during [[Docking]] and [[Voyage|Voyaging]].
# What
## Archiving
The [telegram bot](https://www.make.com/en/help/app/telegram-bot) will be built using [[Make]], a handy integration-building service, to download audio files and save them to an [[Audio Archiving]] location, such as Dropbox. 
![[Pasted image 20231215194034.png]]
## Processing
Beyond archiving the file, we can write custom modules that refer to API endpoints made available in a [[FaaSD]] microservice and do whatever we like. For example, one desirable workflow that develops the [[Docking]] on-boarding process might be:
1. Watch for voice notes in Telegram
	2. Filter for: is voice note 
2. Download the file
3. Refer to custom API endpoint
	1. Generate transcript
	2. Transform with GPT prompt
	3. Write result to telegram chat
4. Archive/ upload file to remote storage
# Where
See [[FaaSD]] and [[Digital Ocean]].
See review of [[Audio Archiving]] platforms.  
# How
The following steps outline how to create a telegram bot and Make integration:
1. Message @BotFather, to create a new telegram bot and register it. You'll receive a link where you can begin messaging with the bot, as well as a token - keep this safe!
2. Jump over to Make and start with [the following Telegram-Dropbox template](https://eu2.make.com/templates/3093-save-new-telegram-files-to-dropbox). This template has three modules:
	1. Telegram: watch for updates 
	2. Telegram: download a file
	3. Dropbox: upload a file
3. In between modules 1 and 2 there's a filter which allows through only messages containing a voice file attachment. 
4. The file ID for the voice recording is used to download the file from the Telegram server and upload it to Dropbox. 
5. Message sent on success:
	![[Pasted image 20231215195220.png]]

Head on over to [[Box Watching]] to see how the file is picked up for processing. 