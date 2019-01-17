# Migrations

## Block Migrations

    # Create a migration with code which will create CMS block based on data of existing CMS block (specified by identifier).
    php bin/magento migrate:make --create-from-block=block_identifier --module=SomethingDigital_MigrationProject CreateFancyPage
    
    # Create a migration with code which will update CMS block based on data of existing CMS block (specified by identifier).
    # You have to make necessary changes into CMS block data in a code inside migration script.
    php bin/magento migrate:make --update-from-block=block_identifier --module=SomethingDigital_MigrationProject CreateFancyPage

## Page Migrations

    # Create a migration with code which will create CMS page based on data of existing CMS page (specified by identifier).
    php bin/magento migrate:make --create-from-page=page_identifier --module=SomethingDigital_MigrationProject CreateFancyPage
    
    # Create a migration with code which will update CMS page based on data of existing CMS page (specified by identifier).
    # You have to make necessary changes into CMS page data in a code inside migration script.
    php bin/magento migrate:make --update-from-page=page_identifier --module=SomethingDigital_MigrationProject CreateFancyPage

    php bin/magento migrate:make --create-from-block=home-page-block --module=SomethingDigital_MigrationProject HomePageBlockContentLoad
    
    magento migrate:make --update-from-block=home-page-block --module=SomethingDigital_MigrationProject UpdateHomePageBlockStyling

## Custom Bluefoot Block Migrations

    bin/magento migrate:make --module=SomethingDigital_BluefootProject CreateAbsoluteLogoWithBorderBlock
