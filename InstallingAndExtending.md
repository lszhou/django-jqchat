# Dependencies #
  * [django-timezones](http://code.google.com/p/django-timezones/)
  * [pytz](http://pypi.python.org/pypi/pytz/) (used by django-timezones).

# Installation #

For now these instructions are very basic - please do not hesitate to point out errors, omissions, black holes, etc... and I will add your corrections.

I will assume that you already have a Django project setup with jQuery. If not,
do it now!
After that, installation is fairy standard:
  * checkout django-jqchat.
  * add jqchat to the project's list of applications.
  * add jqchat's urls.py to your main urls.py file.
  * run a syncdb to add new tables.
  * test it. By default the urls.py file supplied adds 2 types of chat test rooms, you will have to manually create one in the admin before you can test it.

# Design philosophy #
Jqchat is built on the assumption that a chat room is an extra feature on top of an existing object.
Hence jqchat is kept very basic and extensible.

## Integration ##
The easiest way to add a jqchat room to an existing model is to create a OneToOne field
on the existing model.
For example:
```
	    chat_room = models.OneToOneField(room, help_text='Chat room to be used for this lobby.')
```
In the jqchat templates folder you will find chat\_test.html; you will have to pull out
some code and add it to your own templates:
  * the header code which initialises the javascript code.
  * the chatwindow div and the chatform form. If you decide to rename these elements, you
> will have to adjust the javascript code accordingly.

This should be enough to use the supplied chat client; to extend it, please see below.

## There's no chat room members list? ##
No, not at present; as stated above, I see jqchat as an extension to an existing object.
Of course, if someone sends in a patch with a neat and generic way of adding this to jqchat, I'll update it!

# Extending jqchat #
The big feature of jqchat is that it can be extended; by this, I mean that you can
piggyback extra information in the Ajax payloads.
Within the source is an example of using this to add and change descriptions for the
chat rooms.
Things to look at are:
  * template chat\_test\_with\_desc.html: note how the call to the javascript includes a different url for handling the AJAX calls.
  * views.py: the normal handler for the Ajax calls has been overridden. The view WindowWithDescriptionAjaxHandler is an instance of the view class DescriptionAjax.
> This class has its own custom handler - 'ExtraHandling' - that knows what to do with custom actions from the client, and also knows what extra fields to pass back.