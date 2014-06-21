NAME
    netdiff - A simple script to diff a file or a directory of two hosts
    over the network.

    This is very helpful if you want to find out any difference of these two
    hosts.

  SYNOPSYS
      netdiff HOSTNAME PATH [PORT] [ADDITIONAL DIFF OPTS]

  USAGE
    Cluster-SSH into two hosts at the same time and run on both hosts the
    same (simultaneous):

        netdiff HOSTNAME PATH

    Where HOSTNAME can be the hostname of the first or the second host.
    Depending on this the script will decide to be the client or the server
    role.

    And where PATH musst be a full qualified path to a file or a directory.

    Netdiff transfers everything in PATH (recursively and encrypted via
    OpenSSL/AES) to the other host and computes a diff of it.

    If no port is specified the default port will be used, which is defined
    in

      /etc/default/netdiff

  EXAMPLE
    A common use case is to find out the differences of the PAM
    configuration. On most systems the PAM configuration is spread into
    several small configuration files which are hard to compare by hand
    between two hosts.

    Given two hosts one.example.com and two.example.com. Just run this
    command on both hosts:

      netdiff one.example.com /etc/pam.d

    The same affect, but the other way around would be the following
    command:

      netdiff two.example.com /etc/pam.d

LICENSE
    See package description or project website.

AUTHOR
    Paul Buetow - <http://netdiff.buetow.org>

