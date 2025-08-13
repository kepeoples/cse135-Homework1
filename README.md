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

## Step 5 – Compress Textual Content
Configured **gzip** compression in `/etc/nginx/nginx.conf` for the following file types: HTML, CSS, JS, JSON, XML, SVG, and font files.  

Settings applied:
- `gzip on;`
- Compression level: `5`
- Minimum file size: `256 bytes`
- Enabled `gzip_vary` and `gzip_proxied`

After reloading Nginx, verified compression with:
```bash
curl -sS -H 'Accept-Encoding: gzip' \
     -u teamuser:*** \
     -D - https://williampeoples135.site/ \
     -o /dev/null | grep -i content-encoding
```

## Step 6 - Verify and Test After Changes
Validation steps:

Checked response headers from the terminal (using curl) and Chrome DevTools.

Confirmed Content-Encoding: gzip was present for HTML, CSS, and JS files.

Verified reduced transfer sizes in DevTools Size column.

Conclusion:
Nginx configuration changes are successfully applied, and compression is active across all key file types.




