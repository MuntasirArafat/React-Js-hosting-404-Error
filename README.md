# React-Js-hosting-404-Error

## Introduction

This repository addresses and provides a solution for the common 404 error issue that occurs when reloading a ReactJS application hosted on shared hosting or any hosting environment. The problem arises due to the default behavior of servers when handling client-side routing.

![GitHub Logo]([https://example.com/image.jpg](https://www.hostinger.com/tutorials/wp-content/uploads/sites/2/2018/06/Error-404-on-Mozilla-Firefox-1024x762.webp))

## Problem Description

When a user reloads a page in a ReactJS application hosted on shared hosting, the server might not recognize the client-side routes, resulting in a 404 error. This issue is particularly common in environments where direct access to specific routes is not properly configured.

## Solution

To resolve the 404 error on page reload, follow these steps:

1. Open your `.htaccess` file in the root directory of your hosted ReactJS application.

2. Insert the following code:

```apache
<IfModule mod_rewrite.c>
  RewriteEngine On
  RewriteBase /
  RewriteRule ^index\.html$ - [L]
  RewriteCond %{REQUEST_FILENAME} !-f
  RewriteCond %{REQUEST_FILENAME} !-d
  RewriteRule . /index.html [L]
</IfModule>
```
This code ensures that all requests that do not correspond to an existing file or directory will be redirected to the  <code>index.html</code> file. This approach enables proper handling of client-side routes by the ReactJS application.
## Usage
Simply copy and paste the provided code into your <code>.htaccess</code> file, and save the changes. Ensure that the <code>.htaccess</code> file is in the root directory of your hosted ReactJS application.

This solution should effectively resolve the 404 error issue encountered during page reloads on shared hosting or similar environments.
