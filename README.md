#Another one...
Yes, it's repeating of [*tutorial*](http://railstutorial.ru/chapters/4_0/beginning#sec-the_first_application), 
than may founded.
What learns:
* Ruby on Rails
* RubyGem
* Git
* MarkDown (this list maked only for this)
* Postgresql

##SQLite3 migrate to Postgresql
I needed to change SQLite3 to Postgresql, but don't want immediately use
_rails new some2 --database=postgresql_.
I want get expirience of migration. It Sounds funny: i have no db. Just blank
files, that was initialized by _rails new some1_. But, when try to push this
repo to the Heroku, I have noticed, that SQLite3 is used no longer. 
"Challenge accepted." - I think. 
So:
* Platform - ArchLinux
* Rails 4.1.0, Ruby 2.1.1.

###Installing Postgresql (PG) and start database server:
_pacman -S postgresql_ -installing package
_systemd-tmpfiles --create postgresql.conf_ - creates config.
_sudo su - postgres -c "initdb --locale ru_RU.UTF-8 -E UTF8 -D "var/lib/postgres/data'"_ - init claster (*PG specific ?*)
_systemctl start postgresql_ - start server
_systemctl enable postgresql_ - autostart

###Create user for this repo:
_su root
su - postgres_ - become postgres user.
_createuser intey_ - it's me. =]
Manual recommend use -DRSP flags:
D - can't create db; 
R - can't create accounts; 
S - user is no root;
P - ask password.
Also one more hint:
_createuser -a intey_ - make me admin.

###Migrate
in this repo root:
_rake db:setup_ - it's create table (I think so) and .... I should RTFM. TODO:

## It's all.
Lol. It's looks fun. Funny English, Rails, PG, \*Nix and other.
