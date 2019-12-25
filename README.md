# v1.0 README - Allebone
# Begin Adding Structure to the Documents for HELP.OMNI.AF.MIL

## Developers / Technical Writers Install Instructions (One Time Setup):

	1. Press COMMAND + Spacebar
	2. Type: Terminal and press ENTER
	3. Run: /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
	4. Run: brew install python python 2 pip
	5. Run: pip install mkdocs
	6. Run: pip install mkdocs-material
	7. Install Git Desktop from Link: https://central.github.com/deployments/desktop/desktop/latest/darwin
	8. Install Preferred Editor (Like Sublime Text)
	9. Clone Respository - "git clone https://github.com/allebone/help.omni.af.mil.git"
	10. Edit in Editor
	
## Developers / Technical Writers Daily Working Environment: 	
	1. Github Desktop Client: PUSH "Pull from Origin" Button (Top Right)
	2. Run from Terminal: cd ~/Documents/github/help.omni.af.mil/
	3. Run from Terminal: mkdocs build
	4. Run from Terminal: mkdocs serve
	5. Open Safari to URL: http://127.0.0.1:8000
	6. Make Changes to Documents, observe changes in Safari-Realtime, or press refresh
	7. When changes are complete:
		a. Github Client: Commit (Please Comment for Clarity/Explanation)
		b. Github Client: Push to Origin (this merges your changes to the master)