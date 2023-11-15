**Path traversal** is also known as directory traversal. These vulnerabilities enable an attacker to read arbitrary files on the server that is running an application. This might include:
- Application code and data
- Credentials for back-end systems
- Sensitive operating system files

## Reading arbitrary files via path traversal
Imagine a shopping application that displays images of items for sale. This might load an image using the following HTML
```html
<img src="/loadImage?filename=cat.jpg">
```

The `loadImage` URL takes a filename parameter and returns the contents of the specified file. The image files are stored on disk in the location `/var/www/images`. To return an image, the application appends the requested filename to this base directory and uses a filesystem API to read the contents of the file. In other words, the application reads from the following file path:
`/var/www/images/cat.jpg`

This application implements no defenses against path traversal attacks. As a result, an attacker can request the following URL to retrieve the `/etc/passwd` file from the server's filesystem:
```url
https://insecure-website.com/loadImage?filename=../../../etc/passwd
```
