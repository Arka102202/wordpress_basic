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

## Some important functions of WordPress

- `site_url`: to get the root url: site_url(" pass anything that you want to add after root URL");
- `get_the_ID`: to get the `current page`'s ID.
- `wp_get_post_parent_id`: will get the parent's ID of the `current page`.
- `the_title`: will get the title of  `current page`.
- `get_the_title`: will get the title of that page whose ID will be passed to the func.
- `the_content`: will get the title of  `current page`.
- `get_the_content`: will get the title of that page whose ID will be passed to the func.
- `the_permalink`: will get the permanent link or URL of `current page`.
- `get_the_permalink`: will get the permanent link or URL of that page whose ID will be passed to the func.
- `wp_trim_word(str, wordCount)`: str => is the actual string that you want to trim to the word count.
- `wp_reset_postdata()`: run this after the while loop of you custom query.
- `wp_list_pages(options)`: prints out all the pages.

    ```php
        `option` = array(
                "title_li" => none,
                "child_of" => id_of_that_page,
                "sort_column" => "menu_order",
            );
    
    ```

- `get_pages(options)`: lists out all the pages.

    ```php
        `option` = array(
                "child_of" => id_of_that_page
            );

    ```

- `wp_nav_menu(options)`: lists out all the items or links from a menu.

    ```php
        `option` = array(
                "theme_location" => "nameOfTheMenu1"
            );

    ```

- `is_page("page-slug")`: returns true if you are on that very page.

## Template Hierarchy

### name of different pages for different type of elements

- `index.php` is the default for all the types.
- `single.php` for one `Post` type element.
- `page.php` for one `Page` type element.

<img src="https://i0.wp.com/developer.wordpress.org/files/2014/10/Screenshot-2019-01-23-00.20.04.png?ssl=1" alt="word-press template hierarchy explained">
