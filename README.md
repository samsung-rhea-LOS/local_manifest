Manifest for Android KitKat / LineageOS 11.0
====================================
Project corsica|GT-S5310/GT-S5312

---

Manual Way:

To initialize LineageOS 11.0 Repo:

    repo init -u https://github.com/LineageOS/android.git -b cm-11.0 --no-clone-bundle --depth=1

---

To initialize Manifest:

    curl --create-dirs -L -o .repo/local_manifests/local_manifest.xml -O -L https://raw.github.com/samsung-rhea-LOS/local_manifest/cm-11.0/local_manifest.xml

---

Sync the repo:

    repo sync -j$( nproc --all ) --force-sync -c --no-clone-bundle --no-tags --optimized-fetch --prune

---

Apply Pacht

	git clone https://github.com/bcm216xx-LOS/android_patches_los11.git
	sh android_patches_los11/apply-patches.sh
---

Fix buttons

	modify frameworks/base/data/keyboards/Generic.kl as described in this commit:
 	[Commit 29e8260](https://github.com/samshit-bcm/android_frameworks_base/commit/29e826068871a964b3134d184b009fab47ef43df)
	A patch will be developed soon, but in the meantime you'll have to do this
---

Initialize the environment:

    . build/envsetup.sh

---

To build:

	lunch lineage_zanin-userdebug
 	mka otapackage
  	cd $OUT
