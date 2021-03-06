![Mojo Poker Logo](/mojopoker-1.1.1/public/img/logo.png)

[![Build Status](https://api.travis-ci.com/nathanielgraham/Mojo-Poker.svg?branch=master)]

Mojo Poker is a web-based poker system that allows anyone to run their own private poker site.

## Features
Includes all the clasics plus a large selection of offbeat games: 
Hold'em, Hold'em Jokers Wild, Pineapple, Crazy Pineapple, Omaha, Omaha Hi-Lo, 5 Card Omaha, 5 Card Omaha Hi-Lo, Courcheval, Courcheval Hi-Lo, 5 Card Draw, 5 Card Draw Deuces Wild, 5 Card Draw Jokers Wild, 2-7 Single Draw, 2-7 Triple Draw, A-5 Single Draw, A-5 Triple Draw, 7 Card Stud, 7 Card Stud Jokers Wild, 7 Card Stud Hi-Lo, Razz, High Chicago, Follow the Queen, The Bitch, Badugi, Badacey, Badeucy, Dealer's Choice.

![SCREENSHOT](https://github.com/mojopoker/Mojo-Poker/blob/master/SCREENSHOT.png)

## Install
Tested on Ubuntu 16.04. Other distros might require tweaking.
Begin with a newly installed, "clean" install of Ubuntu 16.04.
Issue the following commands in your terminal session:

    cd /tmp
    git clone https://github.com/nathanielgraham/Mojo-Poker.git
    cd Mojo-Poker
    sudo ./install

## Starting the server
Issue the following command in your terminal session:

    sudo systemctl start mojopoker.service

Now point your browser at http://localhost:3000

## Creating new tables
To create a new six handed No-Limit Hold'em table for example, issue the following command:

    /opt/mojopoker/script/mpadmin.pl create_ring -game_class holdem -limit NL -chair_count 6

See mpadmin.pl --help for a complete list of options. 

## Admin tool
mpadmin.pl is a command-line ultility for creating and deleting ring games, editing player info, crediting chips, and other admin tasks.  For a complete list of options, type:

    sudo /opt/mojopoker/script/mpadmin.pl --help 

## Advanced websocket shell
wsshell.pl is a command-line utility for sending JSON encoded WebSocket messages directly to the server. Useful for automating certain tasks. To bulk load many games at once for example, issue the following command in your terminal session:

    sudo /opt/mojopoker/script/wsshell.pl < /opt/mojopoker/db/example_games

## Running in production
Additional steps to run a secure site:
- [ ] Facebook login feature won't work without a registered domain 
- [ ] Setup nginx as reverse proxy to provide SSL/TLS certificate
- [ ] Change admin password
- [ ] Add firewall for DDOS protection
- [ ] Anything else? 

See [Mojolicious::Guides::Cookbook](https://metacpan.org/pod/distribution/Mojolicious/lib/Mojolicious/Guides/Cookbook.pod). You can also contact me directly if you need additional support.

## Contact
Questions and bug reports to ngraham@cpan.org

## TODO 
- [ ] Add support for tournaments
- [ ] Change hand evaluator to [Poker::Eval](https://metacpan.org/pod/Poker::Eval)

## COPYRIGHT AND LICENSE
Copyright (C) 2019, Nathaniel J. Graham

This program is free software, you can redistribute it and/or modify it
nder the terms of the Artistic License version 2.0.
https://dev.perl.org/licenses/artistic.html
