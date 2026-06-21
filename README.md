[index.html](https://github.com/user-attachments/files/29181517/index.html)
[vercel.json](https://github.com/user-attachments/files/29181519/vercel.json){
  "version": 2,
  "builds": [
    {
      "src": "index.html",
      "use": "@vercel/static"
    }
  ],
  "routes": [
    {
      "src": "/(.*)",
      "dest": "/index.html"
    }
  ]
}
