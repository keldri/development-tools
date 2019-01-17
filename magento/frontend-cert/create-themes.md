# 1. Create themes (7%)

# CREATE THEMES 7% ( 4 questions )

Feel pretty good about this section

## 1.1 Describe folder structure for local and Composer-based themes

Themes are found in the app/design folder and are structured in a package/theme path

    app/design/package/theme
    app/design/SomethingDigital/theme

- In which folders can themes be located?
    - Local themes are stored in app/design
    - Composer themes can live anywhere but by default usually live in vendor/package/theme
    - etc/, i18n/ and web/ are directories found in most themes.
- What directories are required in a theme?
- What determines where a theme is installed?
- Define purpose of each of the folders
- What is the difference if a theme is installed in one or the other of the possible directories?
- Composer

    M2 uses composer autoloader autoload.files node who's value is registration.php

    As M2 app starts up, Composer executes each file as specified in the autoload.files section. Registration.php then registers itself as a theme and the theme is now available.

## 1.2 DESCRIBE THE DIFFERENT FOLDERS OF A THEME

- etc/

    holds view.xml which provides configuration values for the theme in a structured format (i.e image sizes, gallery and magnifier settings, and file excludes)

- i18n/

    contains translations for theme

- media/

    has preview.jpg which provides a sample of what theme will look like when activated.

- web/
    - static files and directories downloaded by visitors and accessible from pub/static. Less/Sass files are placed in var/view_preprocessed before being compiled and put in pub/static
    - css/, fonts/, images/, and JS/ (theme specific JS)

## 1.3 DESCRIBE THE DIFFERENT FILES OF A THEME

- composer.json
    - Provides basic instructions, telling Composer info about module
    - autoload.files where composer is informed about registration.php which registers the module as a theme

- registration.php

    [registration.php](./registration-php-d3857517-25fd-4c88-a407-f8b14cf0d2e1.md)

        <!--Registration.php -->
        <!--(frontend or adminhtml)\PackageName\ThemeName
        i.e. adminhtml/Magento/backend or frontend/Magento/luma
        -->
        <?php
        \Magento\Framework\Component\ComponentRegistrar::register(
            \Magento\Framework\Component\ComponentRegistrar::THEME,
            'frontend/Travers/default',
            __DIR__
        );

- theme.xml

    [theme.xml](./theme-xml-8bdf397b-66c7-43d6-97ed-f35d9b68a28f.md)

    Describes theme to Magento ( title, parent, preview(optional)

        <theme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="urn:magento:framework:Config/etc/theme.xsd">
            <title>Travers default Theme</title>
            <parent>SomethingDigital/bryantpark</parent>
        		<!--optional-->
        		<media>
                <preview_image>media/preview.jpg</preview_image>
            </media>
        </theme>

## 1.4 UNDERSTAND THE USAGE OF MAGENTO AREAS: ADMINHTML/BASE/FRONTEND

ADD CONTENT LATER

## Noted Theme Files

[theme.xml](./theme-xml-8bdf397b-66c7-43d6-97ed-f35d9b68a28f.md)

[registration.php](./registration-php-d3857517-25fd-4c88-a407-f8b14cf0d2e1.md)