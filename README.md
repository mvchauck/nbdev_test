# nbdev_test

nbdev_new produces error "ValueError: max_workers must be <= 61"
--> fix by limiting workers in Lib\site-packages\nbdev\serve.py, e.g.:
parallel(nbdev.serve_drv.main, files, n_workers=min(n_workers, 32), pause=0.01, **kw)