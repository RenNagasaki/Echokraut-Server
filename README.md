[![Discord](https://img.shields.io/badge/Join-Discord-blue)](https://discord.gg/5gesjDfDBr)

# Echokraut-Server
This is the backend All-in-One solution for [Echokraut](https://github.com/RenNagasaki/Echokraut), my FFXIV - [Dalamud](https://github.com/goatcorp/Dalamud) Plugin. 
It's goal is to enable the user to use [AllTalk_TTS](https://github.com/erew123/alltalk_tts) without learning the tool inside out. It installs it, configures it for FFXIV use and is able to start/stop it with a simple mouseclick.

## Dislaimer: 
* Since this tool is dependent on [AllTalk_TTS](https://github.com/erew123/alltalk_tts) it is important to note that at the moment on Windows only Nvidia GPUs are supported. On Linux AMD should work as well. In the future this will (hopefully) expand.
* Self hosted TTS is currently heavily dependent on a strong GPU. It's recommended to have at least a RTX 3060 (or AMD equivalent on Linux) with 6+GB VRAM built into the system hosting [AllTalk_TTS](https://github.com/erew123/alltalk_tts) for inference. (Keep in mind thats just for inference.)
* This plugin is still in it's early stages of development, feel free to report any issues here or on my [![Discord](https://img.shields.io/badge/Join-Discord-blue)](https://discord.gg/5gesjDfDBr) (preferred)

## Planned Features
* I'm currently looking in getting emotions to work for TTS meaning that people could use [angry] in their chats and the voice would sound angry. The raw dialogue text for story or quests sometimes contains stuff like <pant> for when a npc is exhausted and more. I aim to use that for more detailed voicing.
* I'm still trying to figure out a way to identify "???" Dialogues to set the correct voice if possible. At the moment Dialogues with "???" as name get identified as a single NPC called "???" resulting in wrong voices.

## Setup/Install
* Setup [AllTalk_TTS](https://github.com/erew123/alltalk_tts) -> Refer to this site on how to install (Branch v2_Beta preferred. It's faster, easier to use, and more reliable).
* (Optional) Finetune the xtts2 model to your own voices. Will sound better than simple voice cloning.
* (Optional) To create your own trained voice model on your own FFXIV GameData, check out: [Echokraut Tools](https://github.com/RenNagasaki/Echokraut-Tools)
* Add the following path to the experimental paths of [Dalamud](https://github.com/goatcorp/Dalamud): `https://raw.githubusercontent.com/RenNagasaki/MyDalamudPlugins/master/pluginmaster.json`
* Search for 'Echokraut' in Dalamud and install the plugin
* Open the settings window either via the button or by typing `/ek`
* In the 'Settings -> Backend' Tab enter the url of your [AllTalk_TTS](https://github.com/erew123/alltalk_tts) instance. (127.0.0.1:7851 should be default)
* If clicking 'Test Connection' results in `ready` you're set.
* (IMPORTANT) The naming scheme of the voices should be like this: `GENDER_RACE_NAME.wav`.
  For example: `Male_Hyur_Thancred.wav` for a named NPC
  and `Male_Hyur_NPC1.wav` for a random Hyur NPC. If more than one NPC voice exists then the plugin selects one randomly the first time you meet a new NPC. IMPORTANT: Number the NPCs in an increment(NPC1, NPC2 ...). Do not skip a number. This will produce problems!!!
* There is one exception, the so called narrator voice. It gets used for all dialogues without a speaker and all NPCs where no other voice could be found (last fallback) and should be named `Narrator.wav` (Always should be existing).
* For NPCs with multiple names (Nanamo Ul Namo/Lilira) or same voice actor take a look at this file: [VoiceNames](https://github.com/RenNagasaki/Echokraut/blob/master/Echokraut/Resources/VoiceNamesDE.json) or the one matching your language. If there is no entry for one you're expecting feel free to add a pull request. These files are in the works while people use the plugin. (I can't fill this for other languages)
* Small example of how the files should be named:
* ![grafik](https://github.com/user-attachments/assets/7a879f5d-9753-423b-a6cc-850871f6eba9)

## Just starting
I started this whole project as a way for me to enjoy replaying the game without having to read all of 2.0 again. It evolved from there so please bear with many features still missing. You can always request more. 😊

## Thanks
* Everyone contributing on the plugin-dev and dalamud-dev channels on the official [Dalamud](https://github.com/goatcorp/Dalamud) discord!
* Some parts of the code are taken from/inspired by:
    [TextToTalk](https://github.com/karashiiro/TextToTalk).
    [XivVoices](https://github.com/arcsidian/XivVoices).
