### bundles时遇到mysql2的error

bundle config --local build.mysql2 "--with-ldflags=-L/usr/local/opt/openssl/lib --with-cppflags=-I/usr/local/opt/openssl/include"


/usr/local/opt/openssl/lib
/usr/local/opt/openssl/include

/opt/homebrew/opt/openssl@1.1/lib
/opt/homebrew/opt/openssl@1.1/include

bundle config --local build.mysql2 "--with-ldflags=-L/usr/local/opt/openssl/lib --with-cppflags=-I/usr/local/opt/openssl/include"

export LDFLAGS="-L/usr/local/opt/openssl/lib"
export CPPFLAGS="-I/usr/local/opt/openssl/include"


sudo gem install mysql2 -v '0.5.3' --source 'http://gems.ruby-china.com/' -- --with-ldflags=-L/usr/local/opt/openssl/lib --with-cppflags=-I/usr/local/opt/openssl/include

## brew info openssl
[comment]: <> (If you need to have openssl@1.1 first in your PATH, run:)
echo 'export PATH="/opt/homebrew/opt/openssl@1.1/bin:$PATH"' >> ~/.zshrc

[comment]: <> (For compilers to find openssl@1.1 you may need to set:)
export LDFLAGS="-L/opt/homebrew/opt/openssl@1.1/lib"
export CPPFLAGS="-I/opt/homebrew/opt/openssl@1.1/include"

[comment]: <> (For pkg-config to find openssl@1.1 you may need to set:)
export PKG_CONFIG_PATH="/opt/homebrew/opt/openssl@1.1/lib/pkgconfig"

sudo gem install mysql2 -v '0.5.3' --source 'http://gems.ruby-china.com/' -- --with-ldflags=-L/opt/homebrew/opt/openssl@1.1/lib --with-cppflags=-I/opt/homebrew/opt/openssl@1.1/include


## brew install mysql
[comment]: <> (We've installed your MySQL database without a root password. To secure it run:)
mysql_secure_installation

[comment]: <> (MySQL is configured to only allow connections from localhost by default)
[comment]: <> (To connect run:)
mysql -uroot

[comment]: <> (To have launchd start mysql now and restart at login:)
brew services start mysql

[comment]: <> (Or, if you don't want/need a background service you can just run:)
mysql.server start

[comment]: <> (==> Summary)
[comment]: <> (🍺  /opt/homebrew/Cellar/mysql/8.0.26: 303 files, 296.7MB)

gem install mysql2 -- --with-mysql-config=/opt/homebrew/Cellar/mysql/8.0.26/bin/mysql_config
/opt/homebrew/Cellar/mysql/8.0.26/bin/mysql_config