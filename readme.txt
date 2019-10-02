Overview:
--------

Vintage is a vi editing package for Sublime Text. It's not quite a faithful recreation, and not all details match up. On the other hand, you do get multiple selections.


Enabling Vintage:
--------

Vintage is disabled by default, via the ignored_packages global setting. If you remove "Vintage" from the list of ignored packages, you'll be able to edit with vi keys.

Vintage starts in insert mode by default. This can be changed by adding:

	"vintage_start_in_command_mode": true

to your User File Settings.


Major Differences From vi:
--------

Insert mode is plain Sublime Text editing, with the usual Sublime Text key bindings: vi insert mode key bindings are not emulated.

Ex commands are not implemented, apart from :w and :e, which work via the command palette.


Extending Vintage:
--------

Vintage is implemented entirely in Python. Extending it, for example, to add additional motions, is a matter of writing the relevant plugin (see vintage_motions.py for the existing ones), and adding a key binding for it.

Motions are normal commands that work by selecting the range of text that they move over. The end of the selection (.b), is considered the active end. Motions are either inclusive, or exclusive (the default). Exclusive motions will move the caret to the right of the last selected character, inclusive motions will move it to the left. Motions are considered inclusive if the inclusive flag is passed to the set_motion command.




---------------------------
["e", "u"], ["alt+0"]       Вход в vim режим
"escape"                    Выход из визуального режима
"c"                         Вход в insert mode
"z"                         Перенос каретки к 1 не пустому символу в строке + insert mode
"z" (visual)                Перенос каретки к началу выделения текста + insert mode
"s"                         Перенос каретки к последнему символу в строке + insert mode
"r"                         Добавление пустой строки под кареткой
"r" (visual)                Перенос каретки к концам выделения
"R"                         Добавление пустой строки над кареткой
"g"                         Undo
"k"                         Visual mode
"K"                         Visual line mode
"L"                         Вставить текст слева от каретки
"l"                         Вставить текст справа от каретки
"H"                         Join lines
["p", "<character>"]        Replace character
"q"                         Удалить символ справа от каретки
"Q"                         Удалить символ слева от каретки
"~" + selection             Swap case
"~"                         Swap letter case
"e"                         Delete line
"f"                         Копировать
"j" (visual)                Delete selection + insert mode
"?"                         Поднять курсор к пустой строке выше
"+"                         Опустить курсор к пустой строке ниже
"<"                         Перенести курсор к началу слова
","                         Перенести курсор вперед
"x"                         Перенести курсор назад
"X"                         Перенести курсор к началу слова назад
"."                         Перенести курсор в конце слова
">"                         Перенести курсор до пустого символа вправо
"alt+,"                     Движение курсора вправо по sub-words
"alt+x"                     Движение курсора влево по sub-words
"b"                         Перемещение каретки в конец строки
"^"                         Перемещение каретки в начало строки, до первого не пустого символа
"n"                         Вправо
"d"                         Влево
"h"                         Вниз
"t"                         Вверх
"I"                         В конце файла
"i"                         В начало файла
["u", "<character>"]        Перенести курсор до символа вправо
["U", "<character>"]        Перенести курсор до символа влево
"m"                         Передвинуть курсор до скобок
"J"                         Удалить до конца строки + insert mode
"F"                         Копировать строку
"o"                         Удаляет + insert mode
"0"                         В начало строки
";"                         Scroll to center
"/"                         Show panel
