

cd Green-Ace/workspace
git clone git@github.com:Green-Ace/TimpLab4.git
cd Green-Ace/workspace/TimpLab4

cat >> CMakeLists.txt <<EOF
cmake_minimum_required(VERSION 3.10)
project(formatter)
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
add_library(formatter STATIC formatter_lib/formatter.cpp)
include_directories(formatter_lib)
add_library(formatter_ex STATIC formatter_ex_lib/formatter_ex.cpp)
include_directories(formatter_ex_lib)
add_executable(hello_world hello_world_application/hello_world.cpp)
target_link_libraries(hello_world formatter formatter_ex)
add_library(solver_lib STATIC solver_lib/solver.cpp)
include_directories(solver_lib)
add_executable(solver solver_application/equation.cpp)
target_link_libraries(solver formatter formatter_ex solver_lib)
EOF



![изображение](https://user-images.githubusercontent.com/112771063/226584178-a46bebf7-cf1c-4e79-9a86-d9919598fd58.png)



git add .
git commit -m 'add files'
git push origin main

![изображение](https://user-images.githubusercontent.com/112771063/226585908-0e10d456-b764-47f2-a332-4b364fdedf3e.png)


mkdir .github
cd .github
mkdir workflows
cd workflows
cat >test.yml
name: GitHub Actions Demo
run-name: ${{ github.actor }} is testing out GitHub Actions 🚀
on: [push]
jobs:
  Explore-GitHub-Actions:
    runs-on: ubuntu-latest
    steps:
      - run: echo "🎉 The job was automatically triggered by a ${{ github.event_name }} event."
      - run: echo "🐧 This job is now running on a ${{ runner.os }} server hosted by GitHub!"
      - run: echo "🔎 The name of your branch is ${{ github.ref }} and your repository is ${{ github.repository }}."
      - name: Check out repository code
        uses: actions/checkout@v3
      - run: echo "💡 The ${{ github.repository }} repository has been cloned to the runner."
      - run: echo "🖥 The workflow is now ready to test your code on the runner."
      - name: List files in the repository
        run: |
          ls ${{ github.workspace }}
      - run: echo "🍏 This job's status is ${{ job.status }}."
      
ctrl + d 

~

cd Green-Ace/workspace/TimpLab4

git add .

git commit -m 'add test'

git push origin main 


![изображение](https://user-images.githubusercontent.com/112771063/226591554-69a1f3e1-4386-49d6-a278-9e127dc90358.png)








![изображение](https://user-images.githubusercontent.com/112771063/226591744-d6416d7d-0ddd-4f74-b5d9-bb8024c4bfde.png)












![изображение](https://user-images.githubusercontent.com/112771063/226591976-f166908c-5527-4c73-a6f3-ab75f9a17c2d.png)



[![Test](https://github.com/Green-Ace/TimpLab4/actions/workflows/test.yaml/badge.svg)](https://github.com/Green-Ace/TimpLab4/actions/workflows/test.yaml)


