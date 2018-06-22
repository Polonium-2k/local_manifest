# local_manifest
Getting Started
---------------

To get started with Android, you'll need to get
familiar with [Git and Repo](https://source.android.com/source/using-repo.html).

1.Set up your environment

    sudo apt-get install git-core
    git clone https://github.com/akhilnarang/scripts
    cd scripts
    ./setup/<script-name>

2.Run the script corresponding to your Linux Distribution . it should be in setup folder

eg : 

    ./setup/ubuntu1604linuxmint18.sh


3.Then run these commands to get git all working:

     git config --global user.email "you@example.com"
     git config --global user.name "Your Name"

4.Then Create a folder for lineageOS/CRDroiD and open it

    mkdir lineage
    cd lineage

5.To initialize your local repository using the LineageOS/cRDROID trees, use a command like this:

LOS

    repo init -u git://github.com/LineageOS/android.git -b lineage-15.1
     
OR crdroid
   
    repo init -u git://github.com/crdroidandroid/android.git -b 8.1


6.Now create a local_manifests dir and Copy the required manifests in that folder.

    mkdir .repo/local_manifests
    
    wget -O .repo/local_manifests/MSM8916.xml 'https://raw.githubusercontent.com/Polonium-2k/local_manifest/master/msm8916'    

7.Then to sync up:

    repo sync -c -f --force-sync

OR, for those with limited bandwidth/storage:

    repo sync -c -f --no-clone-bundle --no-tags --force-sync --optimized-fetch --prune

8.To start the build once everything is ready , Run to prepare our devices list

    . build/envsetup.sh

9.Now build (codename: osprey/lux/surnia/harpia/merlin)

    brunch codename  

Please see the [LineageOS Wiki](https://wiki.lineageos.org/) for building instructions.

