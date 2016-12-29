In the first commit a Byond DMI file that has had its extention changed from `.dmi` to `.png` is added to the project. If you inspect the PNG with TweakPNG or a simmar program, you'll see the DMI metadata in the `ztxt` block:

```
# BEGIN DMI
version = 4.0
	width = 32
	height = 32
state = ""
	dirs = 1
	frames = 1
state = "floor"
	dirs = 1
	frames = 1
state = "white"
	dirs = 1
	frames = 1
state = "plating"
	dirs = 1
	frames = 1
{...}
```

The PNG was then edited with Windows 10 paint (which perserves the `ztxt` block) and committed. Github's interactive image diff feature works correctly.

Then only the `ztxt` block was edited (truncated to only the version info and first state entry) and commited. Github's interactive image diff feature correctly shows no visual changes, and also dosen't seem to get confused.

So it looks like the github software can treat `.dmi` as an alias of `.png` for purpouses of selecting the interactive image diff tool, and it wont break github or corrupt the ztxt block or do anything weird. Awesome!
