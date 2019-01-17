# 1. Create themes (7%)

# CREATE THEMES 7% ( 4 questions )

Feel pretty good about this section

## 1.1 DESCRIBE FOLDER STRUCTURE FOR LOCAL AND COMPOSER BASED THEMES

- Themes are found in the app/design folder and are structured in a package/theme path

    app/design/package/theme
    app/design/SomethingDigital/theme

<br>

<details>
    <summary>In which folders can themes be located?</summary>
    <ul>
        <li>Local themes are stored in app/design</li>
        <li>Composer themes can live anywhere but by default usually live in vendor/package/theme</li>
        <li>etc/, i18n/ and web/ are directories found in most themes.</li>
    </ul>
</details>
<br>

<details>
    <summary>What directories are required in a theme?</summary>
    <ul>
    </ul>
</details>

<br>

<details>
    <summary>What determines where a theme is installed?</summary>
    <ul>
        <li></li>
    </ul>
</details>

<br>

<details>
    <summary>Define purpose of each of the folders</summary>
    <ul>
        <li></li>
    </ul>
</details>

<br>

<details>
    <summary>What is the difference if a theme is installed in one or the other of the possible directories</summary>
    <ul>
        <li>
        </li>
    </ul>
</details>

<br>

<details>
    <summary>Composer</summary>
    <ul>
        <li>M2 uses composer autoloader autoload.files node who's value is registration.php</li>
        <li> As M2 app starts up, Composer executes each file as specified in the autoload.files section. Registration.php then registers itself as a theme and the theme is now available.</li>
    </ul>
</details>

---

## 1.2 DESCRIBE THE DIFFERENT FOLDERS OF A THEME

<details>
    <summary>etc/</summary>
    <ul>
        <li>Holds view.xml which provides configuration values for the theme in a structured format (i.e image sizes, gallery and magnifier settings, and file excludes)</li>
    </ul>
</details>

<br>

<details>
    <summary>i18n/</summary>
    <ul>
        <li>contains translations for theme</li>
    </ul>
</details>

<br>

<details>
    <summary>media/</summary>
    <ul>
        <li>has preview.jpg which provides a sample of what theme will look like when activated.</li>
    </ul>
</details>

<br>

<details>
    <summary>web/</summary>
    <ul>
        <li>static files and directories downloaded by visitors and accessible from pub/static. Less/Sass files are placed in var/view_preprocessed before being compiled and put in pub/static</li>
        <li>css/, fonts/, images/, and JS/ (theme specific JS)</li>
    </ul>
</details>

## 1.3 DESCRIBE THE DIFFERENT FILES OF A THEME

<details>
    <summary>composer.json</summary>
    <ul>
        <li>Provides basic instructions, telling Composer info about module</li>
        <li>autoload.files where composer is informed about registration.php which registers the module as a theme</li>
    </ul>
</details>

<br>

<details>
    <summary>registration.php</summary>

</details>

<br>

<details>
    <summary>theme.xml</summary>
    <p>Describes theme to Magento ( title, parent, preview(optional)</p>
    <code>
    
    <theme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="urn:magento:framework:Config/etc/theme.xsd">
        <title>Travers default Theme</title>
        <parent>SomethingDigital/bryantpark</parent>
            <!--optional-->
            <media>
            <preview_image>media/preview.jpg</preview_image>
        </media>
    </theme>

    </code>
</details>




## 1.4 UNDERSTAND THE USAGE OF MAGENTO AREAS: ADMINHTML/BASE/FRONTEND

ADD CONTENT LATER
