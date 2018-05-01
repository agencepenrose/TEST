# MODIFICATIONS DE FICHIERS SUR LE DOSSIER DU THEME SALIENT ORGINAL

**Ces corrections sont à re-appliquer suite à chaque mise à jour du theme Salient**


## Page équipe, affichage de la bonne taille de photo pour les Team Member :

**MODIFICATION du fichier wp-content/themes/salient/nectar/tinymce/shortcode-porcessing.php ligne 836 :**

    $image_src = wp_get_attachment_image_src($image_url, ‘portfolio-thumb’);

par

    $image_src = wp_get_attachment_image_src($image_url, 'full’);


## Page actualités : affichage de la date sous la catégorie :

**MODIFICATION du fichier wp-content/themes/salient/nectar/tinymce/shortcode-processing.php**

Ajout de la mention
    
    <p class="date-article"> <?php echo get_the_date(); ?> </p>

à la ligne 3424 sous :

    echo '</span>'; ?>


## Page actualités : affichage de la date à côté de l’auteur et de la catégorie dans le slider 4 derniers articles (en haut de page) :

**MODIFICATION du fichier wp-content/themes/salient/nectar/tinymce/shortcode-processing.php**

Modification du paragraphe à la ligne 3757 :

    echo '<div class="grav-wrap"><a href="'.get_author_posts_url($post->post_author).'">'.get_avatar( get_the_author_meta('email'), 70,  null, get_the_author() ). '</a><div class="text">'. trim( $cat_output) . ' | <span>'.__('By',NECTAR_THEME_NAME).' <a href="'.get_author_posts_url($post->post_author).'" rel="author">' .get_the_author().'</a></span> | ' .get_the_date().'</div></div>'; ?>


## Modification ordre affichage du plugin Display Posts Shortcode :

**MODIFICATION du fichier wp-content/plugins/display-posts-shortcode/display-posts-shortcode.php**

Modification du paragraphe à la ligne 511 :  

    $output = '<' . $inner_wrapper . ' class="' . implode( ' ', $class ) . '">' . $image . $category_display_text . $date . $title . $author . $excerpt . $content . '</' . $inner_wrapper . '>';


## Modification vitesse défilement OwlCarousel :

**MODIFICATION du fichier wp-content/themes/salient/js/init.js**

Modification de la ligne 1735 :

    smartSpeed:1000