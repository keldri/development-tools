# Setup Upgrade

## Run setup upgrade and generate symlinks for static files

    php bin/magento setup:upgrade
    
    // Generate static symlinks for theme
    php bin/magento sd:dev:static ThemeName/default
    
    // Generate static symlinks for admin
    php bin/magento sd:dev:static --area=adminhtml Magento/backend

## To run setup upgrade and not run sd:dev:static (keeps symlinks)

    php bin/magento setup:upgrade --keep-generated