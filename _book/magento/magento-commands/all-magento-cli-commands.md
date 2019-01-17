# All Magento Cli Commands

Available commands:
      configurator                             List configurator commands
      help                                     Displays help for a command
      list                                     Lists commands
     admin
      admin:user:create                        Creates an administrator
      admin:user:unlock                        Unlock Admin Account
     app
      app:config:dump                          Create dump of application
      app:config:import                        Import data from shared configuration files to appropriate data storage
      app:config:status                        Checks if config propagation requires update
     cache
      cache:clean                              Cleans cache type(s)
      cache:disable                            Disables cache type(s)
      cache:enable                             Enables cache type(s)
      cache:flush                              Flushes cache storage used by cache type(s)
      cache:status                             Checks cache status
     catalog
      catalog:images:resize                    Creates resized product images
      catalog:product:attributes:cleanup       Removes unused product attributes.
     config
      config:sensitive:set                     Set sensitive configuration values
      config:set                               Change system configuration
      config:show                              Shows configuration value for given path. If path is not specified, all saved values will be shown
     configurator
      configurator:list                        List configurator components
      configurator:run                         Run configurator components
     cron
      cron:install                             Generates and installs crontab for current user
      cron:remove                              Removes tasks from crontab
      cron:run                                 Runs jobs by schedule
     cronmanager
      cronmanager:runjob                       Run a specific cron job by its job_code
      cronmanager:showjobs                     Show all cron job codes in Magento
     customer
      customer:hash:upgrade                    Upgrade customer's hash according to the latest algorithm
     deploy
      deploy:mode:set                          Set application mode.
      deploy:mode:show                         Displays current application mode.
     dev
      dev:di:info                              Provides information on Dependency Injection configuration for the Command.
      dev:profiler:disable                     Disable the profiler.
      dev:profiler:enable                      Enable the profiler.
      dev:query-log:disable                    Disable DB query logging
      dev:query-log:enable                     Enable DB query logging
      dev:source-theme:deploy                  Collects and publishes source files for theme.
      dev:template-hints:disable               Disable frontend template hints. A cache flush might be required.
      dev:template-hints:enable                Enable frontend template hints. A cache flush might be required.
      dev:tests:run                            Runs tests
      dev:urn-catalog:generate                 Generates the catalog of URNs to *.xsd mappings for the IDE to highlight xml.
      dev:xml:convert                          Converts XML file using XSL style sheets
     fastly
      fastly:conf:get                          Enables Fastly as Full Page Cache Caching Application
      fastly:conf:set                          Enables Fastly as Full Page Cache Caching Application
      fastly:format:jsontoserialize            Converts Module JSON data to serialized format
      fastly:format:serializetojson            Converts Module Serialized data to Json format
      fastly:vcl:generate                      DEPRECATED: Generates Fastly VCL and echos it to the command line
     i18n
      i18n:collect-phrases                     Discovers phrases in the codebase
      i18n:pack                                Saves language package
      i18n:uninstall                           Uninstalls language packages
     indexer
      indexer:info                             Shows allowed Indexers
      indexer:reindex                          Reindexes Data
      indexer:reset                            Resets indexer status to invalid
      indexer:set-mode                         Sets index mode type
      indexer:show-mode                        Shows Index Mode
      indexer:status                           Shows status of Indexer
     info
      info:adminuri                            Displays the Magento Admin URI
      info:backups:list                        Prints list of available backup files
      info:currency:list                       Displays the list of available currencies
      info:dependencies:show-framework         Shows number of dependencies on Magento framework
      info:dependencies:show-modules           Shows number of dependencies between modules
      info:dependencies:show-modules-circular  Shows number of circular dependencies between modules
      info:language:list                       Displays the list of available language locales
      info:timezone:list                       Displays the list of available timezones
      info:unirgy:list-modules                 List installed licenses
     maintenance
      maintenance:allow-ips                    Sets maintenance mode exempt IPs
      maintenance:disable                      Disables maintenance mode
      maintenance:enable                       Enables maintenance mode
      maintenance:status                       Displays maintenance mode status
     migrate
      migrate:make                             Generate a migration class file.
      migrate:retry                            Re-execute the last migration.
     module
      module:disable                           Disables specified modules
      module:enable                            Enables specified modules
      module:status                            Displays status of modules
      module:uninstall                         Uninstalls modules installed by composer
     msp
      msp:security:admin_restriction:ip        Set IP Admin Restriction
      msp:security:recaptcha:disable           Disable backend reCaptcha
      msp:security:tfa:disable                 Globally disable two factor auth
      msp:security:tfa:providers               List all available providers
      msp:security:tfa:reset                   Reset configuration for one user
     newrelic
      newrelic:create:deploy-marker            Check the deploy queue for entries and create an appropriate deploy marker.
     queue
      queue:consumers:list                     List of MessageQueue consumers
      queue:consumers:start                    Start MessageQueue consumer
     sampledata
      sampledata:deploy                        Deploy sample data modules
      sampledata:remove                        Remove all sample data packages from composer.json
      sampledata:reset                         Reset all sample data modules for re-installation
     sd
      sd:dev:static                            Generate static symlinks.
      sd:dev:unvirtual                         Set themes to physical.
      sd:dev:virtual                           Set themes to virtual.
     setup
      setup:backup                             Takes backup of Magento Application code base, media and database
      setup:config:set                         Creates or modifies the deployment configuration
      setup:cron:run                           Runs cron job scheduled for setup application
      setup:db-data:upgrade                    Installs and upgrades data in the DB
      setup:db-schema:add-slave                Move checkout quote related tables to a separate DB server
      setup:db-schema:split-quote              Move checkout quote related tables to a separate DB server
      setup:db-schema:split-sales              Move sales related tables to a separate DB server
      setup:db-schema:upgrade                  Installs and upgrades the DB schema
      setup:db:status                          Checks if DB schema or data requires upgrade
      setup:di:compile                         Generates DI configuration and all missing classes that can be auto-generated
      setup:install                            Installs the Magento application
      setup:performance:generate-fixtures      Generates fixtures
      setup:rollback                           Rolls back Magento Application codebase, media and database
      setup:static-content:deploy              Deploys static view files
      setup:store-config:set                   Installs the store configuration. Deprecated since 2.2.0. Use config:set instead
      setup:uninstall                          Uninstalls the Magento application
      setup:unirgy:add-license                 Add Unirgy license
      setup:unirgy:check-updates               Check for module updates
      setup:unirgy:update-reinstall            Update - reinstall unirgy modules
      setup:upgrade                            Upgrades the Magento application, DB data, and schema
     store
      store:list                               Displays the list of stores
      store:website:list                       Displays the list of websites
     support
      support:backup:code                      Create Code backup
      support:backup:db                        Create DB backup
      support:utility:check                    Check required backup utilities
      support:utility:paths                    Create utilities paths list
     theme
      theme:uninstall                          Uninstalls theme
     varnish
      varnish:vcl:generate                     Generates Varnish VCL and echos it to the command line
     webjump
      webjump:abib2b:import-invoices           Import invoices
      webjump:abib2b:import-orders             Import Orders orders
      webjump:abib2b:import-products           Import Products