    v.yurin@hell:~/github/sys_test$ erl -config sys
    Erlang R14B03 (erts-5.8.4) [source] [64-bit] [smp:4:4] [rq:4] [async-threads:0]
    [hipe] [kernel-poll:false]
    
    Eshell V5.8.4  (abort with ^G)
    1> application:start(sasl).
    ok
    2> application:get_all_env(sasl).
    [{errlog_type,error},
     {sasl_error_logger,tty},
     {included_applications,[]}]
