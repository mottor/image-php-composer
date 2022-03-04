# How to update Docker Hub's version

    docker build -t mottor1/php-composer .

    docker login ## Enter login and pass

change version and run this command:

    for i in $(cat VERSION.md) "latest"; do \
    echo "pushing ${i}"; \
    docker tag mottor1/php-composer "mottor1/php-composer:${i}"; \
    docker push "mottor1/php-composer:${i}"; \
    done
