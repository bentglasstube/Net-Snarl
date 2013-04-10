# NAME

Net::Snarl - Snarl network protocol

# SYNOPSIS

    use Net::Snarl;

    # connect to localhost and register Net::Snarl application
    my $snarl = Net::Snarl->register('Net::Snarl');
    $snarl->add_class('Test'); # add Test notification class
    $snarl->notify('Test', 'Hello', 'World', 5); # show hello world for 5 seconds

# DESCRIPTION

A simple interface to send Snarl notifications across the network.  Snarl must
be running on the target machine.

# INTERFACE

## register($application, $host, $port)

Connects to Snarl and register an application.  Host defaults to localhost and
port defaults to `$Net::Snarl::SNARL_PORT`.

## add\_class($class, $title)

Registers a notification class with your application.  Title is the optional
friendly name for the class.

## notify($class, $title, $text, $timeout, $icon)

Displays a notification of the specified class.  Timeout defaults to 0 (sticky)
and icon defaults to nothing.

# BUGS

Please report and bugs or feature requests on GitHub
[https://github.com/bentglasstube/Net-Snarl/issues](https://github.com/bentglasstube/Net-Snarl/issues)

# TODO

Later versions of Snarl report interactions with the notifications back to the
socket.  Currently these are stored in a private queue.  Eventually, I will
expose an interface for triggering callbacks on these events but that will most
likely require threading so I'm a little reluctant to implement it.

# AUTHOR

Alan Berndt, `<alan@eatabrick.org>`

# LICENSE AND COPYRIGHT

Copyright 2013 Alan Berndt.

This program is free software; you can redistribute it and/or modify it under
the terms of either: the GNU General Public License as published by the Free
Software Foundation; or the Artistic License.

See http://dev.perl.org/licenses/ for more information.


