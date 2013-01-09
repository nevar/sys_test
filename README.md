Using "test.config":
```bash
v.yurin@hell:~/github/sys_test$ rebar com
==> sys_test (compile)
Compiled src/test_app.erl
Compiled src/test_sup.erl
v.yurin@hell:~/github/sys_test$ erl -pa ebin -config test
Erlang R15B03 (erts-5.9.3.1) [source] [64-bit] [smp:4:4] [async-threads:0]
[hipe] [kernel-poll:false]

Eshell V5.9.3.1  (abort with ^G)
1> application:load(test).
ok
2> application:get_env(test, my_test_key).
{ok,my_test_value}
3> 
```

Using "sys.config" and include "custom.config" and "test.config":
```bash
v.yurin@hell:~/github/sys_test$ rebar com
==> sys_test (compile)
Compiled src/test_app.erl
Compiled src/test_sup.erl
v.yurin@hell:~/github/sys_test$ erl -pa ebin -config sys
Erlang R15B03 (erts-5.9.3.1) [source] [64-bit] [smp:4:4] [async-threads:0] [hipe] [kernel-poll:false]

Eshell V5.9.3.1  (abort with ^G)
1> application:load(test).
ok
2> application:start(sasl).
ok
3> application:get_all_env(sasl).
[{errlog_type,error},
 {sasl_error_logger,tty},
 {included_applications,[]}]
4> application:get_all_env(test).
[{included_applications,[]},{my_test_key,my_test_value}]
5> 
```
