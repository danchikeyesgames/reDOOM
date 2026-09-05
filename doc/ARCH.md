### Game arch

#### Start gameloop

`d_main.c` : **D_DoomMain**

#### Global Vars

`d_main.c`: wadfiles[20] - collect of wads; adds function - **D_AddFile**

`doomstat.c`: gamemode - license of game {public, registered, shareware, commercial, retail} (different version of game)

devparm - devmode

### Subsystems

`v_video.c` - video subsystem
`m_misc.c`  - misc subsystem (prefix *m_*)
`z_zone.c`  - zone memory allocatation subsystem
`w_wad.c`   - wad subsystem
`r_main.c`  - refresh {render} subsystem (prefix *r_*)
`p_setup.c` - playloop subsystem (prefix *p_*)
`i_system.c`- system subsystem (prefix *i_*)
`s_sound.c` - sound subsystem
`hu_stuff.c`- heads up display subsystem
`st_stuff.c`- status bar subsystem
`g_game.c`  - game subsystem
