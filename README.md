# React-Js-hosting-404-Error
React Js hosting 404 Error 


To slove 404 error on page reload in shared hosing or any hosting just insert this code in .htaccess file.txt

```
<IfModule mod_rewrite.c>
  RewriteEngine On
  RewriteBase /
  RewriteRule ^index\.html$ - [L]
  RewriteCond %{REQUEST_FILENAME} !-f
  RewriteCond %{REQUEST_FILENAME} !-d
  RewriteRule . /index.html [L]
</IfModule>
```
