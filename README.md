# CSE 135 – Team X Website

**Domain:** https://williampeoples135.site/ 
**Root directory:** /var/www/williampeoples135.site


## Deployment process
1. Code is stored in GitHub.
2. Push changes to `main` branch.
3. Server pulls the latest code (manual `git pull` or GitHub Actions).

## Checklist
- [x] HTML passes [W3C Validator](https://validator.w3.org/nu/).
- [x] Favicon loads without 404.
- [x] robots.txt present.
- [x] Deployed to live domain.
- [ ] Demo GIF/MP4 showing deployment in action.

## Site Login
1. Username: kevin
2. Password: Kevin09


## Step 5 – Compress Textual Content
I configured **gzip** compression in `/etc/nginx/nginx.conf` to compress HTML, CSS, JS, JSON, XML, SVG, and font files. The configuration included enabling gzip, setting a compression level of 5, a minimum file size of 256 bytes, and enabling `gzip_vary` and `gzip_proxied`.  

After reloading Nginx, I verified compression by running:
```bash
curl -sS -H 'Accept-Encoding: gzip' -u teamuser:*** -D - https://williampeoples135.site/ -o /dev/null | grep -i content-encoding

The response showed Content-Encoding: gzip. In Chrome DevTools → Network tab, the Response Headers for HTML, CSS, and JS files also displayed content-encoding: gzip. Transfer sizes were smaller than resource sizes, confirming that compression is working.

## Step 6 – Verify & Test After Changes
I validated the compression setup by checking response headers both from the terminal (using curl) and in Chrome DevTools.

For HTML, CSS, and JS files, the Content-Encoding: gzip header was present, meaning files are being compressed before being sent to the browser. In DevTools, the “Size” column confirmed reduced transfer sizes, which shows compression benefits are active.

These verifications ensure that the Nginx configuration changes are correctly applied and that compression is functioning across all key file types.
