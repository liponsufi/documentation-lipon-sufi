# Django template & Static Files
- in the django-template html code  not working  **emmet  ( so go to setting and search emmet then go to emmet-include language and added to  name ⇒ django-html and value ⇒ html**
- if you are using prettier extension  then follow the process ⇒⇒⇒⇒
- go to setting and then go to json.setting and added this code

```json
 "[django-html]":{
        "editor.formatOnSave": false
    }
```

## **Tailwind css configure for the django project**

- first go to tailwind css website version 3
- and in the folder of code create package.json and paste the code
```json
{
  "devDependencies": {
    "autoprefixer": "^10.4.20",
    "postcss": "^8.4.49",
    "tailwindcss": "^3.4.16"
  },
  "scripts": {
    "build:tailwind": "npx tailwindcss -i ./static/css/tailwind.css -o ./static/css/output.css --minify",
    "watch:tailwind": "npx tailwindcss -i ./static/css/tailwind.css -o ./static/css/output.css --watch"
  }
}
```

- go to terminal and run the code  **npm install**
- **npx tailwindcss init** in the terminal
- paste in the content of **tailwind.config.js**

```json
"./templates/**/*.html",
 "./**/templates/**/*.html",
 ```
 in the terminal **npm run build:tailwind**



 ## tailwind css class suggest na korle

### VS Code এক্সটেনশন সেটিংস (সবচেয়ে কমন সমস্যা)

আপনি যদি Django ব্যবহার করেন, তবে VS Code আপনার ফাইলকে **"Django HTML"** হিসেবে চেনে, কিন্তু Tailwind এক্সটেনশন শুধু **"HTML"** ফাইল চেনে। এটি ঠিক করতে:

1. VS Code-এর **Settings**এ যান (Ctrl + ,)।
2. উপরে সার্চ বারে লিখুন **`tailwind include languages`**।
3. **Tailwind CSS: Include Languages** সেকশনে **Add Item**এ ক্লিক করুন।
4. বাম পাশে লিখুন `django-html` এবং ডান পাশে লিখুন `html`।
5. একই ভাবে `html` এর জন্য `html` যোগ করুন।





---

### ২. IntelliSense সেটিংস আপডেট

সরাসরি আপনার `settings.json` ফাইলে নিচের কোডটুকু যোগ করলে সাজেশন আসা নিশ্চিত হবে:

JSON

```json
"tailwindCSS.includeLanguages": {
    "django-html": "html",
    "html": "html"
},
"editor.quickSuggestions": {
    "strings": true
},
"tailwindCSS.experimental.classRegex": [
    ["class=[\"'\\{]([^\"'\\}]*)[\"'\\}]", "([^\\s\"'\\{]*)"]
]
```

---

### ৩. `tailwind.config.js` ফাইলে পাথের ভুল

আপনার কনফিগারেশন ফাইল যদি আপনার টেমপ্লেট ফাইলগুলোকে খুঁজে না পায়, তবে এক্সটেনশন কনফিউজড হয়ে যায়। আপনার ফাইলটি এভাবে চেক করুন:

JavaScript

```json
/** @type {import('tailwindcss').Config} **/
module.exports = {
  content: [
    "./templates/**/*.html",          // মেইন টেমপ্লেট
    "./**/templates/**/*.html",       // অ্যাপের ভেতরের টেমপ্লেট
    "./static/js/**/*.js",            // জাভাস্ক্রিপ্ট ফাইল
  ],
  // বাকি কোড...
}
```

---

### ৪. ফাইল মোড পরিবর্তন (Quick Fix)

যদি উপরে কোনো কাজ না হয়, তবে তাৎক্ষণিকভাবে এটি ট্রাই করুন:

- আপনার HTML ফাইলটি ওপেন করুন।
- VS Code-এর নিচে ডানদিকের কোণায় দেখুন **"Django HTML"** লেখা আছে।
- সেখানে ক্লিক করে লিস্ট থেকে শুধু **"HTML"** সিলেক্ট করুন।

### 5. ভিএস কোড উইন্ডো রিলোড দিন

সেটিংস পরিবর্তনের পর অনেক সময় এক্সটেনশন ক্যাশ ধরে রাখে। তাই:

- কিবোর্ড থেকে Ctrl + Shift + P চাপুন।
- বক্সে লিখুন: Developer: Reload Window
- এন্টার প্রেস করুন।
