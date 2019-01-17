# Mysql

- Change Core Config URLS

    ## Basic Commands to open Mysql and set DB to use

        //Open Mysql
        sudo mysql;
        
        // tell mysl to use the DB you want (typiclly magento_database)
        use <dbname>;

    ## Use Mysql query to see what base_urls are.

        
        /* Search core_config_data table for a row that has value like http
         This will show you the unsecure/base_url and secure/base_url amd if 
        base_url/static and base_url/media are set will show these too */
        
        select * from core_config_data where value like "%http%";
        
        // Search core_config_data for media urls
        select * from core_config_data where path like "%media%";
        
        // Search core_config_data for static urls
        select * from core_config_data where path like "%static%";

    ## Use Mysql query to update  base_urls are.

        // Updating the value to your website url
        // The config_id can be found by running the first command ina bove code block. You may need to change multiple rows (i.e. (163,4198,4207))
        update core_config_data set value="https://naturalvitality.test/" where config_id IN (163,4198,4207);
        
        update setup set value="https://magento.test/" where config_id IN (44,77);

    ## Use Mysql query to update  module schema_versions and data_versions if you run into an error after running setup upgrade

        
        update setup_module set schema_version='2.2.1', data_version='2.2.1' where module='IWD_StoreLocator';

---

- Update Module schema_versions and data_versions

        // ## Use Mysql query to update  module schema_versions and data_versions if you run into an error after running setup upgrade
        
        update setup_module set schema_version='2.1.0', data_version='2.1.0' where module='Amazon_Payment';
        
        update setup_module set schema_version='2.1.1', data_version='2.1.0' where module='Amazon_Payment';

---