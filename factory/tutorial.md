# Hello, fab

fabfile.py

    def hello():
        print("Hello world!")

$ fab hello

    Hello world!

    Done.

# Task arguments

    def hello(name="world"):
        print("Hello %s!" % name)

$ fab hello:name=Jeff

    Hello Jeff!

    Done.

$ fab hello:Jeff

    Hello Jeff!

    Done.

# Local commands

    from fabric.api import local

    def prepare_deploy():
        local("./manage.py test my_app")
        local("git add -p && git commit")
        local("git push")

# Organize it your way

Because Fabric is “just Python” you’re free to organize your fabfile any way you want.

from fabric.api import local

    def test():
        local("./manage.py test my_app")

    def commit():
        local("git add -p && git commit")

    def push():
        local("git push")

    def prepare_deploy():
        test()
        commit()
        push()

# Failure

Fabric checks the return value of programs called via operations and will abort if they didn’t exit cleanly.

## Failure handling

A setting (or environment variable, usually shortened to env var) called warn_only lets you turn aborts into warnings, allowing flexible error handling to occur.

    from __future__ import with_statement
    from fabric.api import local, settings, abort
    from fabric.contrib.console import confirm

    def test():
        with settings(warn_only=True):
            result = local('./manage.py test my_app', capture=True)
        if result.failed and not confirm("Tests failed. Continue anyway?"):
            abort("Aborting at user request.")


* The __future__ import required to use with: in Python 2.5;
* Fabric’s contrib.console submodule, containing the confirm function, used for simple yes/no prompts;
* The settings context manager, used to apply settings to a specific block of code;
* Command-running operations like local can return objects containing info about their result (such as .failed, or .return_code);
* And the abort function, used to manually abort execution.

# Making connections

    from __future__ import with_statement
    from fabric.api import local, settings, abort, run, cd
    from fabric.contrib.console import confirm

    def deploy():
        code_dir = '/srv/django/myproject'
        with cd(code_dir):
            run("git pull")
            run("touch app.wsgi")


* Fabric is just Python – so we can make liberal use of regular Python code constructs such as variables and string interpolation;
* cd, an easy way of prefixing commands with a cd /to/some/directory call. This is similar to lcd which does the same locally.
* run, which is similar to local but runs remotely instead of locally.

## Remote interactivity

    def deploy():
        code_dir = '/srv/django/myproject'
        with settings(warn_only=True):
            if run("test -d %s" % code_dir).failed:
                run("git clone user@vcshost:/path/to/repo/.git %s" % code_dir)
        with cd(code_dir):
            run("git pull")
            run("touch app.wsgi")

# Conclusion

    from __future__ import with_statement
    from fabric.api import *
    from fabric.contrib.console import confirm

    env.hosts = ['my_server']

    def test():
        with settings(warn_only=True):
            result = local('./manage.py test my_app', capture=True)
        if result.failed and not confirm("Tests failed. Continue anyway?"):
            abort("Aborting at user request.")

    def commit():
        local("git add -p && git commit")

    def push():
        local("git push")

    def prepare_deploy():
        test()
        commit()
        push()

    def deploy():
        code_dir = '/srv/django/myproject'
        with settings(warn_only=True):
            if run("test -d %s" % code_dir).failed:
                run("git clone user@vcshost:/path/to/repo/.git %s" % code_dir)
        with cd(code_dir):
            run("git pull")
            run("touch app.wsgi")


* defining fabfile tasks and running them with fab;
* calling local shell commands with local;
* modifying env vars with settings;
* handling command failures, prompting the user, and manually aborting;
* and defining host lists and run-ning remote commands.
