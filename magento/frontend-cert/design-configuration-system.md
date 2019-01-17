# 2. Magento Design Configuration System 7%

# Magento Design Configuration System 7% (4 questions)

**Key Words:**  `theme hierarchy` `fallback sequence` `theme inheritance`

## 2.1 DESCRIBE THE RELATIONSHIP BETWEEN THEMES

- What kind of relationships can exist between themes

    Parent/Child

    In the theme's theme.xml file you can specify the theme's parent node, which is what "child" theme or your theme is built off of or inherits files from.  This is an example of theme hierarchy used to determine the fallback sequence for theme inheritance.

    `<parent>Magento/blank</parent>`

- What is the difference between a parent theme and a child theme?

    A child theme is created based on a parent theme. If child theme is enabled, it will be the them displayed. Child themes can both be child themes and parent themes. 

- How can the relationship between themes be defined and influenced?

    Theme.xml defines the relationship between themes with the presence of a `<parent>` node. Each theme will have a parent with the exception of Magento theme

    [Copy of theme.xml](./Copy-of-theme-xml-44f70928-7536-41bc-8ff1-b1863396cf70.md)

- How is that taken into account when creating a custom theme or customizing an existing theme?

    The relationship between themes determines the fallback sequence, (i.e. what theme to grab a file from if the file doesn't exist, i.e parent, and if not there it falls back to parent of parent, etc.)

## 2.2 CONFIGURE THE DESIGN SYSTEM USING THE OPTIONS FOUND IN THE ADMIN UI UNDER CONTENT > DESIGN > CONFIGURATION

These configurations are associated with a STORE, NOT a theme.

`CONTENT > DESIGN > CONFIGURATION`

- How do the configuration settings affect theme rendering?

    options in content > store > design > configuration allow you to modify options in admin for the theme that is applied to the store (i.e. footer copyright, logo, HEAD title, transactional emails)

- What happens if a theme is added or removed?

    If registered themes are automatically added to the themes table in DB and available in admin panel. See screen to right. If theme removed, the default theme will be automatically used but theme won't be removed from database.

![](Image2018-11-27at3-809ef791-2f1d-47ac-9214-fc14bfb86600.06.45PM.png)

## 2.3 SCHEDULE A TEMPORARY THEME CONFIGURATION TO A STORE VIEW

`CONTENT > DESIGN > SCHEDULE`

- What is the purpose of this feature?

    Design Schedule applies the theme between the dates specified.

    This allows you to schedule site design changes for a specific period of time (i.e. cyber monday only)

    When site design change is scheduled to start, the theme modified for scheduled design will become primary theme for store until schedule ends.

- Can scheduled design changes overlap one another?

    NO

![](Image2018-11-27at4-fcc79cc7-8a04-4116-9287-949898975518.34.57PM.png)