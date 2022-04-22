st - simple terminal
--------------------
st is a simple terminal emulator for X which sucks less.


Requirements
------------
In order to build st you need the Xlib header files.


Installation
------------
Edit config.mk to match your local setup (st is installed into
the /usr/local namespace by default).

Afterwards enter the following command to build and install st (if
necessary as root):

    make clean install


Running st
----------
If you did not install st with make clean install, you must compile
the st terminfo entry with the following command:

    tic -sx st.info

See the man page for additional details.

Credits
-------
Based on Aurélien APTEL <aurelien dot aptel at gmail dot com> bt source code.


# 快捷键

/* Internal keyboard shortcuts. */
// Mod1Mask 为alt
#define MODKEY Mod1Mask
#define TERMMOD (Mod1Mask|ShiftMask)

// from @LukeSmithxyz
static char *openurlcmd[] = { "/bin/bash", "-c",
    "sed 's/.*│//g' | tr -d '\n' | grep -aEo '(((http|https)://|www\\.)[a-zA-Z0-9.]*[:]?[a-zA-Z0-9./&%?#=_-]*)|((magnet:\\?xt=urn:btih:)[a-zA-Z0-9]*)'| uniq | sed 's/^www./http:\\/\\/www\\./g' | dmenu -i -p 'Follow which url?' -l 10 | xargs -r xdg-open",
    "externalpipe", NULL };
static char *copyurlcmd[] = { "/bin/bash", "-c",
    "sed 's/.*│//g' | tr -d '\n' | grep -aEo '(((http|https)://|www\\.)[a-zA-Z0-9.]*[:]?[a-zA-Z0-9./&%?#=_-]*)|((magnet:\\?xt=urn:btih:)[a-zA-Z0-9]*)' | uniq | sed 's/^www./http:\\/\\/www\\./g' | dmenu -i -p 'Copy which url?' -l 10 | tr -d '\n' | xclip -selection clipboard",
    "externalpipe", NULL };
static char *copyoutput[] = { "/bin/bash", "-c", "st-copyout", "externalpipe", NULL };

static Shortcut shortcuts[] = {
	/* mask                 keysym          function        argument */
	{ Mod1Mask,             XK_l,           externalpipe,   {.v = openurlcmd } },/* alt+l打开url*/
	{ Mod1Mask,             XK_y,           externalpipe,   {.v = copyurlcmd } },/* alt+y复制url*/
	{ Mod1Mask,             XK_o,           externalpipe,   {.v = copyoutput } },
	{ XK_ANY_MOD,           XK_Break,       sendbreak,      {.i =  0} },
	{ ControlMask,          XK_Print,       toggleprinter,  {.i =  0} },
	{ ShiftMask,            XK_Print,       printscreen,    {.i =  0} },
	{ XK_ANY_MOD,           XK_Print,       printsel,       {.i =  0} },
    { TERMMOD,              XK_Prior,       zoom,           {.f = +1} },  /*alt+shift+pageup增大字体*/
	{ TERMMOD,              XK_Next,        zoom,           {.f = -1} },
	{ ControlMask,          XK_equal,       zoom,           {.f = +1} },  /*alt+ =增大字体*/
	{ ControlMask,          XK_minus,       zoom,           {.f = -1} },
	{ TERMMOD,              XK_Home,        zoomreset,      {.f =  0} },
	{ ControlMask,          XK_Home,        zoomreset,      {.f =  0} },  //
	{ TERMMOD,              XK_C,           clipcopy,       {.i =  0} },     /*alt+shift+c复制*/
	{ TERMMOD,              XK_V,           clippaste,      {.i =  0} },     /*alt+shift+v粘贴*/
	{ Mod1Mask,             XK_c,           clipcopy,       {.i =  0} },     /* alt + c复制*/
	{ Mod1Mask,             XK_p,           clippaste,      {.i =  0} },     /* alt + v粘贴*/
	{ TERMMOD,              XK_Y,           selpaste,       {.i =  0} },
	{ ShiftMask,            XK_Insert,      selpaste,       {.i =  0} },
	{ TERMMOD,              XK_Num_Lock,    numlock,        {.i =  0} },
	{ ShiftMask,            XK_Page_Up,     kscrollup,      {.i = 20} },  /*shift+pageup上翻20行*/
	{ ShiftMask,            XK_Page_Down,   kscrolldown,    {.i = 20} },
};
