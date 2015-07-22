#!/bin/bash

cp tianc-sde/vim/vimrc ~/.vimrc

git clone https://github.com/gmarik/Vundle.vim.git ~/.vim/bundle/Vundle.vim

vim #type in  :PluginInstall (YouCompleteMe may Fail)

#To install YouCompleteme, download clang-llvm first

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

 cmake -G "Unix Makefiles" -DPATH_TO_LLVM_ROOT=~/utilSpace/clang+llvm-3.6.0-x86_64-linux-gnu/ . ~/.vim/bundle/YouCompleteMe/third_party/ycmd/cpp

 make ycm_support_libs

 make

#to make vim-clang-format work:

 sudo cp ~/utilSpace/clang+llvm-3.6.0-x86_64-linux-gnu/bin/clang-format /usr/bin

#to get .ycm_extra_conf.py loaded

cp /home/tianc/.vim/bundle/YouCompleteMe/third_party/ycmd/cpp/ycm/.ycm_extra_conf.py  ~

echo "let g:ycm_confirm_extra_conf = 0" >> ~/.vimrc

#read more settings for ycm at https://github.com/Valloric/YouCompleteMe/blob/master/README.md

# a lot of good plugins

https://github.com/amix/vimrc


