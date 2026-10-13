# UNIVERSE COMPLAIN — বাংলা ও English / Setup Guide

ওয়েবসাইটে এখন বাংলা ও English ভাষা বেছে নেওয়ার selector আছে। ব্যবহারকারী Language / ভাষা মেনু থেকে নিজের পছন্দের ভাষা বেছে নিতে পারবেন।

এই প্যাকেজে একটি responsive ওয়েবসাইটের `index.html` এবং Firebase Firestore security rules আছে।

## ১) আগে ডেমো দেখো
`index.html` ফাইলটি Chrome-এ খোলো। অভিযোগ ও চ্যাট এই একই ব্রাউজারের local storage-এ থাকবে। এই ডেমো মোডে অন্য মানুষ বা অন্য ডিভাইসের সঙ্গে ডেটা শেয়ার হবে না।

## ২) সবার জন্য সত্যিকারের অনলাইন পোস্ট/চ্যাট চালু করতে Firebase লাগবে
1. https://console.firebase.google.com/ খোলো এবং একটি project তৈরি করো।
2. Project settings → Your apps → Web app যোগ করো; Firebase web config থেকে `apiKey`, `authDomain`, `projectId`, `appId` কপি করো।
3. Authentication → Sign-in method → **Anonymous** sign-in চালু করো।
4. Firestore Database তৈরি করো।
5. Firestore-এর Rules-এ এই ফোল্ডারের `firestore.rules`-এর নিয়মগুলো বসিয়ে Publish করো।
6. `index.html`-এর JavaScript-এ `firebaseConfig` খুঁজে `PASTE_YOUR...` placeholder-গুলোর বদলে নিজের config বসাও।
7. `index.html` আবার GitHub-এ আপলোড করে commit করো। এরপর সাইট Firebase-এর সঙ্গে সংযোগ করলে অভিযোগ ও পাবলিক চ্যাট অনলাইনে শেয়ার হবে।

Firebase config ওয়েব অ্যাপে ব্যবহার করার জন্য তৈরি; কিন্তু Firestore Rules অবশ্যই লাগবে। Firebase console বা config কখনোই অন্য কাউকে অ্যাকাউন্টে প্রবেশাধিকার দেওয়ার জন্য শেয়ার কোরো না।

## ৩) GitHub Pages-এ বিনামূল্যে প্রকাশ
1. https://github.com/ এ নিজের অ্যাকাউন্ট তৈরি/লগইন করো।
2. **New repository** চাপো; নাম দাও `universe-complain`; Public বেছে Create repository করো।
3. **Add file → Upload files** দিয়ে `index.html` আপলোড করো এবং **Commit changes** চাপো।
4. Repository → **Settings → Pages** খোলো।
5. **Build and deployment**-এ Source হিসেবে **Deploy from a branch** বেছে নাও।
6. Branch `main`, folder `/(root)` বেছে **Save** করো।
7. কিছুক্ষণ পর Settings → Pages-এ দেখানো URL খোলো। সাধারণত URL হবে `https://YOUR-USERNAME.github.io/universe-complain/`।

GitHub Pages ফাইল হোস্ট করে; এটি নিজে ডেটাবেস বা লাইভ চ্যাট দেয় না। অনলাইন চ্যাটের জন্য Firebase-এর ধাপগুলোও করতে হবে। সাইটটি সবার জন্য প্রকাশিত হবে।

## নিরাপত্তা ও গোপনীয়তা
- এই সাইটে পোস্ট/চ্যাট পাবলিক হতে পারে। কারও ফোন নম্বর, ঠিকানা, পাসওয়ার্ড, পরিচয়পত্র বা ব্যক্তিগত/সংবেদনশীল তথ্য পোস্ট কোরো না।
- অভিযোগগুলো স্বয়ংক্রিয়ভাবে সত্য বলে যাচাই করা হয় না। বাস্তবে চালুর আগে moderator, report/delete workflow, spam protection এবং privacy notice যোগ করা উচিত।
- অন্তর্ভুক্ত Rules শুধু authenticated users-দের সীমিত দৈর্ঘ্যের লেখা পড়া/লেখার অনুমতি দেয়। এটি সম্পূর্ণ moderation ব্যবস্থা নয়; বাস্তবে চালুর আগে rate limiting, moderator-only deletion, age-appropriate safety ব্যবস্থা এবং abuse handling যোগ করো।
- কোনো ব্যক্তির বিরুদ্ধে গুরুতর অভিযোগ প্রকাশের আগে তথ্য যাচাই করো; ব্যক্তিগত তথ্য প্রকাশ বা হুমকি অনুমোদন কোরো না।
