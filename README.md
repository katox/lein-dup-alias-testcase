# lein-dup-alias-testcase

A minimal reproducible testcase for aliases in profiles.

## Usage

If you run

    lein dumbrepl
    
    Clojure 1.8.0
    user=> 


You will get a normal plain clojure repl. But if you try a profile with the alias of the same name (a dup for example) you will get an exception from leiningen:

    lein with-profile +problem dumbrepl

    Exception in thread "main" java.io.FileNotFoundException: trampoline (No such file or directory), compiling:(/tmp/form-init7926876085163872198.clj:1:73)
        at clojure.lang.Compiler.load(Compiler.java:7391)
        at clojure.lang.Compiler.loadFile(Compiler.java:7317)
        at clojure.main$load_script.invokeStatic(main.clj:275)
        at clojure.main$init_opt.invokeStatic(main.clj:277)
        at clojure.main$init_opt.invoke(main.clj:277)
        at clojure.main$initialize.invokeStatic(main.clj:308)
        at clojure.main$null_opt.invokeStatic(main.clj:342)
        at clojure.main$null_opt.invoke(main.clj:339)
        at clojure.main$main.invokeStatic(main.clj:421)
        at clojure.main$main.doInvoke(main.clj:384)
        at clojure.lang.RestFn.invoke(RestFn.java:421)
        at clojure.lang.Var.invoke(Var.java:383)
        at clojure.lang.AFn.applyToHelper(AFn.java:156)
        at clojure.lang.Var.applyTo(Var.java:700)
        at clojure.main.main(main.java:37)
    Caused by: java.io.FileNotFoundException: trampoline (No such file or directory)
        at java.io.FileInputStream.open0(Native Method)
        at java.io.FileInputStream.open(FileInputStream.java:195)
        at java.io.FileInputStream.<init>(FileInputStream.java:138)
        at java.io.FileInputStream.<init>(FileInputStream.java:93)
        at clojure.lang.Compiler.loadFile(Compiler.java:7314)
        at clojure.main$load_script.invokeStatic(main.clj:275)
        at clojure.main$script_opt.invokeStatic(main.clj:335)
        at clojure.main$script_opt.invoke(main.clj:330)
        at clojure.main$main.invokeStatic(main.clj:421)
        at clojure.main$main.doInvoke(main.clj:384)
        at clojure.lang.RestFn.invoke(RestFn.java:457)
        at clojure.lang.Var.invoke(Var.java:394)
        at user$eval5.invokeStatic(form-init7926876085163872198.clj:1)
        at user$eval5.invoke(form-init7926876085163872198.clj:1)
        at clojure.lang.Compiler.eval(Compiler.java:6927)
        at clojure.lang.Compiler.eval(Compiler.java:6917)
        at clojure.lang.Compiler.load(Compiler.java:7379)
        ... 14 more

## License

Distributed under the Eclipse Public License either version 1.0 or (at
your option) any later version.
