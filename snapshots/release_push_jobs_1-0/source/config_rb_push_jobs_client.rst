

=====================================================
push-jobs-client.rb
=====================================================

A ``push-jobs-client.rb`` file is used to specify the configuration details for the Chef push jobs client.

* This file is loaded every time this executable is run
* This file is not created by default
* When a ``push-jobs-client.rb`` file is present in the default location, the settings contained within that file will override the default configuration settings

Settings
==========================================================================
This configuration file has the following settings:

``allow_unencrypted``
   Required for Chef push jobs client 2.0+ to be set to ``true``.

``chef_server_url``
   The URL for the Chef server. For example:

   .. code-block:: ruby

      https://localhost/organizations/ORG_NAME

``client_key``
   The location of the file that contains the client key. Default value: ``/etc/chef/client.pem``.

``node_name``
   The name of the node.

``ssl_verify_mode``
   Set the verify mode for HTTPS requests.

   * Use ``:verify_none`` to do no validation of SSL certificates.
   * Use ``:verify_peer`` to do validation of all SSL certificates, including the Chef server connections, S3 connections, and any HTTPS **remote_file** resource URLs used in the chef-client run. This is the recommended setting.

   Depending on how OpenSSL is configured, the ``ssl_ca_path`` may need to be specified. Default value: ``:verify_peer``.

``trusted_certs_dir``
   The location of trusted certificates. Default value: ``'/etc/chef/trusted_certs'``.

``whitelist``
   A Hash that contains the whitelist used by Chef push jobs. For example:

   .. code-block:: ruby

      whitelist {
        'job-name' => 'command',
        'job-name' => 'command',
        'chef-client' => 'chef-client'
      }
