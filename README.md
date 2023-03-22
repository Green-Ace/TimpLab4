

cd Green-Ace/workspace

git clone git@github.com:Green-Ace/TimpLab4.git

cd Green-Ace/workspace/TimpLab4



![изображение](https://user-images.githubusercontent.com/112771063/226584178-a46bebf7-cf1c-4e79-9a86-d9919598fd58.png)



git add .

git commit -m 'add files'

git push origin main




![изображение](https://user-images.githubusercontent.com/112771063/226994991-e171f903-8994-4a3a-bc41-d95b443fb73c.png)


name: Test Build
on: [push]
jobs:
    Test_gcc:
        runs-on: ubuntu-latest
        steps:
        - name: Check out repository code
          uses: actions/checkout@v3
        - run: sudo apt update -y
        - run: sudo apt install -y cmake
        - run: cd hello_world_application && cmake . -B _build && cd _build && make
        - run: cd solver_application && cmake . -B _build && cd _build && make
        - run: echo "This job's status is ${{ job.status }}."

    Test_clang:
        runs-on: ubuntu-latest
        steps:
            - name: Check out repository code
              uses: actions/checkout@v3
            - run: sudo apt update -y
            - run: sudo apt install -y clang cmake
            - run: cd hello_world_application && cmake . -B _build -DCMAKE_CXX_COMPILER=clang++ -DCMAKE_C_COMPILER=clang && cd _build && make
            - run: cd solver_application && cmake . -B _build -DCMAKE_CXX_COMPILER=clang++ -DCMAKE_C_COMPILER=clang && cd _build && make
            - run: echo "This job's status is ${{ job.status }}."




![изображение](https://user-images.githubusercontent.com/112771063/226995556-edf2616a-5d49-4ea5-a9fe-f17f9dbfe852.png)





[![Test](https://github.com/Green-Ace/TimpLab4/actions/workflows/test.yaml/badge.svg)](https://github.com/Green-Ace/TimpLab4/actions/workflows/test.yaml)


