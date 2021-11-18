#### This page outlines the required and optional variables in group_vars/all.yml.

See [Sample Inventories](https://github.com/HCL-TECH-SOFTWARE/connections-automation/tree/main/environments/examples) where some of these variables are used.
## Table of contents

[LDAP Variables](https://github.com/HCL-TECH-SOFTWARE/connections-automation/tree/main/documentation/VARIABLES.md#ldap-variables)

[Database Variables](https://github.com/HCL-TECH-SOFTWARE/connections-automation/tree/main/documentation/VARIABLES.md#database-variables)

[DB2 Variables](https://github.com/HCL-TECH-SOFTWARE/connections-automation/tree/main/documentation/VARIABLES.md#db2-variables)

[Oracle Variables](https://github.com/HCL-TECH-SOFTWARE/connections-automation/tree/main/documentation/VARIABLES.md#oracle-variables)

[MSSQL Variables](https://github.com/HCL-TECH-SOFTWARE/connections-automation/tree/main/documentation/VARIABLES.md#mssql-variables)

[WebSphere Variables](https://github.com/HCL-TECH-SOFTWARE/connections-automation/tree/main/documentation/VARIABLES.md#websphere-variables)

[IHS Variables](https://github.com/HCL-TECH-SOFTWARE/connections-automation/tree/main/documentation/VARIABLES.md#ihs-variables)

[IIM Variables](https://github.com/HCL-TECH-SOFTWARE/connections-automation/tree/main/documentation/VARIABLES.md#iim-variables)

[SDI Variables](https://github.com/HCL-TECH-SOFTWARE/connections-automation/tree/main/documentation/VARIABLES.md#sdi-variables)

[Connections Variables](https://github.com/HCL-TECH-SOFTWARE/connections-automation/tree/main/documentation/VARIABLES.md#connections-variables)

[Docs Variables](https://github.com/HCL-TECH-SOFTWARE/connections-automation/tree/main/documentation/VARIABLES.md#docs-variables)

[Component Pack Infra Variables](https://github.com/HCL-TECH-SOFTWARE/connections-automation/tree/main/documentation/VARIABLES.md#component-pack-infra-variables)

### LDAP Variables
Name | Default | Description
---- | --------| -------------
setup_fake_ldap_users | true | true creates dummy ldap users
ldap_bind_pass | password | Password for simple authentication
ldap_realm | dc=cnx,dc=pnp-hcl,dc=com | This directive specifies the DN suffix of queries that will be passed to this backend database
ldap_admin_user | Admin | Ldap admin user
ldap_nr_of_users | 2500 | Ldap number of users to be created
ldap_userid | jjones | User id for the ldap users. It is postfixed with the user number. e.g. with default ldap_userid as 'jjones', user1 will be created with user id - jjones1
ldap_user_password | password | Password for the ldap users
ldap_user_admin_password | password | Ldap user admin password
ldap_user_mail_domain | connections.example.com | Ldap user email domain
ldap_setup_internal | false | true sets up internal users

### Database Variables
Name | Default | Description
---- | --------| -------------
db_type | DB2 | Database type to be passed to the Connections installer
db_username | LCUSER | Database user to be passed to the Connections installer
db_password | password | Database user password to be passed to the Connections installer
db_port | 50000 | TCP/IP service port
db_hostname | *none* - required | Database hostname
db_jdbc_file | /opt/IBM/db2/V11.1/java | Database JDBC driver path

### DB2 Variables
Name | Default | Description
---- | --------| -------------
db2_download_location | *none* - required | DB2 install kit location to download
setup_db2_jdbc | false | true will install jdbc drivers to WAS nodes
db2_user | db2inst1 | DB2 Instance owner
db2_installation_folder | /opt/IBM/db2/V11.1 | DB2 installation folder path
db2_instance_homedir | /home/db2inst1 | DB2 Instance owner home directory
db2_package_name | v11.1.4fp5_linuxx64_universal_fixpack.tar.gz | DB2 package name
db2_license_file | CNB23ML.zip | DB2 license file name
db2_instance | inst1 | logical Database Manager environment for DB2
db2_instance_type | ese | DB2 instance type
db2_instance_group | db2group | DB2 instance group
db2_instance_homedir | /home/db2inst1 | DB2 instance home directory
db2_instance_autostat | YES |  True will enable the DB2 database instance for automatically start
db2_instance_svcname | db2c_db2inst1 | DB2 instance service name
db2_instance_port | 50000 | TCP/IP service port
db2_instance_fcm_port | 60000 | port used by the Fast Communications Manager
db2_instance_max_lnodes | 6 | Maximum node counts
db2_instance_text_search | NO | Yes configures integrated Db2 Text Search server
db2_instance_fenced_user | db2fenc1 | Fenced user to run user defined functions (UDFs) and stored procedures outside of the address space used by the Db2 database
db2_instance_fenced_group | db2group | Fenced user group
db2_instance_fenced_homedir | /home/db2fenc1 | Fenced user home directory
db2_instance_default_lang | EN | DB2 instance default language
install_latest_db2 | false | true will install IBM DB2 v11.5.6 and false will install IBM DB2 v11.1

### Oracle Variables
Name | Default | Description
---- | --------| -------------
oracle_download_location | *none* - required | Oracle database download location
setup_oracle_jdbc | false | true will install jdbc drivers to WAS nodes
ora_rsp_oracle_base | /opt/oracle | Oracle database base location
ora_rsp_oracle_home | /opt/oracle/product/19.0.1/db_1 | Oracle database home location
ora_rsp_starter_db_name | LSCONN | Global Database Name
oracle_package_name | LINUX.X64_193000_db_home.zip | Installer package name
ora_rsp_install_option | INSTALL_DB_AND_CONFIG | The installation option can be - INSTALL_DB_SWONLY, INSTALL_DB_AND_CONFIG, UPGRADE_DB
ora_rsp_unix_group_name | oinstall | Provide values for the OS groups to which OSDBA privileges needs to be granted
ora_rsp_inventory_location | /opt/oracle | 
ora_rsp_data_location | default( '/opt/oracle/data' ) | Database file location: directory for datafiles, control files, redo logs
ora_rsp_data_rcvry_location | default( '/opt/oracle/recovery' ) | Backup and recovery location
ora_rsp_install_edition | EE | Installation Edition of the component e.g. EE : Enterprise Edition, SE : Standard Edition, SEONE : Standard Edition One, PE : Personal Edition (WINDOWS ONLY)
ora_rsp_exec_root_script | false | true for automatic root script execution
ora_rsp_root_config_method | SUDO | Specify the configuration method to be used for automatic root script execution
ora_rsp_starter_db_type | GENERAL_PURPOSE | Starter database type - GENERAL_PURPOSE, TRANSACTION_PROCESSING, DATAWAREHOUSE
ora_rsp_starter_db_name | LSCONN | Starter database name
ora_rsp_starter_charset | AL32UTF8 | Database character set
ora_rsp_use_auto_mem_mgmt | false | true means use auto memory management
ora_rsp_auto_mem_limit | 2048 | Specify the total memory allocation for the database
ora_rsp_enable_recovery | true | true means enable recovery
ora_rsp_storage_type | FILE_SYSTEM_STORAGE | Storage type can be - FILE_SYSTEM_STORAGE, ASM_STORAGE
oracledb_exporter_version | oracledb_exporter.0.3.0rc1-ora18.5.linux-amd64 | Oracle database exporter version
oracledb_exporter_release | 0.3.0rc1 | Binary release version
oracledbexp_extraction_folder | /home/oracle | Oracle database exporter extraction folder path
oracle_bashrc_file_path | /home/oracle/.bashrc | bashrc file path
metrics_port | 9161 | Port to get metrics from the Oracle database
oracledb_port | 1521 | TCP/IP service port

### MSSQL Variables
Name | Default | Description
---- | --------| -------------
setup_mssql_jdbc | false | true will install jdbc drivers to WAS nodes
mssql_sa_password | Pa55w0rd | MSSQL user specified password
mssql_accept_eula | Y | Y confirm your acceptance of the End-User Licensing Agreement
mssql_pid | evaluation | Set the SQL Server edition or product key. Possible values include: Evaluation, Developer, Express, Web, Standard, Enterprise
mssql_jdbc_installation_folder | /opt/mssql/jdbc/lib | MSSQL installation folder path
mssql_jdbc_package_name | sqljdbc_6.0.8112.200_enu.tar.gz | MSSQL package name
mssql_jdbc_tdi_enable | true | true downloads legacy drivers for TDI JRE
mssql_create_admin_user | true | true creates extra admin user for MSSQL
upgrade_tdi_jre | false | true upgrades jre

### WebSphere Variables
Name | Default | Description
---- | --------| -------------
was_repository_url | *none* - required | WebSphere install kit download location
was_fixes_repository_url | *none* - required | WebSphere Fix Pack kit location to download
was_version | 8.5.5000.20130514_1044 | WebSphere Base version
was_fp_version | 8.5.5019.20210118_0346 | WebSphere Fix Pack version
java_version | 8.0.6015.20200826_0935 | (only for Java upgrade during FP16/18 install)
was_username | wasadmin | WAS admin user
was_password | password | WAS admin user password
was_install_location | /opt/IBM/WebSphere/AppServer | WebSphere program folder
dmgr_hostname | *none* - required | Deployment Manager hostname, typically `{{ hostvars[groups['db_servers'][0]]['inventory_hostname'] }}`
dmgr_soap_port | 8879 | Deployment Manager soap port


### IHS Variables
Name | Default | Description
---- | --------| -------------
ihs_repository_url | *none* - required | IHS install kit download location
ihs_fixes_repository_url | *none* - required | IHS Fix Pack kit location to download
ihs_version | 8.5.5019.20210118_0346 | IHS Fix Pack version
ihs_username | ihsadmin | IHS admin user
ihs_password | *none* - required | IHS admin user password


### IIM Variables
Name | Default | Description
---- | --------| -------------
iim_repository_url | *none* - required | IIM install kit download location
tmp_dir | /opt/IBM/Binaries | Folder to extract installation kits
iim_install_location | /opt/IBM/InstallationManager | IIM program folder
imshared_location | /opt/IBM/IMShared | IIM config folder
iim_bin_file | agent.installer.linux.gtk.x86_64_1.9.1003.20200730_2125.zip | IIM program zip
iim_version | 1.9.1003.20200730_2125 | IIM version
iim_keep_fetched_files | false | IIM var, true will keep downloaded files if error occurs
iim_preserve_artifacts | false | IIM var, true will keep the files that are required to run uninstall


### SDI Variables
Name | Default | Description
---- | --------| -------------
tdi_download_location | *none* - required | SDI install kit download location
tdi_package_name | SDI_7.2_XLIN86_64_ML.tar | SDI install kit file
tdi_user_install_dir | /opt/IBM/TDI/V7.20 | SDI program folder
tdi_upgrade_enable | true | Enable SDI FP install
tdi_upgrade_package_name | 7.2.0-ISS-SDI-FP0006.zip | SDI FP install kit file
tdi_upgrade_package_bin | SDI-7.2-FP0006.zip | SDI FP file to provide to installer
tdi_upgrade_package_folder_name | 7.2.0-ISS-SDI-FP0006 | Folder that stores tdi_upgrade_package_bin
tdi_cs_port | 1527 | SDI Derby server port
cnx_updates_enabled | false | true will download `{{ cnx_package }}` (i.e. Connections install kit) again to get the tdisol from there
upgrade_tdi_jre | false | Enable upgrade to SDI JRE 8 (need a separate 6.5CR1 or 7.0 tdisol kit)
tdi_sol_location | /opt/IBM/InstallBinaries/CNX/HCL_Connections_Install/tools/tdisol.tar | path to the tdisol tar to use if not the one from `{{ cnx_package }}` (eg. when upgrade_tdi_jre=true)
jre_package_version | ibm-java-x86_64-80 | JRE package version, used when upgrade_tdi_jre=true
jre_package_name | ibm-java-jre-8.0-5.30-linux-x86_64.tgz | JRE package file, used when upgrade_tdi_jre=true
db_jdbc_file | /opt/IBM/db2/V11.1/java or /opt/IBM/db2/V11.5/java | DB2 JDBC driver folder
oracle_jdbc_location | /opt/oracle | Oracle JDBC driver folder
mssql_jdbc_location | /opt/mssql/jdbc/lib/sqljdbc_4.1/enu/jre7 or /opt/mssql/jdbc/lib/sqljdbc_6.0/enu/jre8 | MSSQL JDBC driver folder


### Connections Variables
Name | Default | Description
---- | --------| -------------
cnx_repository_url | *none* - required | Connections install kit download location
connections_wizards_download_location | *none* - required | Connections Wizard install kit location to download
cnx_package | HCL_Connections_7.0_lin.tar | Connections install kit file
connections_wizards_package_name | HCL_Connections_7.0_wizards_lin_aix.tar | Connections Wizard kit file
setup_connections_wizards | true | true will run the Connections database wizard
cnx_major_version | "7" | Connections major version to install
cnx_fixes_version | *none* - optional | If defined (eg. 6.5.0.0_CR1) will install the CR version
cnx_fixes_files | *none* - optional | If defined (eg. HC6.5_CR1.zip") and cnx_fixes_version is set, will download the CR install kit
cnx_application_ingress | *none*  - required | Set as *dynamicHosts* in LotusConnections-config.xml
connections_admin | jjones1 | User to be passed to the Connections installer as admin user
connections_admin_password | password | password for Connections admin user
cnx_deploy_type | small | Connections deployment option (i.e. small/medium/large)
skip_nfs_mount_for_connections | false | false will setup NFS mount points for Connections data and message store
cnx_enable_invite | false | true will configure selfregistration-config.xml for Invite
cnx_enable_moderation | false | true will install and configure Moderation
global_moderator | *none* - optional | Global moderator user
cnx_enable_full_icec | false | true will configure full CEC
cnx_enable_lang_selector | false | true will enable and add additional lanaguages to the language selector
cnx_force_repopulation | false | true will drop the Connections databases and recreate them in `setup-connections-wizards.yml` playbook
cnx_updates_enabled | false | true will upgrade Connections if a new version is available in cnx_repository_url
db_version | "7.0" | Determines the set of databases to create/drop (eg. 7.0, 6.5)
cnx_db_updates_url | *none* - required for 6.5CR1 with DB2 | database schema upgrade zip download location (6.5 CR1 only)
cnx_db_update_file | 65cr1-database-updates.zip | File name to download for database schema upgrade (6.5 CR1 only)
db_type | DB2 | Database type to be passed to the Connections installer
db_username | LCUSER | Database user to be passed to the Connections installer
db_password | password | Database user password to be passed to the Connections installer
db_port | 50000 | Database user password to be passed to the Connections installer
smtp_hostname | *none* - required | <for future use, you can set it to *localhost*>
ifix_apar | *none* - required when install Connections fix | APAR number of fix 
ifix_file | *none* - required when install Connections fix | fix file name from `{{ cnx_repository_url }}`
cnx_ifix_installer | updateInstaller.zip | updateInstaller file to download from `{{ cnx_repository_url }}`
cnx_ifix_backup | yes | -featureCustomizationBackedUp option to be provided to the updateInstaller
restrict_reader_access | *none* - optional | true will set application roles to All Authenticated in Application's Realm when running the `connections-restrict-access.yml` playbook
restrict_reader_access__trusted_realms | *none* - optional | true will set application roles to All Authenticated in Trusted Realm when running the `connections-restrict-access.yml` playbook 

### Docs Variables
Name | Default | Description
---- | --------| -------------
cnx_docs_download_location | *none* - required | Connections Docs kit download location
cnx_docs_package_name | IBMConnectionsDocs_2.0.1.zip | Connections Docs install kit file
hcl_program_folder | /opt/HCL | Location to store Docs program folders
conversion_install_folder | DocsConversion | Conversion program folder name
editor_install_folder | DocsEditor | Editor program folder name
viewer_install_folder | DocsViewer | Viewer program folder name
proxy_install_folder | DocsProxy | Docs Proxy program folder name
setup_connections_docs | false | true will run the Connections Docs database setup in `setup-connections-wizards.yml` playbook 
docs_username | docsuser | Docs database user
docs_password | *none* - required | Password for the user to be created for job target creation
sudo_group | *none* - required | Group for the user to be created for job target creation
nfs_docs_setup | true | true will create the NFS mount points for Connections data, Docs and Viewer data, must be true if `skip_nfs_mount_for_connections` is false (default)
conversion_cluster_name | HCLConversionCluster | Conversion cluster name
editor_cluster_name | HCLEditorCluster | Docs cluster name
viewer_cluster_name | HCLViewerCluster | Docs Viewer cluster name
docs_proxy_cluster_name | HCLDocsProxyCluster | Docs Proxy cluster name
db_concord_username | DOCSUSER | Docs database user
db_concord_password | *none* - required | Docs database user password
cnx_docs_force_repopulation | false | true will drop the Docs databases and recreate it in setup-connections-wizards.yml playbook
docs_url  | *none* - required | Docs frontend hostname, typically the same as `{{ cnx_application_ingress }}`
docs_shared_storage_type | nfs | Set to `nfs` if Docs data is a NFS share, `local` if it is a local directory
docs_data_remote_path | /nfs/docs_data| NFS share of Docs data dir, `{{ docs_shared_storage_type }}` must be nfs to use it
docs_data_local_path | /mnt/docs_data | path of local location to Docs data dir, if `{{ docs_shared_storage_type }}` is `nfs`, `{{ docs_data_remote_path }}` will mount to this directory
viewer_shared_storage_type | nfs | Set to `nfs` if Docs Viewer data is a NFS share, `local` if it is a local directory
viewer_data_remote_path | /nfs/viewer_data | NFS share of Docs Viewer data dir, `{{ viewer_shared_storage_type }}` must be nfs to use it
viewer_data_local_path | /mnt/viewer_data | path of local location to Docs Viewer data dir, if `{{ viewer_shared_storage_type }}` is `nfs`, `{{ viewer_data_remote_path }}` will mount to this directory
cnx_shared_storage_type | nfs | Set to `nfs` if Connections data is a NFS share to the Docs server, `local` if it is a local directory
cnx_data_remote_path | /nfs/data/shared | NFS share of Connections data dir, `{{ cnx_shared_storage_type }}` must be `nfs` to use it
cnx_data_local_path | /mnt/cnx_data | path of local location to Connections data dir, if `{{ cnx_shared_storage_type }}` is `nfs`, `{{ cnx_data_remote_path }}` will mount to this directory
cnx_data_path_on_cnx_server | /opt/IBM/SharedArea | local path of Connections data on the Connections server (i.e. where Docs extensions will be installed)

### Component Pack Infra Variables
Name | Default | Description
---- | --------| -------------
containerd_version | 1.4.4-3.1.el7 | Containerd version to be installed
docker_version | 19.03.15-3.el7 | Docker version to be installed
registry_port | 5000 | The registry defaults to listening on port 5000
setup_docker_registry | true | true sets up docker registry
docker_registry_url | {{ hostvars[groups['docker_registry'][0]]['inventory_hostname'] }}:5000 | Docker Registry url
registry_user | admin | Docker Registry user name
registry_password | password | Docker Registry user password
overlay2_enabled | true | true enables OverlayFS storage driver
kubernetes_version | 1.19.11 | Kubernetes version to be installed
kube_binaries_install_dir | /usr/bin | kuberneters binary install directory
kube_binaries_download_url | https://storage.googleapis.com/kubernetes-release/release | kuberneters binary download path
load_balancer_dns | localhost | Specify a DNS name for the control plane.
pod_subnet | 192.168.0.0/16 | Specify range of IP addresses for the pod network. If set, the control plane will automatically allocate CIDRs for every node.
kubectl_user |  ansible_env['SUDO_USER'] | Kubectl is setup for all the users listed here
calico_version | 3.11 | Calico version to be installed
calico_install_latest | true | true installs/Upgrades Calico to the latest version
helm_version | 3.6.1 | Helm version to be installed

### NFS Variables
Name | Default | Description
---- | --------| -------------
preserve_nfs_data | true | true will preserve NFS data


