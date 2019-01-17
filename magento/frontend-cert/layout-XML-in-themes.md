# 3. Layout XML in Themes (18%)

## 3.1 DEMONSTRATE KNOWLEDGE OF ALL LAYOUT XML DIRECTIVES AND THEIR ARGUMENTS

Layout instructions make modifications to `<block/>` and `<container/>`, the building blocks of XML elements

- What layout XML elements exist and what is their purpose?
    - `Block`

        A block is a link between a PHP block class, which contains logic and a template which renders content such as text or ui element.

        - Magento recommends against specifying a class as it defaults to `\Magento\Framework\View\Element\Template`
        - Blocks can have child and grandchildren nodes and so on
        - `<Arguments/>` child nodes pass information from layout XML into block
        - **Attributes**

            `class`: name of class that 's responsible for rendering block output

            `name`: unique name given to block by developer

            `before`:  position block before an element inside same parent node by stating block name you would like to precede.  If you want to precede all blocks in parent node, use "-"

            `after`: position block after an element inside same parent node by stating block name you would like to precede.  If you want to succeed all blocks in parent node, use "-"

            `template`: template assigned to block, provides block markup. ** Always use Magento module path notation

                <!--Magento module path notation. Example: -->
                SwiftOtter_Hero::hero.phtml
                
                <!-- 
                	SwiftOtter_Hero = Module name
                	hero.phtml = template name
                -->

            `as`: alias for identifier

            `cacheable`: Defines whether a block element is cacheable.

    - `ReferenceBlock`

        These can be referenced  throughout layout

        Example of Reference Container

            // Example of ReferenceBlock being used to remove the block named from the layout
            <referenceBlock name="product.info.sku" remove="true"/>

        `remove` Removes block from layout

        `display=false` Prevents display of block but loads associated PHP classes

    - `Container`

        If you look in the root layout XML file you will see that a `<container/>` is the top most element.

        Structural element that holds other layout elements such as blocks and containers.

        Containers are helpful in providing a more extensible means of grouping and rendering child blocks because the HTML tag and class can be specified in XML.

            <container name="div.sidebar.additional" htmlTag="div" htmlClass="sidebar sidebar-additional" after="div.sidebar.main">
                <container name="sidebar.additional" as="sidebar_additional" label="Sidebar Additional"/>
            </container>

        - Attributes:

            `name`: name of container

            `label`: name to display in web browser

            `htmlTag`: a tag to wrap the child block output. Required if htmlClass is speci ed.

            `htmlClass`: the class(es) to apply to the wrapper HTML tag.

            `before`:  position container before an element inside same parent node by stating block name you would like to precede.  If you want to ***precede*** all containers in parent node, use "-"

            `after`: position container after an element inside same parent node by stating block name you would like to precede.  If you want to ***succeed*** all containers in parent node, use "-"

            `as`: alias for identifier

            `output`: NEED TO UNDERSTAND THIS ONE BETTER

            ** Containers don’t allow for <arguments>.

    - `ReferenceContainer`

        These can be referenced  throughout layout

        Example of Reference Container

            // Example of Reference Container: This adds a block to the product.info.type container
            
            <referenceContainer name="product.info.type">
            		<block name="additional.product.details" template="SwiftOtter::product.details.phtml">
            		</block>
            </referenceContainer>

    - `Action` — Depreciated. (Use `<Argument>` )

    - `Move` (processed before remove)

        Sets the declared block or container element as a child of another element in the specified order

        Attributes

        `element`: block or container to move

        `destination`: parent destination to be moved to

        `as`: Alias name for the element in the new location.

        `before` `after`: Specifies the element’s position relative to siblings.

    - `Remove`

            <remove src="Magento_Catalog::js/compare.js" />

- What are some important layout instructions?
    - `<update handle/>`

        Includes instructions from another layout handle...need to work on this one

    `<move/>`

    `remove`

## 3.2 DESCRIBE PAGE LAYOUTS AND THEIR INHERITANCE ( I should try to do this myself to get a better feel)

- Page layouts only contain containers unlike page configuration which contains blocks and containers.
- What is the purpose of page layouts?

    The purpose of page layouts is to create a structured and common set of layout instructions to render pages

- How can a custom page layout be created?

    Create Custom Layout: 

    See this to create module to add custom layout:

    [How to Create Module in Magento 2](https://www.mageplaza.com/kb/how-create-hello-world-module-magento-2.html)

    See this to create custom layout:

    [How to create custom layout page in magento2](https://webkul.com/blog/how-to-create-custom-layout-page/)

    1. Register custom layout in Namespace/Module/view/frontend/layouts.xml.  We're basically adding a `layout` to `page_layouts`
    2. Create layout page in Namespace/Module/view/frontend/page_layout/test.xml and then designing the new layout in the `page_layout` directory

- Where are the existing page layouts used?

    These can be customized in the admin panel on products, categories, &  CMS pages

- How can the root page layout be specified for all pages and for specific pages?
    - For all pages: Set the layout parameter on the `<page />` node to the ID of a layout specified in on of the `page_layout`XML files.
    - Specific pages can be target using the layout XML's filename

## 3.3 DEMONSTRATE UNDERSTANDING OF LAYOUT HANDLES AND CORRESPONDING FILES

`layout handle`:  a string that associates a layout XML file with a specific page or group of pages, to connect layout XML instructions with a controller.

- **Examples of layout handle for Customer Account Page**

    `customer_account_index` layout handle 

    `customer-account-index` body class

    **Layout handle determined by**

    `**customer**` Route ID in `magento2/app/code/Magento/Customer/etc/frontend/routes.xml` 

    `**account**` Controller Directory

    `magento2/app/code/Magento/Customer/Controller/Account/`

    `**index**`: Controller's action

    `magento2/app/code/Magento/Customer/Controller/Account/Index.php`

    This maps to a layout file in Module/Layout i.e.  `vendor/magento/module-customer/view/frontend/layout/customer_account_index.xml`

    or for our custom themes `<Theme>/Magento_Customer/layout` or

- How can the available layout handles for a given page be determined?
    - the quickest method is to look at the body class and replace `-` with `_`
    - Another way is to add this to the template being rendered to page in question

            <?php var_dump($block- >getLayout()->getUpdate()->getHandles()) ?>

- How do you add a new layout handle?

    Add to layout instruction: `<update handle="new_handle_name"/>`

- What is the purpose of layout handles?
    - To connect layout XML instructions with a controller.
- What are the most commonly used layout handles?

    • default
    • cms_index_index
    • cms_page_view
    • cms_index_index
    • cms_index_index_id_home • 1column
    • catalog_product_prices

    • default
    • catalog_product_view

    • catalog_product_view_type_simple
    • catalog_product_view_id_16
    • catalog_product_view_sku_24-UG07
    • 1column
    • catalog_product_prices

- How can layout handles be used during theme customization?

## 3.4 UNDERSTAND THE DIFFERENCES BETWEEN CONTAINERS AND BLOCKS

- What is the purpose of blocks? What is the purpose of containers?
    - Containers contain blocks and can wrap with HTML tag and class
    - Containers won't render if they have no children
    - Blocks are the lowest on the chain in rendering HTML
- How can containers be used in theming?
    - Eliminates useless HTML from PHTML files and allows the ability to wrap the blocks in the same place they are called.
- How can blocks be used in theming?

    Blocks handle all static-HTML rendering that containers do not handle.

- What is the default block type?

    `\Magento\Framework\View\Element\Template`

- How can the order of rendered child blocks be infuenced both in containers and in blocks?

    `before` and `after` attribures

## 3.5 DESCRIBE LAYOUT XML OVERRIDE TECHNIQUE

- XML files that are directly placed in the layout directory are merged, while XML files that are placed in the appropriate subdirectory of override replace the original file.
- How can layout XML be overridden? This question is in practice test and I missed initially because we rarely use

    Not ideal to override layout XML, but if needed to erase existing Magento layout, create a new XML file in

    `app/design/<theme>/Magento_<module>/layout/override/frontend/<layout_handle>.xml`

    i.e. `app/design/ SwiftOtter/Flex/Magento_Catalog/layout/override/frontend/ catalog_product_view.xml.`

- How can layout overriding be used in theming?
    - Not Common: If an existing layout file contains an instruction that you cannot change by extending, then overriding that layout file might be the only recourse.
- What are consequences of layout overrides during upgrades?
    - If the original layout file is changed during upgrade, because this method overrides and doesn't merge the layout files, these changes won't be include and other modules that depend on them would not have access.
- What is the effect of layout overrides on compatibility?
    - Overriding layout files circumvent any changes in core files and increase chances of trouble during upgrades.

## 3.6 UNDERSTAND LAYOUT MERGING

- What is layout merging?
    - Layout merging is the process of assembling all of the layout XML files into one large XML document.
    - When rendering page, Magento locates the layout instructions for  the particular handle and merges them together.
    - Then Magento traverses document and creates PHP classes for each block and renders output
    - Layout is merged in order the modules are loaded and if there are conflicts, the last module loaded wins.
- How do design areas influence merging?
    - Layout XML instructions are rst merged in the base area and then by the area that applies to the current request (frontend or adminhtml).

    1. Module base files loaded

    2. Module area files loaded (frontend or adminhtml)

    3. Sorted according to their module priority (array index of module’s position in app/etc/config.php) or if priority is equal, by alphabetical priority

    4. Theme files (layout and then override layout files) from furthest ancestor to current theme. i.e. (Magento >  BryantPark > Client Theme)

- How can merging remove elements added earlier?
    - use `remove` attribute in theme layout
- What are additive changes and what are overriding changes during layout merging?

    Need to add content here

## 3.7 UNDERSTAND PROCESSING ORDER OF LAYOUT HANDLES AND OTHER DIRECTIVES

- In what order are layout handles processed?
- In what order is layout XML merged within the same handle?
- How can the processing order be influenced?
- What are common problems arising from the merge order of layout declarations?