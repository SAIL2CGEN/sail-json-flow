# SAIL to JSON Workflow

This repository is meant to be a starting point for going through the SAIL to JSON workflow. The goal for the repo is to provide the necessary tools and instructions to go through the workflow in a organized and streamlined manner.

## Steps to Build and Compile
Most of the below instructions are from the [JSON.md](https://github.com/ThinkOpenly/sail-riscv/blob/JSON/doc/JSON.md) inside the `sail-riscv` repo but expanded upon to give more detail and clarity
1.  Clone the necessary repos
    - The necessary repos can cloned by running the provided [clone.sh](./clone.sh) script
      ```
      ./clone.sh
      ```
2.  Install SAIL through opam if not yet installed
    - Follow the ["How to install Sail"](./sail/INSTALL.md) instructions in INSTALL.md in the sail repo up until ["Installing development versions of Sail"](https://github.com/ThinkOpenly/sail/blob/json/INSTALL.md#installing-development-versions-of-sail) section (next step will go over installing development version)
3.  Change SAIL version to the one in the [sail](./sail) repository to add json functionality
    - Make sure you are in the [top directory](./) of this repo which by default should be named sail-json-flow
    - To change the SAIL version to have JSON functionality run:
      ```
      opam pin add sail
      ```
    - Later if you want to remove the pin and revert to latest released opam package run:
      ```
      opam pin remove sail
      ```
4. Build the json output from the RISC-V SAIL specification
    - Set up the environment for running the SAIL compiler
      ```
      eval $(opam env)
      ```
    - Navigate into the [sail-riscv](./sail-riscv/) direcotory, which contains the RISC-V `.sail` files, by running:
      ```
      cd sail-riscv
      ```
    - Use the [Makefile](sail-json-flow/sail-riscv/Makefile) to build the RISC-V json file:
      ```
      make json
      ```
    - Example of created json is [here](./sail-riscv-out.json)