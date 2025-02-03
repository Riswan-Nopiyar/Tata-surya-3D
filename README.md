# Tata-surya-3D

### Penerapan 1: Memuat Script JavaScript di dalam `iframe`

```html
<!DOCTYPE html>
<html lang="id">
<head>
</head>
<body>
    <iframe id="solarSystem" width="100%" height="600px"></iframe>

    <script>
        async function loadJS() {
            const url = "https://cdn.jsdelivr.net/gh/riswan-nopiyar/Tata-surya-3D@main/index.js";
            try {
                const response = await fetch(url);
                const scriptText = await response.text();

                const iframe = document.getElementById("solarSystem").contentWindow.document;
                iframe.open();
                iframe.write("<script>" + scriptText + "<\/script>");
                iframe.close();
            } catch (error) {
                console.error("Gagal memuat script:", error);
            }
        }

        loadJS();
    </script>
</body>
</html>
```

### Penerapan 2: Memuat Script html di dalam `iframe`
```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Render HTML dari jsDelivr</title>
</head>
<body>
    <iframe id="preview" width="100%" height="600px"></iframe>

    <script>
        async function loadHTML() {
            const url = "https://cdn.jsdelivr.net/gh/riswan-nopiyar/Tata-surya-3D@main/index.html";
            try {
                const response = await fetch(url);
                const html = await response.text();
                const iframe = document.getElementById("preview").contentWindow.document;
                iframe.open();
                iframe.write(html);
                iframe.close();
            } catch (error) {
                console.error("Gagal memuat halaman:", error);
            }
        }

        loadHTML();
    </script>
</body>
</html>
```
