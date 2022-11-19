# https://github.com/phpmyadmin/docker/blob/master/apache/Dockerfile
# https://www.ukraine.com.ua/info/tools/passwdgenerate/

# Access to phpMyAdmin
# login = &35peiYJ3*&;54Ct^KY2N;dAye!yZ+58eTAhei~E2L_i4^_5Ke-44Z46s^2+*xLS
# password = pn&RRj;+8%7+5XukpM*f43gY695#UY;M!k2@2bK4Z#7z35pF3mS)Y_d!r6GH_E(z

FROM phpmyadmin/phpmyadmin:5.2

MAINTAINER soundsgreat <imithos321@gmail.com>

# Add additional web HTTP authorization for phpMyAdmin
RUN rm -rf /var/www/html/index.php; \
    echo '<?php' >>/var/www/html/index.php; \
    echo 'declare(strict_types=1);' >>/var/www/html/index.php; \
    \
#    echo '$login = "&35peiYJ3*&;54Ct^KY2N;dAye!yZ+58eTAhei~E2L_i4^_5Ke-44Z46s^2+*xLS";' >>/var/www/html/index.php; \
#    echo '$password = "pn&RRj;+8%7+5XukpM*f43gY695#UY;M!k2@2bK4Z#7z35pF3mS)Y_d!r6GH_E(z";' >>/var/www/html/index.php; \
#    echo 'if (isset($_SERVER["PHP_AUTH_USER"]) && ($_SERVER["PHP_AUTH_PW"] == $password) && ($_SERVER["PHP_AUTH_USER"] == $login)) {' >>/var/www/html/index.php; \
#    echo '} else {' >>/var/www/html/index.php; \
#    echo '    header("WWW-Authenticate: Basic realm=\"Backend\"");' >>/var/www/html/index.php; \
#    echo '    header("HTTP/1.0 401 Unauthorized");' >>/var/www/html/index.php; \
#    echo '    echo "Forget it! idiot :D";' >>/var/www/html/index.php; \
#    echo '    exit;' >>/var/www/html/index.php; \
#    echo '}' >>/var/www/html/index.php; \
    \
    echo 'use PhpMyAdmin\Routing;' >>/var/www/html/index.php; \
    echo 'if (! defined("ROOT_PATH")) {' >>/var/www/html/index.php; \
    echo 'define("ROOT_PATH", __DIR__ . DIRECTORY_SEPARATOR);' >>/var/www/html/index.php; \
    echo '}' >>/var/www/html/index.php; \
    echo 'global $route, $containerBuilder;' >>/var/www/html/index.php; \
    echo 'require_once ROOT_PATH . "libraries/common.inc.php";' >>/var/www/html/index.php; \
    echo '$dispatcher = Routing::getDispatcher();' >>/var/www/html/index.php; \
    echo 'Routing::callControllerForRoute($route, $dispatcher, $containerBuilder);' >>/var/www/html/index.php;