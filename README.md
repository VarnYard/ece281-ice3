# ECE 281 ICE 3: FullAdder with Top Level Design

**Fork** this repo.

[ICE 3 instructions](https://usafa-ece.github.io/ece281-book/ICE/ICE3.html)

Targeted toward Digilent Basys3. Make sure to install the [board files](https://github.com/Xilinx/XilinxBoardStore/tree/2018.2/boards/Digilent/basys3).

Tested on Vivado 2018.2.

---

## GitHub Actions Testbench

You can *optionally* enable Actions on your fork.

The workflow uses the [setup-ghdl-ci](https://github.com/ghdl/setup-ghdl-ci) GitHub action
to run a *nightly* build of [GHDL](https://ghdl.github.io/ghdl/).

First, the workflow uses GHDL to **analyze** all `.vhd` files in `src/hdl/`.

Then it **elaborates** the *any* entity with the name `*_tb`.

Finally, the workflow **runs** the simulation. If successful then it will quietly exit with a `0` code.
If any of the `assert` statements fail **with** `severity failure` then GHDL will cease the simulation and exit with non-zero code; this will also cause the workflow to fail.
Assert statements of other severity levels will be reported, but not fail the workflow.

![Full Adder 3 Switch 2 LED Waveform](https://github.com/VarnYard/ece281-ice3/assets/142039672/4f8483d7-6917-4203-820c-79b812a7b1a1)

Documentation Statement: I worked with C3C Shearer on my test bench and he helped me to realize that I needed to correspond the # of switches to a value on the LEDs. I did not make 
that connection prior to our conversation. I also used ChatGPT to try to troubleshoot a "black box" error for C3C Shearer's lab which was something I have never seen before and assumed 
was unrelated to his code. I have one line of code noted that I looked up on the internet but I do not have a link available anymore, it is commented out. 
