# CSE 135 – Team X Website

**Domain:** [https://williampeoples135.site/](https://williampeoples135.site/)  
**Root Directory:** `/var/www/williampeoples135.site`

---

## Deployment Process
1. Code is stored in GitHub.
2. Push changes to the `main` branch.
3. Server pulls the latest code (manual `git pull` or via GitHub Actions).

---

## Checklist
- [x] HTML passes [W3C Validator](https://validator.w3.org/nu/).
- [x] Favicon loads without 404.
- [x] `robots.txt` present.
- [x] Deployed to live domain.
- [ ] Demo GIF/MP4 showing deployment in action.

---

## Site Login
- **Username:** `kevin`  
- **Password:** `Kevin09`

---

## Summary of HTML File Changes in DevTools After Compression
After enabling **gzip** compression in Nginx:
- Chrome DevTools showed a `Content-Encoding: gzip` header in the **Response Headers** for HTML, CSS, and JS files.
- The “Size” column in the Network tab displayed **smaller transfer sizes** compared to the actual resource sizes, indicating that files were being compressed before being sent to the browser.
- This resulted in faster page load times and reduced bandwidth usage.

---

## Summary of Removing 'Server' Header
For security hardening, I removed the `Server` header from Nginx responses to prevent exposing server details.  
- This was done by adding:
  ```nginx
  server_tokens off;
  ```

in the nginx.conf file.

After reloading Nginx, Chrome DevTools and curl -I confirmed that the Server header was no longer present in HTTP responses.

This reduces the amount of information available to potential attackers.





