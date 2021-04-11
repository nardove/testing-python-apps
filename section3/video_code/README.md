# VSCode setup

If you are using VSCode for this course, you my find an error on the first code example, but with a little setup you can make it work as it should.

If you get the error code regarding the 'blog' module not found, then follow this steps:
1. Create a folder at the root with the name `.vscode`
2. In it create a file with the name `settings.json`
3. Add the code:
```json
{
    "python.testing.unittestArgs": [
        "-v",
        "-s",
        "./blog",
        "-p",
        "*test*.py"
    ],
    "python.testing.unittestEnabled": true,
    "python.analysis.extraPaths": ["blog"]
}
```
4. Create an empty `__init__.py` file at the root of every folder in side the `test` directory
5. Everything should work

The folder structure should look like this:
```
.
├── app.py
├── blog.py
├── post.py
└── test
    ├── __init__.py
    └── unit
        ├── __init__.py
        ├── test_blog.py
        └── test_post.py
```
Anf once you reach the integration part, the folder structure should look like this:
```
.
├── app.py
├── blog.py
├── post.py
└── test
    ├── __init__.py
    ├── integration
    │   ├── __init__.py
    │   └── test_blog.py
    └── unit
        ├── __init__.py
        ├── test_blog.py
        └── test_post.py
```

The main thing to keep in mind is that VSCode does not aout generate the `__init__.py` files that are necesary to tell the compile that these are modules
