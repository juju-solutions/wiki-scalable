# A scalable Mediawiki bundle

This bundle deploys a Mediawiki, with MariaDB. Unlike the the wiki-simple bundle, this one is designed for scalability out of the box by using memcached for mediawiki and putting the entire thing behind an haproxy.

# Usage

You can deploy the single bundle with:

    juju deploy wiki-scalable

After deployment you need to expose the Mediawiki service, either via the GUI or the CLI:

    juju expose loadbalancer

Then run a `juju status loadbalancer` to get the public address. The browse to that address in your browser to configure and use the wiki.

## Scale out usage

You can add and remove more mediawiki instances to horizontally scale:

    juju add-unit wiki 

This can be done without service interruption.
