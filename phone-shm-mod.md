# 9th April 2025 - Phone WEAROS SHM MOD 1.4.1.006
Android Manifest:
- New ECG features added with several layouts...
- SDK raised to 31 (Android 12) - not patchable...

GUI:
- Country Code JO (Jordan) and XX (Unknown) added...
- new ECG strings added, instructions, warnings, tips...
- ECG illustrations and images added...
- ECG disclaimer observed "A single-lead ECG can't accurately classify other types of irregular heart rhythms, heart attack, stroke, high blood pressure, or other heart-related conditions."
- Storage issues message observed for phone and watch...
- Old ECG strings have been updated to follow the new ECG features, more classifications are added alongside description.

CODE:
- Code obscure is Observed!!!
- Two ECG folders observed, from this, it is assumed new features were added side by side with old logic...
- I was observed list of region restrictions updates (Check: https://t.me/xda_dante63/171)

ADDITIONAL PATCHES:
- I added support for Predictive Back Gestures (Android 13++)...
- I fixed Android 15 UI overlap with nav and status bar (Samsung will address this in next update for sure)..

~~

# History
> Some Old History does not have a detailed changelog, because I was only patching in the past

## 2024
### 4th Sept 2024 - Phone WEAROS SHM MOD 1.3.2.016 + 1.3.3.002
---
Android Manifest:
- Sleep Apnea observed, added and activated...

GUI:
- Sleep Apnea strings added, instructions, warnings, tips...
- IFU strings (instructions for use) added, calling online sources...
- Sleep Apnea illustrations and images added...
- (added in 1.3.3.002) Message added "Wear OS 5.0 support will expand to more Galaxy Watches soon."

CODE:
- JNI removed, this is great...
- Phone checks watch battery, if less than 30%, it will not record Sleep Apnea...
- Fetch Instructions for Use from the internet, fallback to local files...
- Class renaming Observed, will need to map old classes with new ones when applying Patches...
- List of countries and restrictions are clearer - in previous post (https://t.me/xda_dante63/118)...
- (added in 1.3.3.002) SQLCipher logic reworked, introduced secureroom to handle everything...

Note:
- There is a bug (including stock SHM), You may notice in Apnea tab, the button (instructions for use) does not work for some of you, it was fixed in a later release by hiding it depending on region, so ignore the button...
---

### 8th April 2024 - Phone (TIZEN & WEAROS) SHM MOD 1.2.5.003
Android Manifest:
- Manifest shows line to use native-library libhal.wsm (deleted because this detects knox state and makes shm not work on custom/rooted Samsung)

GUI:
- Assets have the country code MU—Mauritius, but no BP and ECG documents, so the next step would be to check the code for this country to confirm.
- Some strings related to BP were changed from measuring BP on your watch to Measuring BP, probably for Galaxy Ring Measurement? there is no mention of the Ring either way...
- Samsung removed their address in India...
- Switching all fonts to OneUiSans...

CODE:
- CSCUtil confirms MU has ECG and BP but not IHRN...
- Some minor modifications in BP, ECG, IHRN and some activities - namings - not visible to user...
- Samsung Health Data Permission logic added and binding Health Profile Data to SHM - nothing new here, just rewritten everything, either way, this cannot be performed with mod...

Note:
- Patching this was a wild ride due to renaming plenty of classes and functions, whenever I applied a patch, the app would crash because my patch has old namings, but all is well...
---
### 20th January 2024 - Phone (TIZEN & WEAROS) SHM MOD 1.2.4.003
---
GUI:
- assets has country code IN -  india with both BP and ECG documents, this is a clear indicator of support...
- plenty of permissions removed, this will probably solve the issue of SHM being flagged by TotalVirus (I already checked, this apk is safe)...
- Diagnostic added (might be for Samsung Members aka Samsung devices only)
- backup service updated (this might be backup and restore logic activated)
- Samsung India address added...
- I can see Sleep duration strings, not sure what this is, I will know when I look at the code...

CODE:
- CSCUtil confirms India got ECG and BP but not IHRN...
- I can confirm sleep layout and sleep tracking added but I do not see it being used anywhere nor even called - I can confirm sleep is not active from the manifest, probably future implementation...
---

## 2023
### November 2023 - Phone (TIZEN & WEAROS) SHM MOD 1.2.2.005
 > Patch #1 - WearOS - fixed a permission that was causing installation error (conflict with existing installed stock SHM)
---
Here is what I observed on phone SHM 1.2.2.005:
 * I don't see much of changes in UI...
 * They added several policy changes and users have to accept them stating they are 22 years old, but odd, this string tag is for china (example home_setup_cn_age_check) and not the world? or maybe they are lazy to fix it and decided to use china tag for the world?
 * They added Device ID Service, probably to get the Device ID and not generate it randomly...
 * They added a version check for phone and watch, if outdated, force update or close app...
 * BR (Brazil) got IHRN...
 * looky here, they changed the CSC logic, it will be bad news too those who changed watch CSC to get and use stock, now they are calling build.prop "ro.csc.sales_code" and I am betting this CSC is fixed to country of Sale and not the CSC we change (do correct me if I am wrong)
 * they are enforcing age check to be 22 and above, not sure how if calendrer is set by the user...?
 * BP Alarm i spoke of turns out to be scheduled for BP sensor...
---

### August 2023 
 * 9th August 2023 - Phone (TIZEN & WEAROS) SHM MOD 1.1.4.002 (phone - it may be the last working version for Androids with OS 7 and 8) and 1.2.1.009 (watch and phone - this works on android 9 and above)
---
Here is what I observed on UI:
 * MY - Malaysia - translations added finally...
 * The following countries' BP and ECG pdf files were removed...
  United Arab Emirates (AE), Azerbaijan (AZ), Georgia (GE), Honk Kong (HK), Indonesia (ID), Unknown (XL)...
  They are being updated to include the new Irregular Heart Rhythm feature... 

 * BP and ECG PDFs added:
  Honduras (HN), Nicaragua (NI), El Salvador (SV) , Venezuela (VE)
  This is known as support added...

 * Irregular heart rhythm notification message where the watch takes 5 auto measurements (over an hour, every 10 mins) to detect any issues, it needs Samsung Galaxy Watch4 or higher with Wear OS 4.0 and above (Patched)... 
 * Some new images added and Layout for the new IHRN feature...

As for the functionality (Code), here is what I observed:
 * JNI lib has been updated, might be more native functions injected (patched)...
 * Watch6 already added in this version, if I am not mistaken, code (993) seen in the manifest...
 * Smartswitchfiles <- backup added, but this depends on a new version of SmartSwitch, so far i don't see how this can be invoked...
 * The new feature Irregular Heart Rhythm is region locked (Patched) (IHRN_SUPPORTED_COUNTRIES): United States (US),South Korea (KR),United Arab Emirates (AE),Indonesia (ID),Hong Kong (HK),Russia (RU),Georgia (GE),Azerbaijan (AZ),Panama (PA),Guatemala (GT),Dominican Republic (DO),Costa Rica (CR),Ecuador (EC),Argentina (AR)
 * minSDK is set to 28 (Android 9), Android 7 and 8 have been Axed, the cause: 
 *** the new feature workmanger with notification channel requires android 9 and above...
 *** the new backup feature also requires android 9 and above as well...
 * Taiwan (TW) has BP and ECG (but I could've sworn it did have it?)...
 * ECG logic has been completely rewritten to support IHRN...

Finally, did some patches to fix bugs in Watch SHM:
 * Samsung IHRN auto-measurements were using wrong display messages (showing afib detected instead of auto measurement) and triggers sound + vibration notification every 10 minutes, I have fixed this by putting approprite message and set the notification as silent...
 * Samsung called method setWidgetTile when OS have removed it, this causes the app to crash, skipped the code...
 * Removed duplicate tiles of BP and ECG, this may take time to reflect in galaxy wearable...

### July 2023 - Nothing happened this month

### June 2023 - Nothing happened this month

### May 2023 - Tizen + WearOS
 * 23rd May 2023 - Phone (TIZEN & WEAROS) SHM MOD 1.1.3.002 Patch #1 & Watch SHM MOD 1.1.0.225 Patch #2
---
 * Killed Knox in SHM MOD thanks to XDA @blackmesa123 help...
 * WearOS: I fixed an issue related to opening the phone app from watch. It wasn't opening, but now it should work...
---

### April 2023 - Tizen + WearOS
 * 24th April 2023 - SHM MOD 1.1.3.002 Released...
---
Here is what I observed on UI:
 * New Zealand (NZ) & Mexico (MX) having BP & ECG enabled...
 * Some tweaks to BP layouts...

As for the functionality (Code), here is what I observed:
 * A lot of code cleaning (code removal or creating a function and calling it instead of repeating it)...
 * New countries visible in CSCUtil, New Zealand (NZ) & Mexico (MX), confirms BP and ECG support...
 * Method isMatchSavedSimAndNetworkISO was completely dropped...
 * accessories has a different logic to obtain name of the connected device...

Other than that, nothing significant...

---

### March 2023 - Nothing happened this month

### Februray 2023 - Tizen + WearOS
 * 17th Feb 2023 - Patch #3 (1.1.1.227) - I have fixed the mistake that Samsung have put when opening accessories and tapping on "Pair my Watch", it will try to open Galaxy Wearable instead of Bluetooth Settings...
 * 14th Feb 2023 - Patch #2 (1.1.1.227) - Fixed crash when installing the phone app on watch, some people install the phone app on watch because of rushing or not reading or confused about which app to install, when running phone app on watch, it will show message "PHONE APP, NOT FOR WATCH"...

### January 2023 - Tizen + WearOS
 * 25th Jan 2023 - Patch #1 (1.1.1.227) - Forgot to patch age limit from 22 to 16...
 * 24th Jan 2023 - SHM MOD 1.1.1.227 for phone
---
Here is what I observed on UI:
 * Malaysia & Thailand having BP & ECG enabled...
 * Luxembourg & Philippines both having privacy policy and terms of use but nothing obvious about BP or ECG...
 * more works on the icon to support shadows and so (and dropping static round icon)...
 * polishing to UI code (removing useless elements from elements) and seems BP & ECG ISO have their own container...
 * Added 2 Descriptions for BP & ECG (not sure where it will be visible till I patch and make it runnable):
  > Samsung Health Monitor Model Blood Pressure App is a mobile medical application operating on a compatible Samsung Galaxy phone and Samsung Galaxy Watch that can transfer the measurements to the app on the Galaxy phone, allowing the user to view blood pressure data and trends.
  
  > Samsung Health Monitor Model ECG App is a mobile medical application operating on a compatible Samsung Galaxy Watch (ECG-Tizen/WearOS) and Samsung Galaxy phone (ECG-Android). This app captures bioelectric signals from the user. It's used to measure ECG, and data can be transferred to the Samsung Galaxy phone, allowing users to store and share PDF data with healthcare professionals.
 * Samsung has an address in Thailand...
 * Malaysia language is English, they did not translate the app...


As for the functionality (Code), here is what I observed:
 * Message handler that was absent before, failed to sync to watch try again later (I think this is where the layout seems to spinning forever and after a restart, the app connects to the watch)...
 * New countries visible in CSCUtil, Macao (MO), Malaysia (MY), Thailand (TH), Philippines (PH), Norfolk Island (NF), Malta (MT), Luxembourg (LU)...

OK so, NF is checked as isAUModel (Australia), MO is checked alongside HK in a new method called isHongKongRegion (China), and TH has its own method isTHModel

Nothing about the PH or MT or LU but it is possible to say they got partial support if not fully...

what next:
 * they are changing font programmatically ("sec-roboto-light")...
 * BP and ECG results may look different as I spotted method fromHtml (used to add styling to text, such as color, bold, etc) in a TextView...
 * BP History Compare...? worth checking this one out <- this doesn't seem to be visual, this might be related to checking BP accuracy perhaps...
 * BP is heavily modified (Code gone poof lol and new code replacing it or nothing at all)
 * ECG is modified same as BP...
 * I don't think there is a significant change in the UI...
---

## 2022
### December 2022 - Nothing happened this month

### November 2022 - Tizen Only
 * 7th Nov 2022 - I saw an update on Galaxy store, Watch SHM 1.1.0053, I pulled and patched it, so just sign it and install it, All I can say is Canada, Turkey, Vietnam, and Taiwan languages added (so country support), I did not reverse the bin files (hex edit to see it) because it's exhausting, forgive me for that but let's just say optimization considering the direction of the WearOS mod is...

### October 2022 - Tizen + WearOS
 * 25th Oct 2022 - Patched SHM MOD 1.1.1.221 for phone...
---
SHM 221 (phone), here is what I have observed:
 * A complete remake of the styles and theming (it has been reported the app has dark mode) ...
 * Argentina [AR] has documentation on privacy and policy and terms of use of SHM (I don't see documents on BP or ECG)...
 * A lot of updates have been done on the PDF for different countries (few on privacy policy and a lot on ECG), and my guess is syntax and grammar...
 * Once again, more visual changes (buttons, images, animation, and so)...
 * I see they introduced a lot of new dimensions for large screens up to 1920dp (does that mean they want to support tablets...? maybe an update is coming for Galaxy Wearable that would work on Tablets 🤔)...
 * They got rid of the side-navigation drawer and moved everything to a new settings layout view...
 * They added time, as in edit time. Not sure what exactly the time is for...
 * method isFranceRegion added (Mayotte [YT] and Réunion [RE])...
 * I mentioned earlier about Argentina [AR]. It's being checked by CSCUtils (so maybe ECG and BP or one of them is working now)...
 * Most of the code files seem to be the same but they have a lot of annotations (this is just a quick randomly selected files, I didn't see them all)
 * Encryption logic changed, might work on devices that had encryption issues now...?

* big portions of code missing where I used to usually apply patches. This is a setback, there will be a delay as I now need to go through things step by step, with trial and error...

All I can say is it's another major update, Some of the patches I apply are no longer applicable due to the code being erased, moved or rewritten,  there is no ETA on when I can release the patch, I have to go through a lot of testing...

I am bracing myself for a bumpy hell ride...
---

### September 2022 - Tizen + WearOS
 * 18th Sept 2022 - Patched SHM MOD 1.1.1.209 for phone...
---
 > Most likely fixed a bug reported by users, i have no log of this...
---
### August 2022 - Tizen + WearOS
 * 17th Aug 2022 - Released SHM MOD 1.1.1.209 for phone...
---
Here is what is new in SHM 209 (Phone):
 * Turkey (TR) BP & ECG Support
 * Peru (PE) BP & ECG Support
 * Bolivia (BO) BP & ECG Support
 * Réunion (RE - island in France) - not sure if BP & ECG in France is controlled by states...?
 * Nicaragua (NI) - CSCUtil - BP or ECG or Both...?
 * Venezuela (VE) - CSCUtil - BP or ECG or Both...?
 * Added Russia (RU) BP & ECG PDF documentation
 * They made the app icon dynamic, something I have already done in the mod lol...
 * I do see a lot of UI changes, splash screen, BP calibration and several images removed...
 * Heavy code cleaning, lots of code has been deleted and some optimization for HTTP connection, assuming this network activity is for checking for shm updates (disabled in the mod)...
 * Accessibility added...
 * New PDF functionality using browser...?
 * obscured rootcheckutil (kinda too late for that)...
 * Turkey has a new layout apparently, method isKvKK for turkey not sure why...
 * Setting up profile might have changed...
 * BP and ECG code is heavily modified with many new things...
 * Wear connectivity code has changed, hopefully for better...

My plan is to apply the same patches that I applied on the previous version and see whether it's enough or not. If it's enough, I will check what UI changes might have been added...

Once everything seems fine and stable, I will add the theme patch and companion link...

I will do one final test, create the clone for WearOS, then roll it out for Beta Testing...

Might take some time as I brought an 8-inch windows 10 with me, and I am going for my appointments, so whenever I am free, I will work on it on that small screen of mine lol...

Hopefully, in a week I will release the patch and no more than that...
---
### July 2022 - Nothing happened this month

### June 2022 - Nothing happened this month

### May 2022 - Tizen + WearOS
 * 28th May 2022 - Patched phone SHM MOD adding Theme selector and created SHM MOD Companion that would assist you in getting updates, BP sync enabler, reaching me and so...
 * 4th May 2022 - Patched phone SHM MOD changing the icon from static to adaptive icon, bye bye ugly white frame...

### April 2022
 * Nothing happened this month

### March 2022 - Tizen + WearOS
 * 23rd March 2022 - Patched SHM "Age 16 and above" bug...
 * 22nd March 2022 - Released SHM MOD 1.1.1.191 for phone...
---
Here is what is new in SHM 191:
 * New layout BP ISO activity - probably details about BP
 * Canada BP & ECG Support
 * Israel BP & ECG Support
 * Taiwan got BP Support now
 * Ukraine BP & ECG Support
 * Vietnam BP & ECG Support
 * Latin America (XL) BP & ECG Support (7 countries 
"PA" -> PANAMA, "GT" -> GUATEMALA, "HN" -> HONDURAS, "SV" -> EL SALVADOR, "EC" -> ECUADOR, "CR" -> COSTA RICA, "DO" -> DOMINICAN REPUBLIC)
 * South Africa BP & ECG Support
 * BP Calibration Code changed
 * checkUpdateInterfaceWithLocation method, BP & ECG is now enabled and locked based on location
 * About section has isNoneApproveCountry which tells you whether country is approved or not, what's the point of this you ask? not a clue
 * CSC check sim card on Latin American and Caribbean (SELA)
 * Thai Language Added...

And tha.. tha... that's all folks...

Due to the major changes, here is my plan:
 * Release the MOD without Darkmode in beta test...
 * If all goes well, it goes public and I start working on Darkmode and it goes into beta test...
 * if all goes well too, it goes live...

I will do this on Weekend where I grab a big cup of coffee and go through Samsung Messy Code, wish me luck lol

So kindly do not ask if the mod is out, there is no way the mod would be out without my announcing it everywhere, you can ask about the progress...
---

### February 2022 - Tizen + WearOS
 * 11th February 2022 - Patched SHM MOD 1.1.1.181
---
>it has DarkMode (98% completed) and I fixed PDF sharing and exporting for Turkish language...
---

### January 2022 - Tizen + WearOS
 * 19th January 2022 - Released SHM MOD 1.1.1.181 for phone...
---
Here is a quick summary about version 181 for phone:
 * ECG PDF files have been compressed by removing revision history on the PDF file, changed some pictures and some are compressed (but this only dropped few KBs)
 * Added CSC restriction error message
 * Added Bluetooth control settings (Haven't seen it yet, just seen the code)
 * Added ECG wrong wrist warning
 * Added ECG wrong orientation warning messages
 * ECG Download data should tell what watch was used in the measurement (I didn't see anything about BP)
 * Overall BP and ECG optimized
 * Restrictions code is heavily modified, I'll need to revise the changes and make sure what they added does not break the MOD
 * They patched few things that I just observed where errors were unhandled (method try catch exception, the exception wasn't handled, SHM would crash without showing any message or reason)
 * Separated messages of Tizen Watches from WearOS Watches (example: instead of saying top button, they said home button, lol)

Summary:
I fear that I will have a headache lol, 171 -> 181, Major changes, wish the changes didn't include restrictions, so I will either get it working or not, I'd say 40% success on first attempt...

So I will probably have a beta phase after me finishing alpha phase testing...
---

## 2021
### December 2021 - Nothing happened this month

### November 2021 - Tizen + WearOS
 * 22nd November 2021 - Patched SHM MOD 1.1.1.171...
---
>Added 3 languages (Turkish, Persian and Filipino), changed the design of the logo for both phone and watch, changed the naming of the phone MOD in Google Drive...
---
 * 16th November 2021 - Released SHM MOD 1.1.1.171 for Phone...
---
Ok, so version 171...

What's new:
* BP code changes:
affects BP activity on phone...
* ECG code changes:
affects BP activity and wrist selection view on the phone...
* Fix missing permissions...
Feels like they forgot to get rid of some codes and use something else and they decided to do it...
These are the only changes, and missing permissions were vital, hence the fast update...
---
 * 14th November 2021 - Released SHM MOD 1.1.1.169 for Phone...
---
What's new:

* CODE TW, Taiwan support added...
* w673dp added, max width of 200 dip...
* version 169 is the version they started to obscure the code, I'll have to map things now to know what are the new files and lines and functions, etc, I hope I won't need large cup of coffee lol...
* they have done massive change to the code structure and where functions were called before...
* Taiwan has only ECG, no BP...

I am done from going through everything really fast, so conclusion is:

* As overall, I see a lot of conditions on TW which is Taiwan, so if the MOD doesn't work in Taiwan, report it to me...
* Locations of code being called has changed and a lot of the code structure has changed aside from seeing obscured functions being called, so even if i managed to create the MOD, if you face issues, report it to me...

My plan is to release it as a beta, I won't release it everyone on XDA as I know some people will host it on their own threads and cloud storage (sadly), so when beta is ready, I will announce it and I will pick a small group and expand slowly, if things are stable, then I roll it out...
---

### October 2021 - Tizen + WearOS
 * 17th October 2021 - testing complete - introducing 4 new languages, Hindi, Punjabi, Japanese and Malay...
 * 5th October 2021 - Edited the Fit2Installer "Run Me.bat", now it will check for the java version and will tell you from the beginning whether you have JDK15 or something else and whether you will face issues or not, so no one posts about JAVA "main" error again unless JDK is 15 and the error still exist, I wish to eliminate the repeated error of not installing or using JDK15 and also eliminate repeated posts that are about JDK15, do not post about having an error in Fit2Installer if you did not install JDK15 or have other JDKs installed...

### September 2021 - Tizen + WearOS
 * 27th September 2021 - some users reported that sync stopped in new Samsung Health, when investigated, the new update was a major update and it reset set features back to original values, it did not break the sync, do the required changes again in set features of Samsung Health and check that SHM permissions are still enabled and the sync will work again...
 * 26th September 2021 - Added Vietnamese Language support to the phone SHM MOD, so now the app won't be shown in the English Language, if there are any mistakes, please let me know, it would be nice to support languages that are unavailable, I also added in Chinese and Vietnamese "Google Translated by XDA-Dante63" as it's an unofficial translation + fixed age 22, I never thought Samsung would add a 4th age check...
 * 24th September 2021 - Added Chinese Simplified Language to the phone SHM MOD, so now the app won't be shown in the English Language, if there are any mistakes, please let me know, it would be nice to support languages that are unavailable, I also updated the F.A.Q Section...
 * 21st September 2021 - Added a video showing how to enable set features on Samsung Health to enable the BP sync between Samsung Health and Samsung Health Monitor... New Tutorial Video Uploaded...
 * 20th September 2021 - Google Drive updated and changed the entire structure and contents...
 * 19th September 2021 - Patched Watch SHM 1.1.0049 wgt, removed ECG and BP standalones, I will tidy google drive and recreate the video Tutorial, make it much simpler for you guys... Updated media photos in Post#3...
 * 15th September 2021 - Uploaded installer for Watch SHM 1.1.0049 wgt...
 * 9th September 2021 - Patched and released SHM MOD 1.1.1.157, support for AU and heavy code optimization + seems like there is BP cuff feature being implemented but hasn't been released yet...
 * 4th September 2021 - Updated thread, added a F.A.Q section for a video I made that should answer questions for those who are new to the SHM MOD...
 * 2nd September 2021 - Patched some new restrictions I bumped into, removed the following "low ram", "low storage" and "low battery" errors, they prevent launching SHM...

### August 2021 - From here and onwards, WearOS was rolled-out...
 * 23rd Aug 2021 - added a Tizen logo into version 153 and changed app version label included tizen, this is just to ensure that you don't use Tizen SHM with Watch4 because it's not compatible, changed the message when no watch is connected to "To use this feature, you need Galaxy Watch Active 2 or Galaxy Watch 3 that was released in a country where this feature has been approved." and finally, on my google drive, I renamed all phone apk files to include "Phone.Tizen." at the beginning of the name, this will help users that have both Tizen and WearOs watches in knowing what each apk is for...
 * 22nd Aug 2021 - created a thread for watch4, this thread will be only for Tizen devices...
 * 21st Aug 2021 - Watch4 mystery is revealed after long hours of dedication and with the help of different amazing members on Telegram (specifically Italy, love you all and never forget 🤌🏻 lol) and on reddit, the shm mod and watch4 is working but the process is different than the tizen watches, the mod is still being tested and still looking to improve it a bit, it works only on watch4, I will release it when I think it's perfect and has no flaws, I say in a day or two...
 * 17th Aug 2021 - More patches applied to SHM 1.1.1.153 and 1.1.1.151... I also made an installer that would push SHM 47 to the watch... I'm still investigating the matter in regards to the watch 4 detection issues through logcat of users, if I can't fix it, I will probably be able to do more when I get the watch on 10th of September...
 * 13th Aug 2021 - Released SHM 1.1.1.153 and patched 1.1.1.151, when no watch is connected, it will show a message instead of a black screen...
 * 12th Aug 2021 - Fixed SHM 1.1.1.151 issue when trying to accept, you should not face any issues...
 * 11th Aug 2021 - Released SHM 1.1.1.151, it has a bug where if running for the first time, you cannot proceed after hitting accept, so install the previous version of SHM 1.1.0.193, hit accept and finish the profile then update till I release a fix. I also removed from my Drive SHM 175 as it is deprecated, there is no use in having it anymore since you can't update from 175 to anything newer...
 * 8th Aug 2021 - Fixed Samsung Health interference with Samsung Health Monitor, it shouldn't crash anymore and all SHM MODs have been signed with release-keys of my own, this will ensure that my work wouldn't be tampered with or Modified for whatever purposes, if you install an update of SHM MOD from other sources and it fails, that means it has been tampered with, not released by me...
 * 7th Aug 2021 - Found out latest Samsung Health breaks SHM sometimes, workaround is uninstalling both, install SHM first, finish the profile then install Samsung Health again, DO NOT ENABLE THE SYNC INSIDE SHM DATA WITH SAMSUNG HEALTH... I will try my best to find time to investigate this and fix it... I also would like to add that "set features" was accidentally released to the public according to Samsung support, version 6.16 is the latest, I will investigate this as well to see if there is a solution, as a workaround, you can always downgrade Samsung Health, sync the BP and upgrade Samsung Health again... and finally, I did make a patreon page and I'd appreciate your support if you can, I believe that is everything in August for now...

### July 2021 - Tizen Only
 * 2nd July 2021 - Patched 191 by fixing few labels for the Chinese language, and Successfully Modified and uploaded SHM1.1.0.193...

### June 2021
 * Nothing happened this month...

### May 2021 - Tizen Only
 * 31st May 2021 - Patched 189, removed force update, and Successfully Modified and uploaded SHM1.1.0.191, changes are only Singapore Country support - I also had to go back to previous versions, I forgot to change the error of age from 22 to 16 for all languages as I only changed English (Versions affected 183, 189 & 191), I removed Samsung Health 6.17*, please use 6.16.0.047, if you updated and can't see set features, uninstall updates and grab a copy from my drive...
 * 29th May 2021 - Organized Google drive and added Samsung Health 6.17.0.019 that has set features which enables sync with SHM...
 * 14th May 2021 - Some members on XDA, reddit and youtube have struggled with finding JDK 15 since the URL keeps breaking, I decided to locate and download JDK 15 and upload it to my Google Drive, now you have two options, the link and google drive...

### April 2021 - Tizen Only
 * 11th April 2021 - Thanks to XDA juljoe2021 for the tip of using Developer mode on Samsung Health, it allows to bypass signature checks and Sync BP between Samsung Health and Samsung Health monitor, also thanks to XDA adfree, I uploaded the SHM version 43 for the watch and added the installer which has 3 countries support (CY, RU and HK) and some minor optimization, I also uploaded the latest Samsung Health that I used for the BP sync in SHM...
 * 3rd April 2021 - Successfully Modified and uploaded SHM1.1.0.189 - still investigating what has been added aside from 3 countries (CY, RU and HK)...

### March 2021 - Tizen Only
 * 28th March 2021 - I have gathered different solutions of members for the annoying Exception in thread "main" JAVA problem in a section so people can use one of the them to fix it and proceed signing the tpks...
 * 14th March 2021 - I forgot to post about the SHM 39 apk installer, Thanks to XDA adfree, I believe it patches the SHM 37 for bugs in the interface...
 * 10th March 2021 - the issue of hidden ECG and hidden BP was still shown for few users and now I am confident to say with more patches, I think SHM 181 & 183 is at its best, thanks to  XDA jmdomini as despite BP was hidden, he was able to use the BP by calling the activity which tells me that the restrictions was view related and not functionality...
 * 8th March 2021 - very few users reported that SHM still hides BP or ECG showing either "The blood pressure features require a Galaxy Watch Active 2 or later to work" or "The ECG features require a Galaxy Watch Active 2 or later to work", so I dag very deep hoping to find what I missed and I believe I found it & I patched the logic, now you should be able to see "The blood pressure and ECG features require a Galaxy Watch Active 2 or later to work." And to be able to use both BP and ECG on the app...
 * 3rd March 2021 - Organized the Thread, Patched 181 and 183, removed BP restriction for USA, Removed lock screen requirement, changed the message of age restriction from 22 to 16 and applied the check logic...
 * 1st March 2021 - Updated SHM1.1.0.181 & SHM1.1.0.183 removing device restriction and lowered age restriction from 22 to 16, special thanks to XDA l0nax, I also removed version detection, it shouldn't ask you to update to the latest version anymore...

### February 2021 - Tizen Only
 * 11th Feb 2021 - Successfully Modified and uploaded SHM1.1.0.183 root detection & country restriction removed...
 * 10th Feb 2021 - Successfully Modified and uploaded SHM1.1.0.181 root detection & country restriction removed + Added official SMH tpk installer for the watch...

### January 2021 - Tizen Only
 * 14th Jan 2021 - Uploaded a tutorial video, hope it helps...
 * 13th Jan 2021 - Fixed the Modified TPKs - the current ones are working 100% as they have been tested, please sign it and enjoy using it...
 * 10th Jan 2021 - Added Modified BP.tpk, ECG.tpk to be signed, those who fail to install any widget, check for SMH on your watch, if it's installed, it will prevent you from pushing original widgets, sign the modified widgets and push them either sdb or the tpk installer I added and it will work (Note, you need to add the tpk inside the TPKinstaller, decompile, add it and recompile and sign)...
 * 5th Jan 2021 - Added BP.tpk, ECG.tpk and TPK installer apk for editing and pushing if original tpk fail to install, check the Alternative way in the post...

## 2020
### December 2020 - Tizen Only
 * 24th Dec 2020 - Added individual widget installers, BP standalone & ECG standalone, if the watch has one of the widgets already, both widgets installer will fail to install...
 * 20th Dec 2020 - Added photos in post #3...
 * 14th Dec 2020 - Removed root detection from latest Samsung Health Monitor Mod (1.1.0.175.mod4) by XDA caravana
