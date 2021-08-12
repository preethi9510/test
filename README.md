# test

I - Pre-requisites for setting up a programing environment

1) A laptop with Mac OS High Sierra or higher:
	- Install Appium (http://appium.io/)
	- Install Anaconda Python 2.7 (https://www.anaconda.com/distribution/)
	- Install Android Studio (https://developer.android.com/studio)
	- Install Appium Python Client (https://github.com/appium/python-client)
	- Install Selenium (https://selenium-python.readthedocs.io/installation.html)
	- Install Chrome Driver (https://sites.google.com/a/chromium.org/chromedriver/downloads)
	- Install Iterm2 terminal (https://iterm2.com/)
	- Install Homebrew (https://brew.sh/)
	- Install Microsoft Office (https://www.office.com)
	- Install Text Editor (e.g., vim, emacs, vscode, sublime, notepad, etc.)
	- Install Chrome web browser (https://www.google.com/chrome/)
	- Install Latex (http://www.tug.org/mactex/)
	- Install FileZilla (https://filezilla-project.org/)
	- Install Eclipse IDE (https://projects.eclipse.org/releases/kepler)
	- Install ipdb (https://pypi.org/project/ipdb/)
	- Install sshpass (https://gist.github.com/arunoda/7790979)
	- Install pyautogui (https://pyautogui.readthedocs.io/en/latest/)
	- Install Cisco Anyconnect client (https://www.wichita.edu/services/its/userservices/documents/Remote_Desktop_Instructions.pdf)
	- Install Screaming Frog (https://www.screamingfrog.co.uk/seo-spider/)
	- Install lxml (https://lxml.de/parsing.html)

2) A server with Ubuntu 16.04:
	- Install Anaconda Python 2.7 (https://www.anaconda.com/distribution/)
	- Install Apktool (https://ibotpeaches.github.io/Apktool/install/)
	- Install tesseract (https://github.com/tesseract-ocr/tesseract/wiki)
	- Install graphviz (https://www.howtoinstall.co/en/ubuntu/xenial/graphviz)
	- Install openssh server (https://help.ubuntu.com/lts/serverguide/openssh-server.html)
	- Install html2text (http://manpages.ubuntu.com/manpages/trusty/man1/html2text.1.html)
	- Install Text Editor (e.g., vim, emacs, vscode, sublime, notepad, etc.)
	- Install ipdb (https://pypi.org/project/ipdb/)
	- Install Apache webserver (https://httpd.apache.org/)
	- Install httrack (https://www.httrack.com/)

3) A mobile phone with Android OS 6.0:
	- Make sure to turn on Developer Mode
	- Have a Google Play Store account with gmail and password

Notes
	- Make sure Bash version is at least 4.0
	- Make sure the following GNU commands are available from the Bash command prompt: 
	   find, grep, awk, sed, dos2unix, dot, curl, wget, adb, aapt, scp, apktool, split, sshpass, tesseract, html2text, uiautomatorviewer…
	- Any text editor is sufficient to develop in Bash and Python
	- Eclipse IDE (Keepler) is preferred if developing in Java with Soot framework
	- gcc and GNU build system are preferred if developing in C
	- Software version control (e.g., git, svn) is highly recommended for serious programmers
	- Openssh is recommended if working in a team of at least 2 people
	- Database management system can be used but not required
	- Graphical softwares (e.g., Adobe products) can be used but not required
	- Latex is recommended for serious programers
	- FileZilla can be used but not required
	- Server secondary-storage should be large if running with thousands of apks
	- Apache webserver can be replaced with a more light-weight webserver
	- alias server='python -m SimpleHTTPServer' is a very useful snippet for launching a builtin python webserver
	- Cisco Anyconnect client can be used for remote access from home to school if necessary
	- Screaming Frog and httrack can be used but not required
	- lxml can be used but not required



II – Project structure
	
	The project consists of the following packages:

	lai

		contains all the tools for automated testing android apps via appium
	lai_web
		contains all the tools for automated testing websites via selenium
	analyzer
		contains all the tools related to account deletion functionality for android apps
	analyzer_web
		contains all the tools related to account deletion functionality for the web
	analyzer_combiner
		contains all the tools which combine results from the two packages analyzer and analyzer_web
	pystatparser
		contains a parser for natural language processing
	nlp
		contains all the tools which use pystatparser for analyzing the semantics in natural language processing
	duc
		contains all the tools to be used with Soot framework
	calc
		contains all the templates to be used for data calculation
	latex
		contains all the templates to be used for latex (please ask professor Shan)
	clang
		contains all the tools implemented in C language

III – Notations
	
	./		run an executable bash script
	<  >		some user input
	[ X | Y ]		choose either X or Y
	Z		software tool Z is developed or customized in-house
	___		optional
	
	
IV - Software tools and usages	

			#apkdl.sh:
	
|**Synopsis**	|**./apkdl.sh**							|
|:--------------|:-------------- 						|
|**Description**| scrape all the android package names from a website		|
|		|								|
|**Options**	|the input website is already hardcoded as apk-dl.com		|
|		| the script will return a list of android package names	
|		|	
|		|
|		|
|**Dependencies**|curl								|
|		|awk	
|		|	
|**Packages**	|lai_web							|
|		|						
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129245423-43c2be09-904b-4230-9fd5-1558a27a0ba6.png)
								



			apk2web.sh:
	
|**Synopsis**	|**./apk2web.sh**							
|:--------------|:-------------- 						
|**Description**| find the equivalent website address for an apk file by looking into the manifest	
|		|	
|**Options**	||<apkfile>
|               |	an apk file
|               |	given an apk file, the script will return the equivalent website address
|**Dependencies**|aapt					
|		|dos2unix
|		|grep
|		|
|**Packages**   |lai_web								
|		|	
|		|	
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129247712-19fa98e7-659f-4151-9fb1-23c1f84bf347.png)
							


	
	
	
|**Synopsis**	|**./apk2url.sh <packagelist> auto**							
|:--------------|:-------------- 						
|**Description**| find the equivalent website address for for a list of android package names via google	
|		|	
|**Options**	|<packagelist>
|		|		a text file containing android package names
|		|the auto flag is optional:
|               |		if present, the script will automatically pick the first website address from google candidate search results		
|               |		if not present, the script will let testers pick a website manually from the google candidate search results		
|**Dependencies**|url.py					
|		|
|		|
|		|
|**Packages**   |lai_web								
|		|	
|		|	
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129269450-1bae1183-f101-4d18-b716-e80b1ea36bd6.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129270158-b7cd68c3-1a1f-46dc-8a5f-48b6cee3e966.png)|






|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	

|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	

|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
	

|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	

|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
	
|**Synopsis**	|****								
|:--------------|:-------------- 						
|**Description**| 								
|		|								
|**Options**	|		
|		| 	
|		|	
|		|
|		|
|**Dependencies**|								
|		|	
|		|	
|**Packages**	|										
|		|						
|**Examples**	|
	
	
	
	
