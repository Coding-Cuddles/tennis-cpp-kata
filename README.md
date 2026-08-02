# Tennis C++ Kata

[![CI](https://github.com/Coding-Cuddles/tennis-cpp-kata/actions/workflows/main.yml/badge.svg)](https://github.com/Coding-Cuddles/tennis-cpp-kata/actions/workflows/main.yml)
[![C++17](https://img.shields.io/badge/C%2B%2B-17-blue.svg)](https://en.cppreference.com/w/cpp/17)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

Implement tennis scoring in C++17 against the disabled specification test.
Setup is complete when the test binary builds and CTest discovers the test.

## Overview

This kata complements [Clean Code: Fundamentals, Ep. 4 - Function Structure](https://cleancoders.com/episode/clean-code-episode-4).

The rules of the tennis kata are as follows:

- The game is played by two players, called "Player 1" and "Player 2".
- The players start with a score of 0 points each.
- The players take turns hitting the ball over the net, with Player 1 serving
  first.
- The game continues until one of the players reaches a score of 4 points.
- If a player reaches a score of 4 points, they must have a lead of at least 2
  points over the other player in order to win the game. For example, if player
  1 has a score of 4 and player 2 has a score of 3, the game continues.
- If the scores are tied at 4 points each, the game enters the "Deuce" mode. In
  deuce mode, the players continue to play until one of them has a lead of 2
  points.

For more information on the rules of tennis, please see
the [official rules](https://www.itftennis.com/en/about-us/governance/rules-and-regulations/)
from International Tennis Federation.

## Instructions

To complete the kata, your code should include the following features:

- A function that keeps track of the score for each player: this function
  should be able to increment the score for a player when they win a point.
- A function that returns a string representation of the current score.

The rules for scoring representation are as follows:

- If both players have the same number of points, the score is described as
  "Love-All", "Fifteen-All", "Thirty-All", or "Deuce" depending on the number
  of points scored.
- If one player has scored four or more points and has a two-point lead over
  the other player, the score is described as "Win for Player 1" or "Win for
  Player 2" depending on which player has won.
- If one player has scored four or more points and has a one-point lead over
  the other player, the score is described as "Advantage Player 1" or
  "Advantage Player 2" depending on which player has the advantage.
- If both players have scored less than four points, the score is described as
  "Love", "Fifteen", "Thirty", or "Forty" depending on the number of points
  scored by each player.

## Prerequisites

Required:

- [Git](https://git-scm.com/downloads)
- A compiler with C++17 support. Choose one:
  - [GCC](https://gcc.gnu.org/) 10+ on Linux
  - [LLVM Clang](https://llvm.org/) 14+ on Linux
  - [Apple Clang](https://developer.apple.com/xcode/) 17+ on macOS
  - [MSVC](https://visualstudio.microsoft.com/) 2022 on Windows
- [CMake 3.24 or later](https://cmake.org)

Optional:

- [GNU Make](https://www.gnu.org/software/make/), for shorter commands. Every
  required task also has direct CMake and CTest commands. Make may be
  unavailable on Windows.

You do not need to install GoogleTest separately. CMake finds an installed
copy or downloads the pinned release when needed.

## Set up the kata

1. Clone the repository:

   ```console
   git clone https://github.com/Coding-Cuddles/tennis-cpp-kata.git
   ```

2. Enter the repository directory:

   ```console
   cd tennis-cpp-kata
   ```

3. Build and discover the specification test. Use Make when it is installed:

   ```console
   make test
   ```

   Otherwise, use CMake and CTest directly:

   ```console
   cmake -S . -B build -DCMAKE_BUILD_TYPE=Debug
   cmake --build build --config Debug
   ctest --test-dir build --build-config Debug --output-on-failure
   ```

The first run may download and build GoogleTest. CTest should list
`TennisGame.GetScore` as `Not Run (Disabled)`.

If a command reports a missing compiler or CMake, install that prerequisite
and run the setup commands again.

Setup is complete when the build succeeds and CTest discovers the disabled
test.

## Make command reference

Make is optional. Run `make` or `make help` to list these commands in the
terminal.

| Command             | Result                                    |
| ------------------- | ----------------------------------------- |
| `make all`          | Build and run the test suite              |
| `make help`         | Show the Make command reference           |
| `make build`        | Configure and build without running tests |
| `make test`         | Build and run the test suite              |
| `make format`       | Format tracked C++ and header files       |
| `make format-check` | Check formatting without changing files   |
| `make clean`        | Remove generated build artifacts          |
