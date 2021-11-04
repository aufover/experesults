### RUN:
`--div-by-zero-check --signed-overflow-check --unsigned-overflow-check --pointer-overflow-check --undefined-shift-check --float-overflow-check --nan-check --unwind 1 --memory-leak-check --pointer-check --json-ui | cbmc-convert-output | sed 's/: note:/: path:/g' | csgrep --prune 1`

### RESULT: (after removing duplicates)
```console
Error: CBMC_WARNING:
at.c: scope_hint: In function ‘strrchr’:
at.c:772: error: in strrchr: pointer_dereference: dereference failure: invalid integer address in src[(signed long int)i]

Error: CBMC_WARNING:
at.c: scope_hint: In function ‘main’:
at.c:768: error: pointer_dereference: dereference failure: invalid integer address in ge->gr_gid
```

### RESULT WITH TRACE:

##### FIRST ERROR

```console
Error: CBMC_WARNING:
at.c: scope_hint: In function ‘main’:
at.c:768: error: pointer_dereference: dereference failure: invalid integer address in ge->gr_gid
at.c:122: path: entry_point_function:122:integer:        atfile[0l] = '/'
at.c:122: path: entry_point_function:122:integer:        atfile[1l] = 'v'
at.c:122: path: entry_point_function:122:integer:        atfile[2l] = 'a'
at.c:122: path: entry_point_function:122:integer:        atfile[3l] = 'r'
at.c:122: path: entry_point_function:122:integer:        atfile[4l] = '/'
at.c:122: path: entry_point_function:122:integer:        atfile[5l] = 's'
at.c:122: path: entry_point_function:122:integer:        atfile[6l] = 'p'
at.c:122: path: entry_point_function:122:integer:        atfile[7l] = 'o'
at.c:122: path: entry_point_function:122:integer:        atfile[8l] = 'o'
at.c:122: path: entry_point_function:122:integer:        atfile[9l] = 'l'
at.c:122: path: entry_point_function:122:integer:        atfile[10l] = '/'
at.c:122: path: entry_point_function:122:integer:        atfile[11l] = 'a'
at.c:122: path: entry_point_function:122:integer:        atfile[12l] = 't'
at.c:122: path: entry_point_function:122:integer:        atfile[13l] = '/'
at.c:122: path: entry_point_function:122:integer:        atfile[14l] = '1'
at.c:122: path: entry_point_function:122:integer:        atfile[15l] = '2'
at.c:122: path: entry_point_function:122:integer:        atfile[16l] = '3'
at.c:122: path: entry_point_function:122:integer:        atfile[17l] = '4'
at.c:122: path: entry_point_function:122:integer:        atfile[18l] = '5'
at.c:122: path: entry_point_function:122:integer:        atfile[19l] = '6'
at.c:122: path: entry_point_function:122:integer:        atfile[20l] = '7'
at.c:122: path: entry_point_function:122:integer:        atfile[21l] = '8'
at.c:122: path: entry_point_function:122:integer:        atfile[22l] = '9'
at.c:122: path: entry_point_function:122:integer:        atfile[23l] = '0'
at.c:122: path: entry_point_function:122:integer:        atfile[24l] = '1'
at.c:122: path: entry_point_function:122:integer:        atfile[25l] = '2'
at.c:122: path: entry_point_function:122:integer:        atfile[26l] = '3'
at.c:122: path: entry_point_function:122:integer:        atfile[27l] = '4'
at.c:122: path: entry_point_function:122:integer:        atfile[28l] = 0
at.c:111: path: entry_point_function:111:pointer:        no_export[0l] = ?
at.c:111: path: entry_point_function:111:pointer:        no_export[1l] = ?
at.c:111: path: entry_point_function:111:pointer:        no_export[2l] = ?
at.c:111: path: entry_point_function:111:pointer:        no_export[3l] = ?
at.c:111: path: entry_point_function:111:pointer:        no_export[4l] = ?
at.c:111: path: entry_point_function:111:pointer:        no_export[5l] = ?
at.c:111: path: entry_point_function:111:pointer:        no_export[6l] = ?
at.c:111: path: entry_point_function:111:pointer:        no_export[7l] = ?
at.c:111: path: entry_point_function:111:pointer:        no_export[8l] = ?
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[0l] = 0
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[1l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[2l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[3l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[4l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[5l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[6l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[7l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[8l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[9l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[10l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[11l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[12l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[13l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[14l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[15l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[16l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[17l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[18l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[19l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[20l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[21l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[22l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[23l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[24l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[25l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[26l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[27l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[28l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[29l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[30l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[31l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[32l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[33l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[34l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[35l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[36l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[37l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[38l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[39l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[40l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[41l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[42l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[43l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[44l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[45l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[46l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[47l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[48l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[49l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[50l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[51l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[52l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[53l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[54l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[55l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[56l] = 1
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[0l] = -1
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[1l] = '"'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[2l] = '#'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[3l] = '$'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[4l] = '%'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[5l] = '&'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[6l] = '\''
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[7l] = '('
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[8l] = 'D'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[9l] = 'A'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[10l] = ')'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[11l] = '*'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[12l] = '+'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[13l] = ','
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[14l] = '-'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[15l] = 'U'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[16l] = '.'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[17l] = ';'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[18l] = '<'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[19l] = '='
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[20l] = 'O'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[21l] = '7'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[22l] = 'G'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[23l] = 'V'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[24l] = 'P'
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[0l] = -73
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[1l] = -73
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[2l] = -73
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[3l] = -73
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[4l] = -73
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[5l] = -73
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[6l] = -73
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[7l] = -73
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[8l] = -14
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[9l] = -73
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[10l] = -7
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[11l] = -73
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[12l] = -1
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[13l] = -73
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[14l] = -18
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[15l] = 11
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[16l] = 'A'
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[17l] = -73
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[18l] = -73
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[19l] = -73
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[20l] = '$'
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[21l] = -72
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[22l] = '1'
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[23l] = -73
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[24l] = -73
at.c:744: path: from_entry_point_function:function-call:main
at.c:744: path: function_parameter_set_in:entry_point_function:744:integer:        argc = 134217727
at.c:744: path: function_parameter_set_in:entry_point_function:744:pointer:        argv = argv'
at.c:746: path: main:746:integer:        c = 0
at.c:747: path: main:747:integer:        queue = 0
at.c:747: path: main:747:integer:        queue = 'a'
at.c:748: path: main:748:integer:        queue_set = 0
at.c:749: path: main:749:pointer:        pgm = ((char *)NULL)
at.c:751: path: main:751:integer:        program = 0
at.c:751: path: main:751:integer:        program = 3
at.c:752: path: main:752:pointer:        options = ((char *)NULL)
at.c:752: path: main:752:pointer:        options = ?
at.c:753: path: main:753:integer:        disp_version = 0
at.c:754: path: main:754:integer:        timer = 0l
at.c:755: path: main:755:pointer:        pwe = ((struct passwd *)NULL)
at.c:756: path: main:756:pointer:        ge = ((struct group *)NULL)
at.c:758: path: from_main:function-call:getuid
at.c:758: path: from_main:function-return:getuid
at.c:758: path: main:758:integer:        real_uid = 0u
at.c:758: path: from_main:function-call:geteuid
at.c:758: path: from_main:function-return:geteuid
at.c:758: path: main:758:integer:        effective_uid = 0u
at.c:758: path: from_main:function-call:getgid
at.c:758: path: from_main:function-return:getgid
at.c:758: path: main:758:integer:        real_gid = 0u
at.c:758: path: from_main:function-call:getegid
at.c:758: path: from_main:function-return:getegid
at.c:758: path: main:758:integer:        effective_gid = 0u
at.c:758: path: from_main:function-call:setreuid
at.c:758: path: from_main:function-return:setreuid
at.c:758: path: from_main:function-call:setregid
at.c:758: path: from_main:function-return:setregid
at.c:760: path: from_main:function-call:getpwnam
at.c:760: path: from_main:function-return:getpwnam
at.c:760: path: main:760:pointer:        pwe = ?
at.c:763: path: dereference failure: pointer NULL in pwe->pw_uid
at.c:763: path: dereference failure: deallocated dynamic object in pwe->pw_uid
at.c:763: path: dereference failure: dead object in pwe->pw_uid
at.c:763: path: dereference failure: invalid integer address in pwe->pw_uid
at.c:763: path: main:763:integer:        daemon_uid = 0u
at.c:765: path: from_main:function-call:getgrnam
at.c:765: path: from_main:function-return:getgrnam
at.c:765: path: main:765:pointer:        ge = ?
at.c:768: path: dereference failure: pointer NULL in ge->gr_gid
at.c:768: path: dereference failure: deallocated dynamic object in ge->gr_gid
at.c:768: path: dereference failure: dead object in ge->gr_gid
at.c:768: path: dereference failure: invalid integer address in ge->gr_gid
```
##### SECOND ERROR:
```console
Error: CBMC_WARNING:
at.c: scope_hint: In function ‘strrchr’:
at.c:23: error: pointer_dereference: dereference failure: pointer outside object bounds in src[(signed long int)i]
at.c:122: path: entry_point_function:122:integer:        atfile[0l] = '/'
at.c:122: path: entry_point_function:122:integer:        atfile[1l] = 'v'
at.c:122: path: entry_point_function:122:integer:        atfile[2l] = 'a'
at.c:122: path: entry_point_function:122:integer:        atfile[3l] = 'r'
at.c:122: path: entry_point_function:122:integer:        atfile[4l] = '/'
at.c:122: path: entry_point_function:122:integer:        atfile[5l] = 's'
at.c:122: path: entry_point_function:122:integer:        atfile[6l] = 'p'
at.c:122: path: entry_point_function:122:integer:        atfile[7l] = 'o'
at.c:122: path: entry_point_function:122:integer:        atfile[8l] = 'o'
at.c:122: path: entry_point_function:122:integer:        atfile[9l] = 'l'
at.c:122: path: entry_point_function:122:integer:        atfile[10l] = '/'
at.c:122: path: entry_point_function:122:integer:        atfile[11l] = 'a'
at.c:122: path: entry_point_function:122:integer:        atfile[12l] = 't'
at.c:122: path: entry_point_function:122:integer:        atfile[13l] = '/'
at.c:122: path: entry_point_function:122:integer:        atfile[14l] = '1'
at.c:122: path: entry_point_function:122:integer:        atfile[15l] = '2'
at.c:122: path: entry_point_function:122:integer:        atfile[16l] = '3'
at.c:122: path: entry_point_function:122:integer:        atfile[17l] = '4'
at.c:122: path: entry_point_function:122:integer:        atfile[18l] = '5'
at.c:122: path: entry_point_function:122:integer:        atfile[19l] = '6'
at.c:122: path: entry_point_function:122:integer:        atfile[20l] = '7'
at.c:122: path: entry_point_function:122:integer:        atfile[21l] = '8'
at.c:122: path: entry_point_function:122:integer:        atfile[22l] = '9'
at.c:122: path: entry_point_function:122:integer:        atfile[23l] = '0'
at.c:122: path: entry_point_function:122:integer:        atfile[24l] = '1'
at.c:122: path: entry_point_function:122:integer:        atfile[25l] = '2'
at.c:122: path: entry_point_function:122:integer:        atfile[26l] = '3'
at.c:122: path: entry_point_function:122:integer:        atfile[27l] = '4'
at.c:122: path: entry_point_function:122:integer:        atfile[28l] = 0
at.c:111: path: entry_point_function:111:pointer:        no_export[0l] = ?
at.c:111: path: entry_point_function:111:pointer:        no_export[1l] = ?
at.c:111: path: entry_point_function:111:pointer:        no_export[2l] = ?
at.c:111: path: entry_point_function:111:pointer:        no_export[3l] = ?
at.c:111: path: entry_point_function:111:pointer:        no_export[4l] = ?
at.c:111: path: entry_point_function:111:pointer:        no_export[5l] = ?
at.c:111: path: entry_point_function:111:pointer:        no_export[6l] = ?
at.c:111: path: entry_point_function:111:pointer:        no_export[7l] = ?
at.c:111: path: entry_point_function:111:pointer:        no_export[8l] = ?
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[0l] = 0
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[1l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[2l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[3l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[4l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[5l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[6l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[7l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[8l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[9l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[10l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[11l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[12l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[13l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[14l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[15l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[16l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[17l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[18l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[19l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[20l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[21l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[22l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[23l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[24l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[25l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[26l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[27l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[28l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[29l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[30l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[31l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[32l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[33l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[34l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[35l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[36l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[37l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[38l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[39l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[40l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[41l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[42l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[43l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[44l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[45l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[46l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[47l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[48l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[49l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[50l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[51l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[52l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[53l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[54l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[55l] = 1
lex.yy.c:421: path: entry_point_function:421:integer:        yy_meta[56l] = 1
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[0l] = -1
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[1l] = '"'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[2l] = '#'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[3l] = '$'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[4l] = '%'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[5l] = '&'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[6l] = '\''
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[7l] = '('
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[8l] = 'D'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[9l] = 'A'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[10l] = ')'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[11l] = '*'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[12l] = '+'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[13l] = ','
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[14l] = '-'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[15l] = 'U'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[16l] = '.'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[17l] = ';'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[18l] = '<'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[19l] = '='
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[20l] = 'O'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[21l] = '7'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[22l] = 'G'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[23l] = 'V'
y.tab.c:813: path: entry_point_function:813:integer:        yydefgoto[24l] = 'P'
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[0l] = -73
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[1l] = -73
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[2l] = -73
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[3l] = -73
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[4l] = -73
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[5l] = -73
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[6l] = -73
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[7l] = -73
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[8l] = -14
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[9l] = -73
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[10l] = -7
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[11l] = -73
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[12l] = -1
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[13l] = -73
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[14l] = -18
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[15l] = 11
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[16l] = 'A'
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[17l] = -73
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[18l] = -73
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[19l] = -73
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[20l] = '$'
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[21l] = -72
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[22l] = '1'
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[23l] = -73
y.tab.c:805: path: entry_point_function:805:integer:        yypgoto[24l] = -73
at.c:744: path: from_entry_point_function:function-call:main
at.c:744: path: function_parameter_set_in:entry_point_function:744:integer:        argc = 134217727
at.c:744: path: function_parameter_set_in:entry_point_function:744:pointer:        argv = argv'
at.c:746: path: main:746:integer:        c = 0
at.c:747: path: main:747:integer:        queue = 0
at.c:747: path: main:747:integer:        queue = 'a'
at.c:748: path: main:748:integer:        queue_set = 0
at.c:749: path: main:749:pointer:        pgm = ((char *)NULL)
at.c:751: path: main:751:integer:        program = 0
at.c:751: path: main:751:integer:        program = 3
at.c:752: path: main:752:pointer:        options = ((char *)NULL)
at.c:752: path: main:752:pointer:        options = ?
at.c:753: path: main:753:integer:        disp_version = 0
at.c:754: path: main:754:integer:        timer = 0l
at.c:755: path: main:755:pointer:        pwe = ((struct passwd *)NULL)
at.c:756: path: main:756:pointer:        ge = ((struct group *)NULL)
at.c:758: path: from_main:function-call:getuid
at.c:758: path: from_main:function-return:getuid
at.c:758: path: main:758:integer:        real_uid = 0u
at.c:758: path: from_main:function-call:geteuid
at.c:758: path: from_main:function-return:geteuid
at.c:758: path: main:758:integer:        effective_uid = 0u
at.c:758: path: from_main:function-call:getgid
at.c:758: path: from_main:function-return:getgid
at.c:758: path: main:758:integer:        real_gid = 0u
at.c:758: path: from_main:function-call:getegid
at.c:758: path: from_main:function-return:getegid
at.c:758: path: main:758:integer:        effective_gid = 0u
at.c:758: path: from_main:function-call:setreuid
at.c:758: path: from_main:function-return:setreuid
at.c:758: path: from_main:function-call:setregid
at.c:758: path: from_main:function-return:setregid
at.c:760: path: from_main:function-call:getpwnam
at.c:760: path: from_main:function-return:getpwnam
at.c:760: path: main:760:pointer:        pwe = ?
at.c:763: path: dereference failure: pointer NULL in pwe->pw_uid
at.c:763: path: dereference failure: deallocated dynamic object in pwe->pw_uid
at.c:763: path: dereference failure: dead object in pwe->pw_uid
at.c:763: path: dereference failure: invalid integer address in pwe->pw_uid
at.c:763: path: main:763:integer:        daemon_uid = 0u
at.c:765: path: from_main:function-call:getgrnam
at.c:765: path: from_main:function-return:getgrnam
at.c:765: path: main:765:pointer:        ge = ?
at.c:768: path: dereference failure: pointer NULL in ge->gr_gid
at.c:768: path: dereference failure: deallocated dynamic object in ge->gr_gid
at.c:768: path: dereference failure: dead object in ge->gr_gid
at.c:768: path: dereference failure: invalid integer address in ge->gr_gid
at.c:768: path: main:768:integer:        daemon_gid = 0u
at.c:772: path: from_main:function-call:strrchr
at.c:772: path: function_parameter_set_in:main:772:pointer:        src = ?
at.c:772: path: function_parameter_set_in:main:772:integer:        c = 47
<builtin-library-strrchr>:22: path: pointer arithmetic: pointer NULL in src + (signed long int)i
<builtin-library-strrchr>:22: path: pointer arithmetic: deallocated dynamic object in src + (signed long int)i
<builtin-library-strrchr>:22: path: pointer arithmetic: dead object in src + (signed long int)i
<builtin-library-strrchr>:22: path: pointer arithmetic: pointer outside object bounds in src + (signed long int)i
<builtin-library-strrchr>:22: path: pointer arithmetic: invalid integer address in src + (signed long int)i
<builtin-library-strrchr>:22: path: dereference failure: pointer NULL in src[(signed long int)i]
<builtin-library-strrchr>:22: path: dereference failure: deallocated dynamic object in src[(signed long int)i]
<builtin-library-strrchr>:22: path: dereference failure: dead object in src[(signed long int)i]
<builtin-library-strrchr>:22: path: dereference failure: pointer outside object bounds in src[(signed long int)i]
<builtin-library-strrchr>:22: path: dereference failure: invalid integer address in src[(signed long int)i]
<builtin-library-strrchr>:22: path: pointer arithmetic: pointer NULL in (char *)src + (signed long int)i
<builtin-library-strrchr>:22: path: pointer arithmetic: deallocated dynamic object in (char *)src + (signed long int)i
<builtin-library-strrchr>:22: path: pointer arithmetic: dead object in (char *)src + (signed long int)i
<builtin-library-strrchr>:22: path: pointer arithmetic: pointer outside object bounds in (char *)src + (signed long int)i
<builtin-library-strrchr>:22: path: pointer arithmetic: invalid integer address in (char *)src + (signed long int)i
<builtin-library-strrchr>:23: path: pointer arithmetic: pointer NULL in src + (signed long int)i
<builtin-library-strrchr>:23: path: pointer arithmetic: deallocated dynamic object in src + (signed long int)i
<builtin-library-strrchr>:23: path: pointer arithmetic: dead object in src + (signed long int)i
<builtin-library-strrchr>:23: path: pointer arithmetic: pointer outside object bounds in src + (signed long int)i
<builtin-library-strrchr>:23: path: pointer arithmetic: invalid integer address in src + (signed long int)i
<builtin-library-strrchr>:23: path: dereference failure: pointer NULL in src[(signed long int)i]
<builtin-library-strrchr>:23: path: dereference failure: deallocated dynamic object in src[(signed long int)i]
<builtin-library-strrchr>:23: path: dereference failure: dead object in src[(signed long int)i]
<builtin-library-strrchr>:23: path: dereference failure: pointer outside object bounds in src[(signed long int)i]
```
