# rorus

version 0.1

**rorus** is a command-line tool to simplify basic start/stop operations of a Ruby On Rails Unicorn Server.

**rorus** mimics the syntax of an init.d script.

**rorus** does not require _sudo_.

-----

## Summary

~~~
$ rorus [ start | status | stop ]
~~~

-----

## License

rorus is released under the GPLv3 license. THIS SOFTWARE COMES WITH ABSOLUTELY NO GUARANTEES OR WARRANTIES.

-----

## Installing

The following steps will install rorus to a Linux/UNIX system, using the directory _/home/user/bin_.

This guide assumes some familiarity with Linux/UNIX systems and basic programming.

### Pre-installation

Before installing the rorus file, be sure the filesystem has a directory for it, and the directory is in the PATH. 

1. Make a directory in your home folder for executable scripts. For example:

  > `$ mkdir bin`

2. Add the directory to your PATH by editing your .bashrc file (or other shell initializer). For example:

    * Add it to an existing statement: 

    > `$ export PATH="`_`(/any/number/of/preexisting/paths/here)`_`:/home/user/bin"`
    
    * Or use an additional statement:

    > `$ export PATH="$PATH:/home/user/bin"`
    
### Installation

Add the file, change or confirm the application variables, and verify rorus is executable.

1. Transfer the rorus file to _/home/user/bin_.

2. Open the rorus file with a text editor, and change the following variable:

    - *line 22: app_dir*  
      the root directory for the rails application

3. With the text editor still open, verify the following default values, and make changes if needed:

    - *line 23: config_file*  
      the config file for the unicorn server

    - *line 24: pid_file*  
      the PID file created by the unicorn server

    - *line 25: server_start_cmd*  
      the command used to start the unicorn server
  
4. Save the rorus file.

5. Make the rorus file executable.

  > `$ chmod 744 rorus`    


-----

## Usage

To start the rails application:

  > `$ rorus start`

To show the status of an application, including process IDs for a running server:

  > `$ rorus status`

To stop a running application:  

  > `$ rorus stop`

-----

_Tested with chruby, Rails 6, and Ubuntu 18.04_  
_(p) 2020 Eli Harrison CC-BY GPLv3_