https://www.make.com/
Make is a visual automation-building service that has a library of pre-built modules you can drag-and-drop into an automation workflow: "From tasks and workflows to apps and systems, build and automate anything in one powerful visual platform."
# Custom Apps & Modules
Automations in Make are based upon chaining modules of apps. An app in this case would be Dropbox, Telegram, Spotify etc. Each of these apps make available a list of modules, e.g. Upload file, Reply to message, Add to playlist, respectively. 
## Astralship Use Cases
We're going to want to build our own apps for at least the following use cases:
1. Voice note processing
	1. Archiving
	2. Transcribing (using the [[OpenAI Whisper]] module [ref](https://openai.com/research/whisper?ref=yasuhisa.com))
	3. GPT-prompting (using the [[OpenAI Completions]] module [ref](https://platform.openai.com/docs/api-reference/completions))
2. Making Asana tasks from chats e.g. `/delivering something`
3. Voice-to-Wiki

For details on building custom make apps and modules, see [[Using Custom Services]].