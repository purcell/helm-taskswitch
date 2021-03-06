# helm-taskswitch
Helm source for switching between X windows

You know how some times looking for the program or browser tab is like
rummaging through a drawer of unmatched socks? This is a solution to
that problem.

## How I use this

### Hot key to activate helm-taskswitch
I map the win-a key to be globally handled by the window manager to
run ``` emacsclient -n -e '(helm-taskswitch)' ```

### Force all browser tabs to a window instead
A lot of tasks are done in browser tabs. But they are not accessable
to task switchers. I definitly need to switch between browser tabs to
get my work done.

To get chrome browser tabs exposed to the helm-taskswitcher, I use a
extension called 'New Tab, New Window' so each tab is in its own
window. To further assist with searching for tabs I use an extension
'URL in title'.

These would allow access to tabs from any task switcher but most
mainstream ones would be useless with dozens of browser windows. Using
matching from helm alows helm-taskswitcher to quickly find them.

### Example 
With this setup, when I hit win-a, Emacs comes up and I get the task
switcher, from there I type in the first thing that comes to mind
related to the tool I want, the title, the URL or host, .js to get all
my JavaScript buffers. Helm handles all the auto-complete and
filtering. Hitting return brings the window/tab/buffer to the
foreground.

Lets say I want a chrome window with the an AWS ElasticSearch console.

I hit win-a, type 'go' (that filers to all google chrome windows)
SPACE 'ela' (all google chrome with 'ela' in title) SPACE 'con' (all
chrome with 'ela' and 'con' in title). Then I usually just hit return
without looking since I'm confident it will be right.

This works great for me. I still use alt-tab for most recently used
program. And if I have my hand on the mouse I use it for task
switching. 

## Why?

When working on a computer I'm working on tasks. Usually each task is
serviced by a program that is running, a tab in a browser or a buffer
in Emacs.

When I switch between one task and another it goes something like
this: 

1) Something triggers a mental need to switch to another task in
my mind 

2) I think of which program/tab/buffer is servicing this task. I
personally, the first thing I think of about the program/tab/buffer is
some sort of word such as 'inbox' 'terminal to server-dev-23'
'ItemAction.js'. 

3) I do something with the computer to bring the program I
need to do that task to a state where I can use it.

Mainstream UIs for switching between tasks almost always use a visual
UI to offer the options of which running programs can be switched
between. This does not work with my step 2 since I'm thinking of
something like "google chrome with AWS lambda console". I don't think
of how it looks, I don't think of how many times back in a stack that
might be. 

I find these deficient because I usually have a large number of
programs/tabs/buffers running, each servicing a task. They focus on a
visual search of open program windows. As the number of windows grows
these become illegible. 

Web browser tabs are a huge difficulty. If I have three browser
windows open each with a dozen tabs there is no way I'm going to find
the tab I want efficiently.  Mainstream UIs don't service tabs/buffers
so they don't cover all of the things I want to bring forward.

The setup I use with this package achieves: 

1) Symbolic searching of title, program etc for programs/tabs/buffers
that service tasks. I just hit win-a and type something. I touch type
so this works well for me. I'm never rummaging around.

2) Combines the program window search space, tab search space and
Emacs buffer search space. These are the most common types of tools
I'm looking for.

3) I never have to find which browser window has which tab. All the
tabs are exposed.


## TODO 
This doesn't keep track of how frequently windows are visited or the
most recently visited window. I'm working on that. I have the input
data by listening to xevents. 

## Requirements

Xwindows, wmctrl, emacs, helm. I run this on linux.
