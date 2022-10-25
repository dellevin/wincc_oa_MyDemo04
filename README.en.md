# WinCC OA Chinese

#### Description
WinCC OA Chinese Package
WinCC OA officially has three language packages, German, English and Russian, but does not support Chinese. We can use Gedi translation tool to make Chinese development enviroment.

#### Software Architecture

Software architecture description
data/trans/dictionary.json 
data/dplist/AES_Config.dpl 
data/dplist/sys.dpl 
msg/zh_CN.utf8/LogViewer.qm 
msg/zh_CN.utf8/qt.qm 
msg/zh_CN.utf8/uim.qm

AES_Config.dpl and sys.dpl are the localization of the system management interface opened in the GEDI environment. Some internal DP points are used, and Chinese are displayed in multiple languages. 

LogViewer.qm, qt.qm, uim.qm are LogViewer, GEDI, prompt window The Chineseization of multiple languages in the software, etc. 

dictionary.json -- dictionary file
#### Installation

step 1. Create a new standard empty project. At least select "English-US(en_US.utf8), Simplfd.Chinese - China(zh_CN.utf8)" two language options. Project Name can be defined by yourself, such as "CN318"; start the project.

step 2. Unzip the content to the project path

step 3. Run the menu bar translation tool: GEDI>Tools>Translator, select Import, and configure as shown below:

![输入图片说明](https://www.winccoa.top/chinese/WinCC%20OA%20Chinese_files/image001.jpg)

select English-US(en_US.utf8),language to import: Select Simplfd Chinese - China(zh_CN.utf8),

![输入图片说明](https://www.winccoa.top/chinese/WinCC%20OA%20Chinese_files/image002.jpg)

Check the All radio option under Version Files.

At this point, it should be available in File: to see the dictionary file of "dictionary.json".

step 4. Click the Start button. Wait for a few minutes to automatically complete the localization of all panels.

step 5. Localization of alarm/event window form

Before doing this step, you must open it once: System Management > settings > A&E - Row/Screen > Edit Row, the system will automatically create two DPs under the _AESConfi DP type, _AESConfig and _AESConfigRow in the background, and then execute the following Chinese

Gedi>System Management>Database>ASCII Manager

Direction select Import

Import the AES_Config.dpl and sys.dpl files, import them into the system, and complete the localization of the system management interface.

#### Instructions
Verify : Create a new User Interface in the Console (option: -m gidi -lang zh_CN.utf8)

Purpose: Use the translated project "CN318" as a library. We only use the translated files in panels, msg, and dplist. Log out the project from the Console and delete other unnecessary files contents of the folder.

In the config file of your own WinCC OA project, next to pvss_path, create a new line and add the library file path 
[general]
proj_path = "C:\WinCC_OA_Proj\CN318" 


#### Contribution

1.  zhigang.li@live.cn

