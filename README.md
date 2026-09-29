# TLP48 Fan App v2
Static multi-page Vercel-ready prototype.

Pages: Home, Members, Member Profile, Shop, Token, Redeem, Orders, Profile, Login, Admin.

Demo user: fan@tlp48.com / 123456

Admin is not included in the demo user by default. To enable an admin for testing, open browser console and run:
const d=JSON.parse(localStorage.getItem('tlp48_db_v2')); d.users.push({id:99,name:'TLP48 Admin',email:'admin@tlp48.com',password:'admin123',role:'admin',token:99999}); localStorage.setItem('tlp48_db_v2',JSON.stringify(d));

IMPORTANT: This version stores data in browser localStorage. It is suitable for UI/prototype/testing only. For a real public shop, login, tokens, redeem codes, orders, image uploads and admin security should be moved to a server/database such as Supabase/Firebase with server-side authorization and payment/order handling.

## Why the old version was blank
The HTML pages referenced `app.js`, but that file was not included in the uploaded files. This package includes the missing `app.js` and a `single.html` entry point.
