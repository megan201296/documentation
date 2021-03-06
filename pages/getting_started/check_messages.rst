Check If You Have Messages
^^^^^^^^^^^^^^^^^^^^^^^^^^

Now that we've configured rsyslog, return to your browser and navigate to the *System / Inputs* page.

.. image:: /images/gs/input_page.png

Click on the *Show received messages* button next to the *appliance-syslog-udp* input.

BOOM! You should now see the messages received on this input from your syslog clients. For now it's just our one virtual machine, but imagine the possibilities!  Here's where the fun really starts!

.. image:: /images/gs_10-messages.png

*Skip the following section if you are all good.*

If You Don't Have Messages
^^^^^^^^^^^^^^^^^^^^^^^^^^
1.  Check to see that you made the proper entries in the rsyslog configuration file.

2.  Check the syslog UDP configuration and make sure that is right - remember we changed the default port to 514.

3.  Check to see if rsyslog messages are being forwarded to the port.  You can use the `tcpdump <http://manpages.ubuntu.com/manpages/xenial/en/man8/tcpdump.8.html>`_ command to do this:

``$ sudo tcpdump -i lo host 127.0.0.1 and udp port 514``

4.  Check to see if the server is listening on the host:

``$ sudo netstat -peanut | grep ":514"``

If you still have issues, connect to our `community support <https://www.graylog.org/community-support>`__ or get in touch with us via the `professional support offering <https://www.graylog.org/professional-support>`__.
