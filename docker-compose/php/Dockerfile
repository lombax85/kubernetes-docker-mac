FROM webdevops/php-apache:7.2

ENV WEB_DOCUMENT_ROOT=/var/www/public
ENV WEB_DOCUMENT_INDEX=index.php

ADD /web/ /var/www/public/


EXPOSE 80

CMD ["supervisord"]