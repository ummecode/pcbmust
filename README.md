![Haicam Logo](https://haicam.tech/app/themes/haicam/dist/images/haicam-logo-black-250.png)

## Haicam generic camera software

Haicam introduces end-to-end encryption technology to home security cameras since 2017

“With cases of privacy invasion and security breaches involving home security systems on the rise, there has to be a better solution. I think this is it.”

## steps for development-

1. Haicam project introduction-
- https://drive.google.com/u/2/open?id=1C8iJNla9VwyZp5UVFTZnXcy-qrBbTQsNq_UncXnZLAA
- [Haicam Deck.pdf](https://github.com/ummecode/git_test/files/8788162/Haicam.Deck.pdf)
- [Haicam-flow.pdf](https://github.com/ummecode/git_test/files/8788237/Haicam-flow.pdf)
- ### camera state graph
- ![camera-state](https://user-images.githubusercontent.com/104251819/170747956-29cdb8e4-853f-438a-87ee-85d71b0cd953.png)
- [camera-codes.zip](https://github.com/ummecode/git_test/files/8788252/camera-codes.zip)


1. Become familier with Git,Docker,googletest,c++ shared pointer,cmake.
2. Install Ubuntu for linux.
3. install docker,VSCode
4. study https://github.com/libuv/libuv
                https://docs.libuv.org/en/v1.x/guide.html
 - libuv TCP
 - libuv UDP
 - libuv thread
 - libuv timer
5. Haicam project introduction-https://drive.google.com/u/2/open?id=1C8iJNla9VwyZp5UVFTZnXcy-qrBbTQsNq_UncXnZLAA
6. [Haicam Deck.pdf](https://github.com/ummecode/git_test/files/8788162/Haicam.Deck.pdf)


7. please read about the GM8136 firmware- https://www.dropbox.com/s/jbskn03hfnrzgc0/GM8136-Docs.zip?dl=0
8. Fork project https://github.com/Haicam/Haicam to your account.
9. git clone the forked project in your account to your local computer.
10. switch to develop branch.
11. docker pull haicam/haicam-toolchain:latest.
12. Run haicam toolchain docker by command: ./run_docker.sh
13. Enter the docker Environment.
14. Build the project for all platforms, by run command: ./build/haicam.sh
15. Build for Linux x86_64 only by command: ./build/apps/linux-x86_64.sh
16. Run all test cases for Linux x86_64, by command: ./bin/linux/x86_64/generic/haicam-test
17. If the test cases crash, run gdb command below for debug
- $ gdb ./bin/linux/x86_64/generic/haicam-test
- (gdb) r
- (gdb) bt full
- You will find the crash location

15. Memory leak check by command below

- $valgrind ./bin/linux/x86_64/generic/haicam-test

16. You can run one test case by command below (For example)

- $ ./bin/linux/x86_64/generic/haicam-test --gtest_filter=haicam_UDPTest.udp_test
- $ gdb --args ./bin/linux/x86_64/generic/haicam-test --gtest_filter=haicam_UDPTest.udp_test
- $ valgrind ./bin/linux/x86_64/generic/haicam-test --gtest_filter=haicam_UDPTest.udp_test

18. Build for GM8136 by command: build/apps/gm8136-armv5.sh

#### run in docker by qemu simulator: 

- ./bin/gm8136/armv5/generic/haicam-app.sh
or
- ./bin/gm8136/armv5/generic/haicam-test.sh

#### gdb debug in docker

- ./bin/gm8136/armv5/generic/haicam-test-gdb-server.sh

#### then open another terminal to connect to the gdb server

- docker exec -it haicam-docker bash
- ./bin/gm8136/armv5/generic/haicam-test-gdb.sh

19. Do development in the directory below

- header files: include
- source codes: src 
- test codes: test

20. After run your test case and do memory leak check, push your codes to github, and do pull reqest to contribute your codes

