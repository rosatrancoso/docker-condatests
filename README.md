
1. Build image without environment yml:

    docker build -t test_noyml -f Dockerfile.noyml .

2. Export environment yml:

    docker run --rm test_noyml conda env export -n myenv > environment.yml

3. Build image from environment yml:

    docker build -t test_withyml -f Dockerfile.withyml .

4. Check it's the same:

    docker images

    docker run --rm test_withyml conda env export -n myenv > tmp.yml
    diff environment.yml tmp.yml