# Things to check if static content missing 

## Things to check if static content missing

1. Are base_static_url & /base_media_url set correctly? Should match secure url  + static/ or media/ at the end.

Use correct permissions for apache with mod_php for the pub/static and var/ folders

    chmod -R 777 /path/to/magento2/pub/static /path/to/magento2/var –