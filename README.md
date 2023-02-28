# Wheel Axle Example - Python Wheel enhancement library

## See More

[wheel-axle](https://github.com/karellen/wheel-axle)

[wheel-axle-runtime](https://github.com/karellen/wheel-axle-runtime)

## Example

To activate `wheel-axle` using `setuptools` when you need to substitute `wheel` for the `wheel-axle` is the following stanza:

```python
setup(
    # ...
    cmdclass={"bdist_wheel": wheel_axle.bdist_axle.BdistAxle}
    # ...
)

```
The resulting behavior will be as follows:

```bash
(wheel-axle-example) bash-5.2$ pip install build
Collecting build
  Using cached build-0.10.0-py3-none-any.whl (17 kB)
Collecting packaging>=19.0
  Using cached packaging-23.0-py3-none-any.whl (42 kB)
Collecting pyproject_hooks
  Using cached pyproject_hooks-1.0.0-py3-none-any.whl (9.3 kB)
Installing collected packages: pyproject_hooks, packaging, build
Successfully installed build-0.10.0 packaging-23.0 pyproject_hooks-1.0.0

[notice] A new release of pip available: 22.3.1 -> 23.0.1
[notice] To update, run: pip install --upgrade pip
(wheel-axle-example) bash-5.2$ pip install wheel-axle
Collecting wheel-axle
  Using cached wheel_axle-0.0.4-py3-none-any.whl (8.9 kB)
Collecting wheel>=0.37.0
  Using cached wheel-0.38.4-py3-none-any.whl (36 kB)
Collecting wheel-axle-runtime<1.0
  Using cached wheel_axle_runtime-0.0.2-py3-none-any.whl (12 kB)
Collecting filelock
  Using cached filelock-3.9.0-py3-none-any.whl (9.7 kB)
Requirement already satisfied: pip in /home/user/.pyenv/versions/3.11.2/envs/wheel-axle-example/lib/python3.11/site-packages (from wheel-axle-runtime<1.0->wheel-axle) (22.3.1)
Installing collected packages: wheel, filelock, wheel-axle-runtime, wheel-axle
Successfully installed filelock-3.9.0 wheel-0.38.4 wheel-axle-0.0.4 wheel-axle-runtime-0.0.2

[notice] A new release of pip available: 22.3.1 -> 23.0.1
[notice] To update, run: pip install --upgrade pip
(wheel-axle-example) bash-5.2$ python3 -m build -n --wheel
* Getting build dependencies for wheel...
running egg_info
writing src/test_axle_1.egg-info/PKG-INFO
writing dependency_links to src/test_axle_1.egg-info/dependency_links.txt
writing top-level names to src/test_axle_1.egg-info/top_level.txt
reading manifest file 'src/test_axle_1.egg-info/SOURCES.txt'
writing manifest file 'src/test_axle_1.egg-info/SOURCES.txt'
* Building wheel...
running bdist_wheel
running build
running build_py
reproducing link src/bar/foo.so (../../../foo.so) -> build/lib/bar
running build_scripts
copying scripts/script1 -> build/scripts-3.11
changing mode of build/scripts-3.11/script1 from 644 to 755
installing to build/bdist.linux-x86_64/wheel
running install
Distribution option extra_path is deprecated. See issue27919 for details.
running install_lib
creating build/bdist.linux-x86_64/wheel
creating build/bdist.linux-x86_64/wheel/bar
copying build/lib/bar/__init__.py -> build/bdist.linux-x86_64/wheel/bar
registering link build/lib/bar/foo.so (../../../foo.so) -> build/bdist.linux-x86_64/wheel/bar/foo.so
running install_headers
creating build/bdist.linux-x86_64/wheel/test_axle_1-0.0.1.data
creating build/bdist.linux-x86_64/wheel/test_axle_1-0.0.1.data/headers
copying headers/header1.h -> build/bdist.linux-x86_64/wheel/test_axle_1-0.0.1.data/headers
registering link headers/header2.h (header1.h) -> build/bdist.linux-x86_64/wheel/test_axle_1-0.0.1.data/headers
running install_data
creating build/bdist.linux-x86_64/wheel/test_axle_1-0.0.1.data/data
creating build/bdist.linux-x86_64/wheel/test_axle_1-0.0.1.data/data/lib
copying data/lib/foo.1.so -> build/bdist.linux-x86_64/wheel/test_axle_1-0.0.1.data/data/lib
registering link data/lib/foo.so (foo.1.so) -> build/bdist.linux-x86_64/wheel/test_axle_1-0.0.1.data/data/lib
running install_egg_info
running egg_info
writing src/test_axle_1.egg-info/PKG-INFO
writing dependency_links to src/test_axle_1.egg-info/dependency_links.txt
writing requirements to src/test_axle_1.egg-info/requires.txt
writing top-level names to src/test_axle_1.egg-info/top_level.txt
reading manifest file 'src/test_axle_1.egg-info/SOURCES.txt'
writing manifest file 'src/test_axle_1.egg-info/SOURCES.txt'
Copying src/test_axle_1.egg-info to build/bdist.linux-x86_64/wheel/test_axle_1-0.0.1-py3.11.egg-info
running install_scripts
creating build/bdist.linux-x86_64/wheel/test_axle_1-0.0.1.data/scripts
copying build/scripts-3.11/script1 -> build/bdist.linux-x86_64/wheel/test_axle_1-0.0.1.data/scripts
registering link build/scripts-3.11/script2 (script1) -> build/bdist.linux-x86_64/wheel/test_axle_1-0.0.1.data/scripts/script2
changing mode of build/bdist.linux-x86_64/wheel/test_axle_1-0.0.1.data/scripts/script1 to 755
creating build/bdist.linux-x86_64/wheel/test_axle_1-0.0.1.pth
creating build/bdist.linux-x86_64/wheel/test_axle_1-0.0.1.dist-info/WHEEL
creating '/home/user/Documents/src/wheel-axle-example/dist/tmpa1miw0b7/test_axle_1-0.0.1-py3-none-any.whl' and adding 'build/bdist.linux-x86_64/wheel' to it
adding 'test_axle_1-0.0.1.pth'
adding 'bar/__init__.py'
adding 'test_axle_1-0.0.1.data/data/lib/foo.1.so'
adding 'test_axle_1-0.0.1.data/headers/header1.h'
adding 'test_axle_1-0.0.1.data/scripts/script1'
adding 'test_axle_1-0.0.1.dist-info/METADATA'
adding 'test_axle_1-0.0.1.dist-info/WHEEL'
adding 'test_axle_1-0.0.1.dist-info/axle.lck'
adding 'test_axle_1-0.0.1.dist-info/symlinks.txt'
adding 'test_axle_1-0.0.1.dist-info/top_level.txt'
adding 'test_axle_1-0.0.1.dist-info/RECORD'
removing build/bdist.linux-x86_64/wheel
Successfully built test_axle_1-0.0.1-py3-none-any.whl
```
