![TimOS Logo](https://github.com/timleunghk/timos/blob/master/logo/TimOS.jpg)

# TimOS #



TimOS係我個人將Android OS客製化既系統，主要是來自AOSP和Pixel Expeience兩大網站修改而成

TimOS is my customized Android Mobile Phone OS project based on AOSP and Pixel Experience. 

最初期，我只改咗Launcher，拎走咗Google Search Bar同埋icon一啲多餘白色部份。其餘部份都仲係喺Pixel Experience果邊fork過嚟。不過我慢慢會加多啲app或者component上去，做多啲自己野。

In initial phase, only launcher has been modified by removing Google search bar and removing unwanted icon area. Other components are forked from Pixel Experience. More and more components will be launched here gradually.

長遠來講，我想整一部屬於香港人手機，香港人講廣東話(應該要講"港語")，一部港語手機，除咗令多啲人明白手機運作之外，最重要係身份認同！我哋讀書由細到大，一直都唔可以將港語好似我而家咁樣寫作文章，要寫書面語，其實，即係要寫國語/普通話！一個民族點可以只有聲音無文字？台灣人講福建話都可以叫台語，我哋做乜野唔可以叫廣東話做港語？！所以，我可以做既就係做呢個OS，希望有更加多人支持港語手機！  Telegram已經有，Android更加要有！

順便講埋，唔駛中國人乜野紅蒙，我哋香港人夠有自己既OS咯！


In long term development, it will be a combination of Mobile Phone and PC. Just connecting HDMI cable to your TV or monitor, a new Window Like desktop will be displayed. Moreover, a full Cantonese wording will be added in TimOS. As a Hongkonger, Cantonese (or simply HongKongese) is our mother tongue that always be discrimated by people speaking Mandarin. Our own words cannot be written in public. To break this wall, I decide to do this in the near of the future. That's why I set up this repository for everyone download this source code, modify it and constribute your works.

Before that, please download this source and enjoy!

下面將會係下載和編譯方法，用英文寫。

## Compile by Yourself ##

### Important ###
Please make sure you have a PC satisfy the following requirements

1.Ubuntu 18.04 64-bit enviroment.

2.At least 8GB RAM.

3.At least 250GB Space.


Virtual Enviroment is no problem. However, the performannce is dramaically poor. So, I suggest all of you guys prepare a physical PC as your development environment

## Steps ##

Open Terminal to execute the following commands.

### Step 1 Download and Extract Android SDK ### 
```
wget https://dl.google.com/android/repository/platform-tools-latest-linux.zip
unzip platform-tools-latest-linux.zip -d ~
```
### Step 2 Setup Android SDK ###
Modify ~/.profile by adding the following statement.
```
if [ -d "$HOME/platform-tools" ] ; then
    PATH="$HOME/platform-tools:$PATH"
fi
```
### Step 3 Update List ### 
```
sudo apt-get update
sudo apt-get upgrade
```
### Step 4 Download necessary components ###
```
sudo apt-get install bc bison build-essential ccache curl flex g++-multilib gcc-multilib git gnupg gperf imagemagick lib32ncurses5-dev lib32readline-dev lib32z1-dev liblz4-tool libncurses5-dev libsdl1.2-dev libssl-dev libwxgtk3.0-dev libxml2 libxml2-utils lzop pngcrush rsync schedtool squashfs-tools xsltproc zip zlib1g-dev openjdk-8-jdk
```

### Step 5 Create Directories ###
```
mkdir -p ~/bin
mkdir -p ~/android/timos
```
### Step 6 Download repo ###
repo is repository which storing source codes of TimOS
````
curl https://storage.googleapis.com/git-repo-downloads/repo > ~/bin/repo
chmod a+x ~/bin/repo
````
### Step 7 Setup repo ###
Same as Step 2, modify ~/.profile by adding the following statement.
````
if [ -d "$HOME/bin" ] ; then
    PATH="$HOME/bin:$PATH"
fi
````

### Step 5 Download Source Codes from repository ###
```
cd ~/android/timos
repo init -u https://github.com/timleunghk/timos.git -b master
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
```

### Step 6 Establish Build Environment ###
````
source build/envsetup.sh
````

### Step 8 Download Necessary Files for Destinated Device (Recommended Device: Nexus 5X) ###
````
breakfast bullhead
````
### Step 9 Build your TimOS ###
````
brunch bullhead
````
Where 'bullhead' is codename of Nexus 5X. For other mobile phones, please refer the following link. 
(https://www.droidviews.com/list-of-android-device-codenames/)
However, I cannot ensure all mobile phones are able to be built.

### Step 10 Get your compiled TimOS ###
If there is no any fails, you will be able to find a zip file under 
````
~/android/timos/out/target/bullhead/PixelExperience_Plus_bullhead-10.0-ddmmyyyy-hhmm-UNOFFICIAL.zip
````
You can flash this zip file to your mobile phone.

## Result ##

### Before Change ###

![A](https://github.com/timleunghk/timos/blob/master/result/Before1.png)

![B](https://github.com/timleunghk/timos/blob/master/result/Before2.png)

### After Change ###

![C](https://github.com/timleunghk/timos/blob/master/result/After1.png)

![D](https://github.com/timleunghk/timos/blob/master/result/After2.png)
