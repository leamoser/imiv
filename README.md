# imiv
Hier sind die Snippets zu finden, welche im Unterricht IM4 (Wordpress-Theme-Entwicklung) gebraucht werden.

## S01.01
```html
<!doctype html>
<html>

<head>
    <title>Mein Portfolio</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0, minimum-scale=1.0,user-scalable=yes">
</head>

<body>
    <header>
        <h1>Portfolio</h1>
        <p>Von Lea</p>
        <nav>
            <ul>
                <li>Das ist ein Navigationspunkt</li>
                <li>Das ebenfalls</li>
            </ul>
        </nav>
    </header>
    <main>
        <article>
            <p>Hier kommt der Hauptinhalt des Protfolios</p>
        </article>
    </main>
    <footer>
        <p>Hier kommt der Footer</p>
    </footer>

</body>

</html>
```
## S01.02
```html
<link type="text/css" rel="stylesheet" href="<?php bloginfo('stylesheet_url') ;?>">
```
