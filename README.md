docker-phpcs
============

Used to create Docker images for running PHP_CodeSniffer tools (phpcs/phpcbf).  http://pear.php.net/package/PHP_CodeSniffer


Build
--------------------

Build from `Dockerfile`:

    ``` sh
    sudo docker build --no-cache -t initlab/phpcs .
    ```

Verify build:

    ``` sh
    sudo docker run --rm -it initlab/phpcs phpcs --version
    sudo docker run --rm -it initlab/phpcs phpcbf --version
    ```

Usage
--------------------

1. Install the `initlab/phpcs` container (optional - this step is performed by Docker automatically when running the container):

    ``` sh
    $ docker pull denisura/phpcs
    ```

2. Define an bash alias that runs this container whenever `composer` is invoked on the command line:

	``` sh
	$ echo "alias phpcs='docker run --rm -it -v \$(pwd):/workspace initlab/phpcs phpcs'" >> ~/.bashrc
	$ echo "alias phpcbf='docker run --rm -it -v \$(pwd):/workspace initlab/phpcs phpcbf'" >> ~/.bashrc
	$ source ~/.bashrc
	```

3. Run composer as always:

	``` sh
	$ phpcs --version
	```

	``` sh
	$ phpcbf --version
	```
