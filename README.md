# SuperShaper-SOHO

SuperShaper-SOHO is a traffic shaping setup for DSL connections which
prioritizes VoIP and interactive traffic, and makes sure P2P traffic doesn't
saturate your uplink.

## Requirements

 * iproute2 (tc command)
 * Linux kernel with support for HTB and fq_codel schedulers

Ubuntu 14.04 is known to work and is the author's primary development
platform. It's been in daily use by the author for a number of years.

## Installation

Modify the variables on top of `supershaper.init` and copy this file to
`/etc/init.d/supershaper`.  Make sure that the file has executable bits set.
Then make sure it starts up automatically at startup.

On Ubuntu this is usually done like this:

    $ sudo cp supershaper.init /etc/init.d/supershaper
    $ sudo chmod 0755 /etc/init.d/supershaper
    $ sudo update-rc.d supershaper defaults

If you're using a PPP-based connection you might also want to ensure it is
started every time your connection is established by symlinking it into
`/etc/ppp/ip-up.d/`.

On Ubuntu this is usually done like this:

    $ sudo ln -sf /etc/init.d/supershaper /etc/ppp/ip-up.d/supershaper

## Support

If you require support for this product or have other contracting
assignments, please contact the author directly via email.

## Author, copyright and license

See the main script and the file LICENSE for details.
