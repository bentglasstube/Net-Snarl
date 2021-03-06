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

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies
of the Software, and to permit persons to whom the Software is furnished to do
so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
