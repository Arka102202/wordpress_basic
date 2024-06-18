# how to add the famous `While` loop in WordPress

```php
    <?php 
    
        // heart of every page
        while(have_posts()){
            the_post(); ?>
            <h2><a href="<?php the_permalink(); ?>"><?php the_title();?></a></h2>
            <p><?php the_content();?></p>
        <?php } 

    ?>
```

# name of different pages for different type of elements:

  - `index.php` is the default for all the types.
  - `single.php` for one `Post` type element.
  - `page.php` for one `Page` type element.


# to add `script` or any `style` file need to use the following code in the `function.php` file:

```php
// first use wp_header(); inside the <head></head> of the header.php file so that wordPress can load what ever file it requires........
    <?php

    // the following section is to add any script or style file
    function script-enqueuing_func_name(){
        // get_styleSheet_uri() ==> gives you the location of the main style sheet location.
        wp_enqueue_style("provide_name_to_identify", get_theme_file_uri("file relative path goes here"));
    }

    add_action("wp_enqueue_script", "script-enqueuing_func_name");

    // to the appropriate title to every page but default one

    function extra_feature() {
        add_theme-support("title-tag");
    }

    add_action("after_setup_theme", "extra_features");
```



## Some important functions of WordPress:

1.  to get the root url: site_url(" pass anything that you want to add after root URL");