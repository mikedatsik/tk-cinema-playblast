Cinema Playblast app for Shotgun Toolkit
======================================

This tool is meant to do the playblast, save the file in the directory and submit it to shotgun. We create a simple UI for it, and an interface to be used by other apps.

To enable the apps, additional lines added to environment config shot_step.yml under cinema engine

    tk-cinema-playblast:
      hook_post_playblast: default
      hook_setup_window: default
      location: {name: tk-cinema-playblast, type: manual, version: v0.1.0}
      template_work: cinema_shot_work
      template_shot: cinema_shot_playblast
      template_sequence: cinema_sequence_playblast

# Optional Configuration Fields

	  scale_options: [25, 100]

Configure a custom set of playblast resolution percentage, to be selected by user via UI. *Default: [50, 100]*

	  temp_directory: "C:/Temp"

Configure a local path for playblast file creation before being copied into project folder. Path must be absolute.

	  camera_name_pattern: ".*ShotCam_.*"

Set a regular expression to filter camera names. First camera with matching name will be used for playblast. *Default: "persp"*

# Added to Favourites menu
    menu_favourites:
    - {app_instance: tk-multi-workfiles, name: Shotgun File Manager...}
    - {app_instance: tk-multi-snapshot, name: Snapshot...}
    - {app_instance: tk-multi-workfiles, name: Shotgun Save As...}
    - {app_instance: tk-multi-publish, name: Publish...}
    - {app_instance: tk-cinema-playblast, name: Cinema Playblast...}
