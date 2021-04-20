---
title: File permissions readiness check issues
labels: File,Magento Commerce,Magento Commerce Cloud,check,how to,permissions,readiness,web setup wizard
---

This article provides a fix for file permissions readiness check issues. Directories in the Magento file system must be writable by the web server user and the Magento file system owner, if applicable. An error similar to the following displays in the Web Setup Wizard if your permissions are not set properly:

![install_rc_file-perms.png](https://support.magento.com/hc/article_attachments/360039636431/install_rc_file-perms.png)

The way you resolve the issue depends on whether you have a one-user or two-user setup:

* _One user_ means you log in to the Magento server as the same user that also runs the web server. This type of setup is common in shared hosting environments.
* _Two users_ means you typically _cannot_ log in as, or switch to, the web server user. You typically log in as one user and run the web server as a different user. This is typical in private hosting or if you have your own server.

### One-user resolution

If you have command-line access, enter the following command assuming Magento is installed in `` /var/www/html/magento2 ``:

<pre><code class="language-bash">$ cd /var/www/html/magento2 &amp;&amp; find var vendor pub/static pub/media app/etc -type f -exec chmod g+w {} + &amp;&amp; find var vendor pub/static pub/media app/etc -type d -exec chmod g+w {} + &amp;&amp; chmod u+x bin/magento</code></pre>

If you do not have command-line access, use an FTP client or a file manager application provided by your hosting provider to set permissions.

### Two-user resolution

To optionally enter all commands on one line, enter the following assuming Magento is installed in `` /var/www/html/magento2 `` and the web server group name is `` apache ``:

<pre><code class="language-bash">$ cd /var/www/html/magento2 &amp;&amp; find var vendor pub/static pub/media app/etc -type f -exec chmod g+w {} + &amp;&amp; find var vendor pub/static pub/media app/etc -type d -exec chmod g+ws {} + &amp;&amp; chown -R :apache . &amp;&amp; chmod u+x bin/magento</code></pre>

In the event file system permissions are set improperly and can't be changed by the Magento file system owner, you can enter the command as a user with `` root `` privileges:

<pre><code class="language-bash">$ cd /var/www/html/magento2 &amp;&amp; sudo find var vendor
  pub/static pub/media app/etc -type f -exec chmod g+w {} + &amp;&amp; sudo find
  var vendor pub/static pub/media app/etc -type d -exec chmod g+ws {} + &amp;&amp;
  sudo chown -R :apache . &amp;&amp; sudo chmod u+x bin/magento</code></pre>