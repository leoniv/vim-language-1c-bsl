# Поддержка языка 1С:Предприятие 8 (BSL) в VIM

Добавляет подсветку встроенного языка 1С:Предпрятие 8 файлам \*.bsl и \*.os - синтаксис `1C (BSL)`.  

# Связи с другими проектами
Разработка основана на данных репозитария [xDrivenDevelopment/1c-syntax](https://github.com/xDrivenDevelopment/1c-syntax).

# Возможности
* Подсветка синтаксиса для русского и английского языка `1C (BSL)`
* Подсветка синтаксиса для русского и английского языка запросов `1C (SDBL)`
* Поддержка шаблонов кода с помощью плагина [vim-snipmate](https://github.com/garbas/vim-snipmate)
* Поддержка просмотра списка процедур и функций текущего файла с помощью плагина [tagbar](https://github.com/majutsushi/tagbar)
* Поддержка сворачивания блоков кода процедур, функций и областей (#Область)
* Автоматическая расстановка отступов при переходе на новую строку
* Автодополнение для процедур и функций текущего файла, с выводом в подсказке параметров метода
* Автодополнение для переменных текущего файла, объявленных с использование ключевого слова `Перем`

# Зависимости
* [Vundle.vim](https://github.com/VundleVim/Vundle.vim)
* [vim-snipmate](https://github.com/garbas/vim-snipmate)
* [vim-addon-mw-utils](https://github.com/MarcWeber/vim-addon-mw-utils)
* [tlib_vim](https://github.com/tomtom/tlib_vim)
* [tagbar](https://github.com/majutsushi/tagbar)
* [Exuberant ctags](http://ctags.sourceforge.net/)(минимальная версия 5.9) или [universal-ctags](https://github.com/universal-ctags/ctags)

# Установка
Установим менеджер пакетов Vundle для vim [Vundle.vim](https://github.com/VundleVim/Vundle.vim)

Настроим файл `~/.vimrc`
```vim
set nocompatible              " be iMproved, required
filetype off                  " required

"=====================================================
" Vundle settings
"=====================================================
" set the runtime path to include Vundle and initialize
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()

Plugin 'VundleVim/Vundle.vim'		" let Vundle manage Vundle, required

"---------=== Code/project navigation ===-------------
Plugin 'majutsushi/tagbar'          	" Class/module browser

"--------------=== Snippets support ===---------------
Plugin 'garbas/vim-snipmate'		" Snippets manager
Plugin 'MarcWeber/vim-addon-mw-utils'	" dependencies #1
Plugin 'tomtom/tlib_vim'		" dependencies #2

"--------------=== 1С(BSL)===---------------
Plugin 'andreevlex/vim-language-1c-bsl' "

call vundle#end()            		" required
filetype on
filetype plugin on
filetype plugin indent on
```
Запускаем `vim` и набираем команду `:PluginInstall`

После успешной установки добавим в файл `~/.vimrc` настройку для поддержки шаблонов
```vim
" указываем каталог с настройками SnipMate
let g:snippets_dir = "~/.vim/bundle/vim-language-1c-bsl/snippets"
```

Копируем файл `./setup/.ctags` в домашнюю папку `~/.ctags`

# Снимки экрана Gvim
![vim-syntax-1c-bsl](https://cloud.githubusercontent.com/assets/20382553/19023013/51bbcf1c-88f5-11e6-89a0-406e6716c4ee.png)
![vim-language-1c-sdbl](https://cloud.githubusercontent.com/assets/20382553/19448621/af0fa6e2-94b3-11e6-948a-a46821e181d2.png)

# Снимок экрана Vim (терминал)
![vim-1c-bsl-terminal](https://cloud.githubusercontent.com/assets/20382553/19032706/744de89a-896c-11e6-9acf-0ef9e859aaf9.png)
