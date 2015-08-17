# Maintainer: Joao Cordeiro <jlcordeiro at gmail dot com>
pkgname=vaporsofinsanity
pkgver=0.54
pkgrel=1
pkgdesc="Roguelike set on a paradise island of Fortarica where a magical fog turns everyone into mindless machines."
arch=('i686' 'x86_64')
url="http://www.roguetemple.com/z/vapors/"
license=('GPL2')
depends=('gcc-libs' 'sdl' 'ncurses' 'zlib' 'glibc')
source=(http://www.roguetemple.com/z/vapors/vapors-054n.zip
        vaporsofinsanity.sh)
md5sums=('7f85f5c8c5236978a30683ae16299b29'
         '3b6964c849baff06b6ec8d4d351ca674')


build() {

  _dest_dir=$pkgdir/usr/share/$pkgname

  mkdir -p $_dest_dir/{save,config,gfx,gsl,rec}

  cd "vapors/src"

  make CCEV=LINUX ../vapors

  cd ..

  install -D -m 644 gfx/*     "$_dest_dir/gfx/"  
  install -D -m 644 gsl/*     "$_dest_dir/gsl/"  
  install -D -m 644 rec/*     "$_dest_dir/rec/"  
  install -D -m 644 config/*  "$_dest_dir/config/"  

  install -T -D -m 644 vapors.ini "$_dest_dir/vapors.ini"  
  install -T -D -m 755 vapors "$_dest_dir/vapors"  

  install -T -D -m 755 "$srcdir/vaporsofinsanity.sh" "$pkgdir/usr/bin/$pkgname"

  chown -R :games $_dest_dir 
  chmod -R g+srw $_dest_dir
}

# vim:set ts=2 sw=2 et:
