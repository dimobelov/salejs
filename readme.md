Cart Widget that can be embedded into sites in order to allow its users to
buy products and send orders to the site owner.

## How to install NodeJS

We need it to use LESS, and as our web server.

Don't use NodeJS pre-packaged installer because it will install it with sudo and
you don't want that, also don't install it via `brew` or other package manager because
for some reason unknown to me all of them install it somehow wrongly.
It's better to built NodeJS from sources.

``` Bash
wget http://nodejs.org/dist/vX.X.X/node-vX.X.X.tar.gz
tar -xzf node-vX.X.X.tar.gz
cd node-vX.X.X
./configure
make
make install
```

## How to install LESS

NodeJS should be installed, then type `npm install less -g`

## How to namespace Twitter Bootstrap styles

Download Twitter Bootstrap http://getbootstrap.com, go to `css` folder, create
`bootstrap.less` file and copy content of `bootstrap.css` there (LESS is superset of CSS so it will be fine).

Create file `bootstrap-widget.less` and put import bootstrap styles into namespace.

``` CSS
.bootstrap {@import "./bootstrap.less";}
```

Now run LESS and convert it to CSS

``` Bash
lessc bootstrap-widget.less > bootstrap-widget.css
```

You should get file `bootstrap-widget.css` with all bootstrap styles put under
the `bootstrap` namespace.