# Information
Repository for general information, documentation and overall comments.

Please join our slack channel #won-hackathon-2019

[![Join the chat at https://join.slack.com/t/webofneeds/shared_invite/enQtNzc0NjM0MzY3NTIyLTMwZmY1YTljMjMzYjJhMjJkYjYxM2MyMDdmMjU4ZTE4MDM4NWFiNDJiNWMyZGNjYTliYjA4NWYzY2RjMGY5YWE](https://img.shields.io/badge/slack-join%20chat-informational.svg)](https://join.slack.com/t/webofneeds/shared_invite/enQtNzc0NjM0MzY3NTIyLTMwZmY1YTljMjMzYjJhMjJkYjYxM2MyMDdmMjU4ZTE4MDM4NWFiNDJiNWMyZGNjYTliYjA4NWYzY2RjMGY5YWE)

# Preparation
Things you'll need:
* Java 8 (other versions may not work) - For running a bot, you'll need OpenJDK 8 (standard on linux, Windows installer can be found at [AdoptOpenJdk.net](https://adoptopenjdk.net/index.html). 
* Maven
* Git
* Some java development enviroment (Eclipse or Intellij, or do you have a better one?)
* Make sure you have a system shell that you are comfortable with. On Windows, if unsure, take Git Bash.
* Download [blazegraph](https://sourceforge.net/projects/bigdata/files/bigdata/)

# Team Projects
Overview of the projects the teams are working on. 

Please add one bullet point for each of your projects and describe them in a little more detail in your team page.

* [**AirQualityBot**](teams/air-quality-bot.md#airqualitybot-1): A [WebOfNeeds](https://github.com/researchstudio-sat/webofneeds)-Bot to regularly fetch air quality data from https://docs.openaq.org/ and publish them as WoN-atoms to a WoN-node.
* [**InternationalChatBot**](teams/international-chat-bot.md): Allows you to connect to a chat partner anywhere in the world and translates the messages to the corresponding language of the receiver.
* [**TranslateBot**](teams/translatebot.md): Translates messages from one language to another to deliver the translation needed for InternationalChatBot
* [**BookPileBot**](teams/book-pile-bot.md): Reacts to book-related atoms, searches on the Buecherein Wien website for books and creates new atoms from the result(s)
* [**BookMatchBot**](teams/book-match-bot.md): Matches book-related atoms for renting/renting out or buying/selling books and hints the respective owners
* [**PollCreaterBot**](teams/poll-creator-bot.md): Creates a new strawpoll.me. All required information is collected via an interactive chat with the bot.
* [**PollVoteBot**](teams/poll-vote-bot.md): Allows the user to vote for a strawpoll.me poll. The user can choose the option to vote for via an interactive chat with the bot.
* [**MeetingBot**](teams/meeting-bot.md): Given multiple locations (the locations of the interaction partners) we find you a venue for a meeting near the halfway point between you. 
* [**LocationInformationBot**](teams/LocationInformation-Bot.md): Given a location of desire and the tag "locationinformation", the bot provides useful information about that location. Including, but not limited to: country name, region, capital, interesting locations.
* [**PollutionWarningBot**](teams/PollutionWarningBot.md): The PolutionWarningBot evaluates the air quality based on the air´s chemical components and determines whether the given results are critical or within a normal range.
* [**CoopBot**](teams/won-coopbot.md): Bot that creates new group chats, to find the best meeting place for all group members. Uses the MeetingBot to find the best place.
