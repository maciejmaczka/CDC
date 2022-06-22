# CDC
 Check Point Diagnostic Console


About

 

CDC is set of scripts that allows to show CKP parameters, do some simple configuration and do debugs. Scirpts are organized in following way:

 

<action>_<place>_<module>_<info>

 

where:

action:

    show - show CKP parameters
    config - change something
    debug - start/stop, show debug, test something, show logs

 

 

place:

    MGMT - scripts for Management
    Gateway - scripts for Gateway
    General - GAIA

 

module:

    Corexl
    SecureXL
    Threat Prevention
    and other stuff

 

info:

    enable - start debug
    show - show debug
    other - no rules here. Just to kepp is simple

 

 

How to use it:

 

======================== GENERAL ==============================

 

(go to directory)

cd cdc

 

(run command)

./show_gateway_firewall_interface_drop

 

Hint: Use tab to finish command or to show commands available.

 

 

======================== SHOW COMMANDS ==============================

 

To see all commands  available run:   ls

To search for specific command:   ls  | grep module.  

 

For example:

[Expert@te:0]# ls | grep securexl
config_gateway_securexl_disable
config_gateway_securexl_enable
debug_gateway_securexl_errors_enable
debug_gateway_securexl_show
show_gateway_securexl_connections
show_gateway_securexl_connections_summary
...

 

You can alse use  search here:

http://epg.org.pl/cdc/reference.php?search= 

 

 

======================== SHOW ==============================

 

All commands start with "show"

 

[Expert@te:0]# ./show_mgmt_manager_status
Check Point Security Management Server is running and ready

 

======================== DEBUG ==============================

 

All commands start with "debug"

 

To start debug:

Most debugs require 3 commands: enable, show, disable_debug. Some only show.

 

For example:

./debug_gateway_ssl_inspect_related_enable

 

 

This will start debug of ssl inspect module. All kernel variable will be set for you. After that, what to do next message will be presented:

 

---------------------------------------------------------------------------

 

 Usage:
 debug_gateway_ssl_inspect_show | grep <options>

 

 debug_gateway_debug_disable to turn off debug!

 

 TIPS:
 | grep CN   - to check certificate CN processed by SSL Inspect
 | grep domain - to check search for specific domain
 Check log number. Use grep -A 10 -B 10

 

 ---------------------------------------------------------------------------

 

 

To see debug in this example:

./debug_gateway_ssl_inspect_show

 

CTRL + C to break.

 

To disable debug

./debug_gateway_debug_disable

 

 

======================== CONFIG  ==============================

 

All commands start with "config"

 

[Expert@te:0]# ./config_gateway_identity_users_excluded_clear
Warning this will CLEAR excluded users list!!!
Do you wan't to continue? (Hit any key to continue. CTRL+C to exit)

 

The suspected service accounts list has been cleared.

 

 

There should be a message, what this command will do. You need to press Enter to continue.

 

 

 

====================== HOW TO INSTALL ===================================

 

In expert mode.

Go to directory where do you want to install. 
Extract archive

cd cdc
chmod 755 *
mkdir /var/log/cdc

 

========================== WHAT CAN YOU DO =============================

 

Everything Smiley Happy

 

You can share, edit, add / remove scirpts. Please, be so kind and share changes Smiley Happy. Internet access is not required. If you don't want to share changes just edit your scripts.

 
