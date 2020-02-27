# imiv
Hier sind die Snippets zu finden, welche im Unterricht IM4 (Wordpress-Theme-Entwicklung) gebraucht werden.

## S01.01
```html
<!doctype html>
<html lang="de-CH">

<head>
    <title>Mein Portfolio</title>
    <meta charset="UFT-8">
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
## S02.01 - Navigation registrieren
```PHP
    add_action('after_setup_theme', 'navigation_registrieren');

    function navigation_registrieren(){
        register_nav_menu('hauptnavigation', 'Hauptnavigation oben');
    };
```
## S02.02 - Navigation einfügen
```PHP
<?php 
            
        $args = array(
        'theme_location' => 'hauptnavigation'
        );
            
        wp_nav_menu($args) ;?>
```
## S02.03 - Logo im Customizer registrieren
```PHP
add_action( 'after_setup_theme', 'theme_prefix_setup' );
function theme_prefix_setup() {
  add_theme_support( 'custom-logo' );
}
```
## S02.04 - Logo ausgeben
```HTML
<img src="
                    <?php     
                            $custom_logo_id = get_theme_mod( 'custom_logo' );
                            $image = wp_get_attachment_image_src( $custom_logo_id , 'full' );
                            echo $image[0] ;?>
                    " alt="hier alt eingeben">
```
## S03.01 - Start Loop
```PHP
<?php if ( have_posts() ) : while ( have_posts() ) : the_post(); ?>
```
## S03.02 - Rest Loop
```HTML
<?php endwhile; else : ?>
    <p>Hier gibt's leider nix zu sehen.</p>
<?php endif; ?>
```
## S05.01 - Beitragsbilder registrieren
```PHP
add_theme_support( 'post-thumbnails' );
```
## S05.02 - Gesamten Autor/innen-Namen ausgeben
```PHP
<?php

  $fname = get_the_author_meta('first_name');
  $lname = get_the_author_meta('last_name');
  $full_name = '';

  if( empty($fname)){
      $full_name = $lname;
  } elseif( empty( $lname )){
      $full_name = $fname;
  } else {
      $full_name = "{$fname} {$lname}";
  }

	//in der variabel $full_name ist nun der Name abgespeichert, es muss nur noch dieser mit PHP (echo) ausgegeben werden.
 ?>
 ```
 ## S05.03 - Schlagwörter ohne Links ausgeben
 ```PHP
   <?php
  $posttags = get_the_tags();
  if ($posttags) {
    echo '<ul>';
    foreach($posttags as $tag) {
      echo '<li>' .$tag->name. '</li>';
    }
    echo '</ul>';
  }
  ?>
  ```
  ## S06.01 - Return Self-Closing Shortcode
  ```PHP
  return '<div class="sociallink" style="color:' . $atts['color'] . '">
  <p><a href="#">Folge mir auf Facebook</a></p>
  <p><a href="#">Folge mir auf Twitter</a></p>
  </div>';
  ```
  ## S06.02 - Return Enclosing Shortcode
  ```PHP
  return '<div class="textauszeichnung">' . $content . '</div>';
  ```
  
