# Mobile Gallery: folders and setup

mobile-gallery/
  website/   customer website (index.html + firebase-config.js)
  admin/     admin panel (index.html + firebase-config.js)
  firebase/  firestore.rules, storage.rules, this guide (not uploaded to hosting)

Hosting
- Upload the `website` folder as your public site, and the `admin` folder as a separate site or sub-path (for example admin.yourdomain.com or yourdomain.com/admin).
- The admin links back to the website with ../website/index.html. If you host them on different domains, change that link in admin/index.html to your website address.
- Both folders already contain firebase-config.js with the same project config. If you change it, change it in both.

Firebase console
1. Firestore Database > Create database.
2. Authentication > enable Email/Password > Users > Add user (admin). Copy the UID. Settings > User actions: turn OFF sign-up.
3. Firestore > Rules: paste firebase/firestore.rules, replace PASTE_ADMIN_UID, Publish.
4. Authentication > Settings > Authorized domains: add your website domain and your admin domain.
5. Optional 3D model upload: Storage (Blaze plan), paste firebase/storage.rules (replace the UID), and set a CORS rule allowing GET from your website domain.
6. Open admin, log in, Settings > Load sample data (once).
