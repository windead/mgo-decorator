# mgo-decorator
Use decorator to implement some features on globalsign/mgo, like performance monitor, mock and etc. 

## TODO
1. Due to the mgo library didn't provide interface, so it need an extractor to get interfaces automatically from mgo, mainly from mgo/session.go.
2. Due to golang has no function like the magic method __call() in PHP, so it need a generator to generate code for every interface func from TODO.1.
3. Due to golang is strongly typed, even for the function type, so it cannot implement the decorator like Python, then either we use reflection, or we use a template embedded into TODO.2.
   * Using reflection, we can get parameters and returns in the decorator, although we cannot do anything except log without type assertion, but this is still pros. Meanwhile, the preformanc is definitely cons.
   * Using template, we cannot get parameters and returns, unless we provide a special decorator for some func. But the performance is OK.
   
   So we may provide these 2 implementations for develop and production environment.
4. We will love a mgo mock for our unit test.
   We can refer to https://godoc.org/database/sql/driver
