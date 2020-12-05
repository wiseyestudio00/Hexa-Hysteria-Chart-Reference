# VN

## Show Character
```
$ show Esti.1@Body.1@Normal.2@Action
```
This shows 2.png in Action Folder over 1.png in Normal folder over 1.png in Body.folder

Should the initial label just be the name of the file?

Better question: why do we need label?
- To enable Jump command
That makes sense

Then what is the point of making the initial label in the file itself, but not the name of the file?
- No reason, really.

Jump: Jump to the label while maintaining the Original Stack
Go: Go to the specified label but clearing all the original stack

$ show Esti.1@Body.1@Angry.1@Action

labels do not automatically connect to each other...

@ label1
Esti:this is label one
@ label2 // should we just add a Jump label1 command here?

^this enables choice
@ label1
$ choice where should I go?
  choice1:
    (internally this will be label1.choice1)
    This is line 1
    This is line 2
    $ label2
    (this will become label2)

  Choice2:
    this is line 1
    this is line 2
