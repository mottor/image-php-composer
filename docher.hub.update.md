# How to update Docker Hub's version

Build image:

    docker build -t mottor1/php-composer .

Login to docker hub:

    docker login ## Enter login and pass

Change version in file VERSION.md

And run this command:

    for i in $(cat VERSION.md) "latest"; do \
    echo "pushing ${i}"; \
    docker tag mottor1/php-composer "mottor1/php-composer:${i}"; \
    docker push "mottor1/php-composer:${i}"; \
    done
