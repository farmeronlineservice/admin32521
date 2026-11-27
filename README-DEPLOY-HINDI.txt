========================================
Farmer ID — Admin Panel Deploy (Private Git OK)
========================================

IS ZIP ME:
  admin/          → GitHub / Hosting par upload
  FIREBASE-RULES-ADMIN-ONLY-TOKENS.json → Firebase Rules

IMPORTANT
---------
1) Private GitHub repo se code chhupta hai.
2) Login Firebase Auth se hota hai — repo private/public se nahi.
3) Free GitHub Pages PRIVATE repo par aksar KAAM NAHI karta.
   Isliye private repo + site live rakhne ke 2 tareeke:

================================================
OPTION A — Private GitHub + Firebase Hosting (BEST)
================================================
1) Naya PRIVATE repo banao (GitHub)
2) Is ZIP ka "admin" folder content repo root me push karo
   (index.html root par ho)
3) PC par:
   npm install -g firebase-tools
   firebase login
   firebase init hosting
   - existing project: farmer-id-57d6e (ya aapka)
   - public directory: .  (jahan index.html hai)
   - single page: No
4) firebase deploy --only hosting
5) Jo URL mile (https://xxxx.web.app) wahi admin panel
6) Login: admin ID/password (Firebase Auth + adminUids)

================================================
OPTION B — GitHub Pro/Team + Private Pages
================================================
1) PRIVATE repo
2) admin folder files root me
3) Settings → Pages → Branch: main / root → Save
4) URL: https://USERNAME.github.io/REPO/
5) Free plan par private Pages nahi chalega

================================================
OPTION C — Public Pages (purana tarika)
================================================
Repo PUBLIC rakho, sirf admin panel files.
Login phir bhi Firebase se — bina password panel data
Rules se protect hona chahiye.

========================================
FIREBASE RULES (token sirf admin credit)
========================================
1) Firebase Console → Realtime Database → Rules
2) FIREBASE-RULES-ADMIN-ONLY-TOKENS.json paste → Publish
3) Data me:
   adminUids / 519XWFlvWmSoDeR5JMWAPEp4VZf2 = true
   (apna admin Auth UID)

========================================
LOGIN CHECKLIST
========================================
[ ] Authentication → Email/Password ENABLED
[ ] adminUids me aapka UID = true
[ ] Rules publish
[ ] Admin panel URL open → Login
[ ] Token credit test

Extension change zaroori NAHI.
