# Any thing that goes into function.php

## to add `script` or any `style` file need to use the following code in the `function.php` file

```php
// first use wp_header(); inside the <head></head> of the header.php file so that wordPress can load what ever file it requires........
    <?php

    // the following section is to add any script or style file
    function script_enqueuing_func_name(){
        // get_styleSheet_uri() ==> gives you the location of the main style sheet location.
        wp_enqueue_style("provide_name_to_identify", get_theme_file_uri("file relative path goes here"));
    }

    add_action("wp_enqueue_script", "script-enqueuing_func_name");

    // to add the appropriate title to every page but default one

    function extra_feature_title() {
        add_theme_support("title-tag");
    }

    add_action("after_setup_theme", "extra_features_title");

```

## to add dynamic menu at different locations use the following code in the `function.php` file

```php
    <?php

    // to add a menu location which is nothing but a variable that has access to the menu items
    // for multiple menu add multiple menu location variable

    function extra_feature_menu() {
        register_nav_menu("nameOfTheMenu1", "Name of the Menu 1");
        register_nav_menu("nameOfTheMenu2", "Name of the Menu 2");
    }

    add_action("after_setup_theme", "extra_features_menu");
```
