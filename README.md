# Yocto Cheatsheet

## Build Commands

### Start a build
`bitbake <target>`

### Execute a particular task for a package
`bitbake <package> -c <task>`\
Common tasks: fetch, unpack, patch, configure, compile, install, package, package_write, build

***EX***: Compile the Linux kernel\
`bitbake linux-imx -f -c compile`

## Developer Tools
Quick Reference: https://docs.yoctoproject.org/ref-manual/devtool-reference.html

### Modify sources for a recipe
`devtool modify <recipe>`

### Edit a recipe
`devtool edit-recipe <recipe>`

### Apply patches to recipe sources
This is a handy way to apply patches from "devtool modify" to the recipe so you don't have to do it manually (by adding SRC_URI and such)\
`devtool update-recipe <recipe>`

You can also create a new recipe which applies a .bbappend file to keep from editing the base recipe.\
`devtool update-recipe <recipe> -a <base-layer-directory>`\
You will need to ensure that <base-layer-directory> is included in bblayers.conf.



