```
@range = generator {
    parameter @start constraint integer;
    parameter @limit constraints (integer, @> @start) ;
    parameter @step constraints (integer, @> 0) default 1;

    @start <= @limit ? {
        @step <= 0 ? throw new LogicException('Step must be positive');
    } : {
        @step >= 0 ? throw new LogicException('Step must be negative')
    }   
    yield from @start to @limit step @step;
};
```