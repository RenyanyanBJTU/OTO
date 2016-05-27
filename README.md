# OTO
openthos based on android-x86 

## Establishing a Build Environment
First, follow the AOSP page "[Establishing a Build Environment](http://source.android.com/source/initializing.html)" to configure your build environment.
<br><br>
<b>
Notice: Before you establishing a build environment, you'd better make your Linux version to be Ubuntu 14.04 LTS, because the version of openjdk must be 7, there may be something wrong when you build the source code of openthos with openjdk-8-jdk.
</b>
## Downloading the Source
```
git clone https://github.com/openthos/OTO.git
#info: clone repo to your local computer, make sure you installed git before this command, 
#if not,try ' sudo apt-get install git ' to install git, 
#and use git config --global user.name(or email) "your name(or email)" to config your information

cd OTO
export PATH=$PATH:$PWD

mkdir WORK_DIR
cd WORK_DIR
repo init -u https://github.com/openthos/OTO.git -b $branch
#eg: repo init -u https://github.com/openthos/OTO.git -b multiwindow
repo sync
```
Where $branch is any branch name described in the list below.
<p>
We have created different branches based on lollipop-x86 (required openjdk7):
 - lollipop-x86
 - multiwindow
 - singlewindow

## Building openthos
```
cd WORK_DIR
source build/envsetup.sh
lunch $target_build
#eg: lunch android_x86_64-eng
make iso_img -j$P
#out directory: out/target/product/ and $P depend on the performance of your computer
```
