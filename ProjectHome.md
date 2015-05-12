Django-jqchat is a chat client for Django.

PLEASE NOTE THAT I AM NO LONGER MAINTAINING THIS PROJECT - I HAVE TRANSFERRED IT TO GITHUB (https://github.com/richardbarran/django-jqchat) AND A NEW MAINTAINER IS TAKING OVER.

[Try out the demo](http://arbee-design.co.uk/jqchat/room/1/).

![http://arbee-design.co.uk/media/photologue/photos/cache/jqchat_screenshot_google_code_shot.png](http://arbee-design.co.uk/media/photologue/photos/cache/jqchat_screenshot_google_code_shot.png)

# Features #
  * Uses the [jQuery](http://jquery.com/) library (so for example fits in nicely with a [Pinax](http://pinaxproject.com/) project).
  * Extensible (see below).

# Extensible: what do you mean? #
I had a specific requirement to add a chat client to a page, where the chat window
was not the only data that was to be updated by Ajax calls.

The solution was to write a basic chat client that allows extra data to be
piggybacked on the Ajax payloads; for an example, [see this demo where a description field can be updated by the user](http://arbee-design.co.uk/jqchat/room_with_description/1/).

# Sites that use this application #
  * [demo site](http://arbee-design.co.uk/jqchat/room/1/).
  * soon to be included in [FriendcodeConnect.com](http://www.friendcodeconnect.com/) - 'lobbies' will include this chat client.

# To Do #
This chat client is still very basic; during summer 2009 I will be making changes
to improve performance, this so far has not been a design objective.