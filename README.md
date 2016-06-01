# Monitor::Monit

Provide an interface to the monit monitoring daemon

## Synopsis

```perl6

use Monitor::Monit;

# use default settings
my $mon = Monitor::Monit.new;

for $mon.service -> $service {
	say $service.name, " is ", $sevice.status-name;
}

```

## Description

Monit is a lightweight, relatively simple and widely used system
and application monitoring service.

This provides a mechanism to interact with its http api.

## Installation

In order for this to be useful you will need to have 'monit' installed,
most Linux distributions provide it as a package.

The tests will attempt to connect to a monit daemon on the local host
with the default port and credentials, if there is no connection then
the online tests will be skipped.

You can provide the details for the running monit daemon you want to test
with by setting some environment variables before running the tests:

   * ```MONIT_TEST_HOST```  - the hostname on which the daemon is running
   * ```MONIT_TEST_PORT```  - the port the daemon is using (default 2812)
   * ```MONIT_TEST_USER```  - the username to authenticate (default ```admin```)
   * ```MONIT_TEST_PASS```  - the password to authenticate (default ```monit```)

Additionally, if the environment variable ```MONIT_TEST_CONTROL``` is set to
a true value, the tests will attempt to control the services, you probably don't
want to do this on a production system.

Assuming you have a working Rakudo Perl 6 installation then you should be able
to install with either ```panda``` or ```zef``` depending on your preference:

   panda install Monitor::Monit

or

   zef install Monitor::Monit

Other installers may become available in the future.

## Support

I've only tested this against my particular configuration of monit so it is
entirely possible that I have missed something that is important to you,
please feel to make suggestions at https://github.com/jonathanstowe/Monitor-Monit/issues

## Copyright and Licence

This is free software.

Please see the [LICENCE](LICENCE) file in this directory.

© Jonathan Stowe 2016
