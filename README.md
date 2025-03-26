Manifest for Android Marshmallow / Cyanogenmod 13
====================================
Project zanin | GT-B5330

---

Manual Way:

To initialize LineageOS 13 Repo:

    repo init -u https://github.com/LineageOS/android.git -b cm-13.0 --no-clone-bundle --depth=1

---

To initialize Manifest:

    curl --create-dirs -L -o .repo/local_manifests/local_manifest.xml -O -L https://raw.github.com/samsung-rhea-LOS/local_manifest/cm-13.0/local_manifest.xml

---

Sync the repo:

    repo sync -j$( nproc --all ) --force-sync -c --no-clone-bundle --no-tags --optimized-fetch --prune

---

Initialize the environment:

    . build/envsetup.sh

---

To build:

    lunch lineage_zanin-userdebug
    mka otapackage
