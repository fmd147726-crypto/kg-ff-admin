KG FF PANEL ADMIN PANEL

Files were adapted from the supplied admin-panel ZIP:
- Branding changed to KG FF PANEL.
- Firebase configuration updated to your supplied kg-ff-panel project.
- Existing page filenames and database paths are preserved.
- Google sign-in and admins/super + admins/normal checks in the original login flow are preserved.

IMPORTANT SETUP
1. Upload the contents of this folder to your GitHub Pages repository.
2. In Firebase Authentication, enable Google as a sign-in provider.
3. In Authentication > Settings > Authorized domains, ensure fmd147726-crypto.github.io is listed.
4. In Realtime Database, add your admin email to admins/super using the key format used by the app: periods in the lowercase email replaced with commas.
   For fmd147726@gmail.com, the key is fmd147726@gmail,com.
   Preserve the data shape expected by your existing admins/super record.
5. Review your Realtime Database Rules. The screenshots previously provided showed .read and .write set to true. That is unsafe for production. Do not leave public writes enabled. Apply rules that preserve your public site's required reads and restrict writes to authorized admins.
6. Test each management page on the deployed site.

NOTES
- The Firebase web config is intended to be public; do not put service-account private keys in browser code.
- The email fmd147726@gmail.com is the account you showed, but the code's existing authorization still depends on the admins/super or admins/normal database records. This ZIP does not silently bypass that permission logic.
- No live Firebase sign-in or writes were tested from this environment.
