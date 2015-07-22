#!/bin/bash

cp tianc-sde/vim/vimrc ~/.vimrc

git clone https://github.com/gmarik/Vundle.vim.git ~/.vim/bundle/Vundle.vim

vim #type in  :PluginInstall (YouCompleteMe may Fail)

# to install YouCompleteme, download clang-llvm first

 cd ~/.vim/bundle

 git clone https://github.com/Valloric/YouCompleteMe.git

 cd YouCompleteMe

 git submodule update --init --recursive

 cd ~

 mkdir utilSpace

 cd utilSpace

 wget http://llvm.org/releases/3.6.0/clang+llvm-3.6.0-x86_64-linux-gnu-ubuntu-14.04.tar.xz

 tar xvf clang+llvm-3.6.0-x86_64-linux-gnu-ubuntu-14.04.tar.xz

 mkdir ycm_build

 cd ycm_build/

 cmake -G "Unix Makefiles" . ~/.vim/bundle/YouCompleteMe/third_party/ycmd/cpp

 cmake -G "Unix Makefiles" -DPATH_TO_LLVM_ROOT=~/utilspace/clang+llvm-3.6.0-x86_64-linux-gnu/ . ~/.vim/bundle/YouCompleteMe/third_party/ycmd/cpp

 make ycm_support_libs

 make

#to make vim-clang-format work:

 sudo cp ~/utilspace/clang+llvm-3.6.0-x86_64-linux-gnu/bin/clang-format /usr/bin

# a lot of good plugins

https://github.com/amix/vimrc
