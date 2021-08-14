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
|**Options**	|\<apkfile\>
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
							

			apk2url.sh:
	
	
	
|**Synopsis**	|**./apk2url.sh <packagelist> auto**							
|:--------------|:-------------- 						
|**Description**| find the equivalent website address for for a list of android package names via google	
|		|	
|**Options**	|\<packagelist\>
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



						auto.sh:


|**Synopsis**	|./auto.sh \[\<apklist-directory\>\<server-username\> \<server-password\> \<wait\-time\-in\-secs\> collect  \| \<apkdir\> apk2web \]
|:--------------|-------------- 						
|**Description**| an automatic script to collect apks and websites without any manual intervention
|		|	    	 
|               | 	     
|		|						
|		|								
|**Options**	|collect 
|          	|	automatically go to google play store, download apks, and upload them to a dedicated server
|          	|	\<apklist\-directory\> 
|               |        	a directory which contains files whose contents are android package names
|          	|	\<server\-username\> 
|               |        	ssh username
|          	|	\<server\-password\> 
|               |        	ssh password
|          	|	\<wait\-time\-in\-secs\>
|               |        	time to wait between each batch of apk files finish uploading to the server
|		|apk2web
|          	|	automatically find equivalent websites from a directory containing all apk files pulled from the mobile phone 
|		|\<apkdir\>	
|		|	a directory which contains all apk files pulled from the android mobile phone
|		|
**Dependencies**|lac_batch.sh 
|		|upload.sh
|		|apk2web.sh
|		|						
|**Packages**	|lai_web										
|		|
|** Notes**	|Appium is required to run the script
|		|
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129371484-132d33b4-8e09-4295-9e8f-1b9f09d8271a.png)	
	
						batch.sh:
	
	
|**Synopsis**	|**./batch.sh \<apk\-directory\> [ install \| uninstall \| remove \| signup \| login \| delete \| manual ]**			
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
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129371636-c6f40773-5d93-4bf8-8361-adc093df83ff.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129371735-03612142-8ca7-4097-b8aa-3a81bde55fd4.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129371810-1d785c9b-8a87-4776-ba2f-7eba097da5e1.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129371883-6114ed53-bd8d-42ab-bba2-1d1cd00ea7b4.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129371941-7766664d-5a7f-4191-8989-30838288f396.png)|

|		|
|		|
						single.sh:
	
	
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
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129373542-31a7ba77-a5f4-410f-893f-20645962c8cc.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129373599-e7a0cbbe-e82f-45e6-b35d-9f618ef2af7f.png)|
|		|
|		|
		
						pm.sh:
	
	
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
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129373659-46741c18-90c8-4e2e-83b5-3d6ff4998080.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129373708-60936214-984d-402f-a30c-969ebbd8f4d0.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129373744-344dd800-47b5-46d0-8983-f72a5a5429ab.png)|
|		|

						minus_operation.sh:

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
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129373821-88269777-4dc1-4e97-bcc6-2ef238206a5c.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129373872-88a85d42-68cc-4ff7-aa4c-d4a134404e0e.png)|
|		|

						lac_batch.sh:
	
	
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
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129373955-ec9522da-bedc-4c5b-9248-0b4dd2b23bc2.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129373975-e1779d5d-0541-40ac-b595-7c475cd18ed6.png)|

	
						upload.sh:
	
	
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
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129374017-16a9a92e-74f3-4194-b0d7-58adf03f6dc9.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129374065-b0163239-650f-4d95-aee5-68659f3a2ad0.png)|
|		|
	
	
						lac_adf.sh:
	
	
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
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129374128-fd49791c-c692-4a53-8627-e3eddfd5a1f9.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129374187-e6d76152-9ea3-448a-9034-ce1b86aeed2d.png)|
|		|

						stats2.sh:
	
	
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
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129374263-aa111dc9-939f-4520-8d1f-b85270045946.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129374326-7375d4d9-230f-446f-8f9a-5d80b420c14e.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129374368-49df4f53-584d-49ad-a3be-3526e38e56db.png)|
|		|
		
	
						stats2_web.sh:
	
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
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129374950-1889937e-1b98-4f7d-bd40-a12c673c77fb.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129375030-23aa567d-1997-424a-bf4d-7cf59b345a7e.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129375094-7b98d440-0650-41d1-a34f-fa7b595b84d2.png)|
|		|
				
						adf.sh:
	
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
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129375266-9457d6ab-447e-4e4d-9de8-76d5cbe8d905.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129375329-57bbe8c5-df8b-490e-ad84-e304a59e7c35.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129375427-4d299895-5a6e-408c-aa16-37b64aeaed12.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129375517-8fdbc9e8-e06a-4854-a828-5a60caecee86.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129375570-2963318d-740b-40ba-967a-4757c72d7287.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129375652-992d187b-52e5-41ae-8fb1-213eb80d59f0.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129375730-0a4af2e0-e4eb-46fb-8a25-0aa05a48b817.png)|
|		|

	
	
	
	
	
						parallel.sh:
	
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
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129377413-5fa96bd3-2e3b-4634-8efd-4f49270cc49c.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129377520-5aa59dc3-ed5e-4482-b32d-320792606d69.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129377574-2ddeee9e-c9ed-4ff2-bda9-6ca205de2b57.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129377910-5c4c8c5e-a654-470b-bc9d-0c1d63c1a9fd.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129377955-00344443-433b-4942-ac3a-1da6efb3a275.png)|
|		|
		
		
	
	
	
	
						adf_fp.sh:

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
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129378045-40b6d4da-018f-46c1-91ef-6f2975421c30.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129378111-b969d7ab-eaeb-4a9a-b6bf-5bbd7a32bddc.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129378200-28215678-fe00-4a54-acab-0fe6cebc9efb.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129378248-9d247f60-4f32-43c9-8726-ace1d1e7a270.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129378418-b78717bd-ce5d-4507-9767-b8607572c4da.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129378624-dfbf1e39-303d-436a-94da-66a1ad003b9e.png)|
|		|
	
	
						parallel_fp.sh:
	
	
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
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129378975-c842b5c2-9a2e-446f-894f-41afef80a315.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129379282-97e8d696-53b2-432d-8747-9adcad9a6f0f.png)|
|		|
	
						stats.sh:
	
	
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
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129380546-df785a8c-f7c9-4e07-bda8-8157b8b7b124.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129380662-0a0ddf7c-709f-40ae-834a-33f1bf374708.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129380701-58619dd1-2431-4bca-b639-9ab085c712dc.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129380752-d2d933d3-d938-4698-b09e-a5ac0102a86d.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129380806-6c8b4f00-69cf-4643-966d-5645f6619e1f.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129380850-6b3906cb-82ef-477e-831e-01ce8bd056a2.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129380910-4d44cca0-03ae-4a45-855e-8b4faf8f3ce3.png)|
|		|
	
	
	
	
	
						concat.sh:
	
	
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
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129381042-de305981-fd64-40f5-b0f5-ffe1a9bf7b93.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129381137-0c7dcc29-eb0a-485e-97b2-8494be950eb0.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129381178-68318b4c-f996-4225-b1da-aed106a26641.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129381211-8e7f736e-d566-4c89-9284-62888d84ded1.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129381245-8992edb6-b644-42b0-88d5-d59f997bc77c.png)|
|		|

	
						
	
	
						semantics.py:

	
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
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129381408-c0ac30a8-5a17-4609-9c72-10aadb8cd599.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129381444-f625d032-e98f-42ca-bc98-60d99cc392e4.png)|

	
	
						context.py:
	
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
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129381501-53f68cd9-813d-4684-8f8f-b69c8c42d95b.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129381544-73aef7d9-29c8-4d07-a7e3-e80546b538a9.png)|

	
	
				apktool to extract retention period from apps:
	
	
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
	
	
	
				Web tool to extract retention period from websites:
	
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
	
	
	
	
				url.py:
	
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
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129381601-08ec15b1-75bc-4aef-a9db-7ce9ede1ce8b.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129381665-6feb2fb0-63f7-4ca2-bc5c-33bf8a6a3558.png)|

	
	
	
	
				store.py:
	
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
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129381743-f50a5714-55c0-48af-b096-8936243ceb83.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129381783-aa093d3d-c245-45df-8cb9-429fa6f1d4bd.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129381820-389e7b5b-ae6f-4a46-a32e-9c13c71e4345.png)|

	
	
				my_apps.py:
	
	
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
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129381879-4ca4f3f8-f446-4935-bdae-042d9920e356.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129381925-495a508e-8fef-4458-93d8-9bff2a1eb276.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129381964-92176cb5-392c-4f2d-bc84-2783c2e2db6f.png)|

	
	
	
				manual.py:
	
	
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
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129382101-131e5dfe-18c9-4550-bdb8-6fc1223c7e4a.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129382135-3ef4bd0b-5563-4ada-933f-afb9a34e6f86.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129382169-5449a08f-b4f9-4365-bf3b-0a59a7507d04.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129382207-408c979e-2cef-42db-a928-740ca06d8163.png)|

	
	
	
				signup.py:
	
	
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
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129382236-a18a1516-b6dc-4063-8308-e068adcbc693.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129382277-1fe0660e-6fe7-45f0-9b16-b36c28866ae3.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129382316-36408fea-4f34-4128-89ed-bbdbcc0789d5.png)|


	
	
				login.py:
	
	
	
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
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129382396-6e65efc8-8c4d-4e5d-83b9-25dca527309d.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129382440-ea582a01-69d4-4eb1-b0a8-b7c5aa04f4a5.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129382484-033fa7c2-06c6-42d0-af4f-0d55b3295765.png)|

	
	
	
	
				delete.py:
	
	
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
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129382542-41bf787d-46f4-4476-9505-04ed0c029420.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129382579-3013b12d-d2ae-4fa5-a346-c73f30bb088a.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129382630-e77b924e-a8d5-41ef-a186-a7e51ae6bf81.png)|

	
	
	
				cleanup.py:
	
	
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
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129382773-a6ce567c-233f-4684-8cf1-7932b73d8436.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129382825-8979ea11-7161-47b2-861d-6401046142e2.png)|

	
	
	
				commons.py:
	
	
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
	
	
				commons_web.py:
	
	
	
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
	
	
				random_scraper.py:
	
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
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129382951-dc50da23-145a-4ae9-b254-8b9be2f74bcd.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129382988-ba8f55ce-4a14-439f-8e53-be175891f4d0.png)|

	
	
	
	
				capture.py:
	
	
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
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129383034-71a953b6-72d4-4ded-ab6e-5d928475d668.png)|

	
	
	
				DefUseChain.java:
	
	
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
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129383075-ff10838f-5662-4f0f-a7ed-d239e889e30b.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129383118-b5439d03-82d4-47f5-b341-503538ec32a5.png)|

	
	
	
				pystatparser:
	
	
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
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129383340-9b05828d-979c-4e33-945b-813e67ed939e.png)|

	
	
	
	
				auth:
	
	
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
|**Examples**	|![image](https://user-images.githubusercontent.com/84356922/129383387-6cc7b996-3cc8-4795-a97f-def17d55778f.png)|
|		|![image](https://user-images.githubusercontent.com/84356922/129383418-792976f5-89bd-4c86-bb14-7443bb5c2556.png)|
|
	
	
	
	
	
	
	
