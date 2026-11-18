JTV SPORTS — Native Android + Adsterra Smartlink
================================================

এটি একটি Native Android Java সোর্স প্রজেক্ট; APK নয়।

ফিচার:
- Native Android home screen (WebView নয়)
- JTV SPORTS launcher icon
- Cricket / Football / Other categories
- Media3 ExoPlayer দিয়ে HLS (.m3u8) ও সমর্থিত stream playback
- Player controls
- Home screen-এ Adsterra Smartlink বাটন

Adsterra Smartlink:
- আপনার দেওয়া URL যুক্ত করা হয়েছে: https://auctionr.org/4/336775353b902c1f9550ed98f199e020
- বাটনে ব্যবহারকারী নিজে চাপলেই Android-এর বাইরের browser-এ লিংক খুলবে।
- অ্যাপ চালু হলেই বা চ্যানেল চালানোর সময় স্বয়ংক্রিয়ভাবে বিজ্ঞাপন খোলা হয় না।
- Smartlink-এর গন্তব্য ও বিজ্ঞাপনের কনটেন্ট লিংক প্রোভাইডার নিয়ন্ত্রণ করে; প্রকাশের আগে নিজের ডিভাইসে যাচাই করুন।
- বিজ্ঞাপনে নিজেরা ক্লিক করবেন না এবং ব্যবহারকারীকে জোর করে ক্লিক করাবেন না। Adsterra-এর বর্তমান publisher terms মেনে ব্যবহার করুন।

লাইভ চ্যানেল যোগ করার নিয়ম:
1. app/src/main/java/com/jtv/sports/MainActivity.java খুলুন।
2. buildChannels() ফাংশনের ভেতরে এই ধরনের লাইন যোগ করুন:
   channels.add(new Channel("Channel Name", "CRICKET", "https://YOUR-AUTHORIZED-STREAM/live.m3u8"));
3. category হিসেবে CRICKET, FOOTBALL অথবা OTHER ব্যবহার করুন।
4. URL অবশ্যই আপনার নিজের বা ব্যবহারের অনুমতি থাকা stream URL হতে হবে।

Build:
- Android SDK Platform 35 এবং JDK 17 প্রয়োজন।
- Android Gradle Plugin 8.6.1 / compatible Gradle environment ব্যবহার করুন।
- প্রথম build-এ internet লাগবে, কারণ AndroidX Media3 dependency ডাউনলোড হবে।

Package: com.jtv.sports
Min Android: API 24
Version: 1.0

গুরুত্বপূর্ণ:
- কোনো বাস্তব চ্যানেল URL বা VPS API যুক্ত নেই।
- AdMob SDK সরানো হয়েছে; এই সংস্করণে Adsterra Smartlink button আছে, native banner/interstitial SDK নয়।
- এটি সোর্স প্রজেক্ট; APK তৈরি করতে Build করতে হবে।
