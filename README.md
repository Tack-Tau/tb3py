# TB3PY

by Kevin F. Garrity and Kamal Choudhary

This is a python wrapper for the
[ThreeBodyTB.jl](http://github.com/usnistgov/ThreeBodyTB.jl) Julia
package, which runs two- and three-body tight-binding calculations for
materials.

Using the Julia version directly is the primary method for running the
code. However, I recognize that many materials science codes are written in
python. Therefore, I have created this wrapper to help people with no
Julia knowledge run the code using the
[PyJulia](https://github.com/JuliaPy/pyjulia) interface.

## Installation

1) Clone this distribution.

    ```
    git clone https://github.com/usnistgov/tb3py.git
    ```
    
2) Run the installation

    ```
    python setpu.py develop
    ```

Note that this can take a while and may use significant disk space. The code
will, if necessary, a) download & install Julia b) download & install
ThreeBodyTB.jl, and c) create a system image for fast loading.


3) Example usage :

    ```
    pytest tb3py/tests/test_ptop.py
    ```


For main documentation of ThreeBodyTB.jl, see [![](https://img.shields.io/badge/docs-dev-blue.svg)](https://pages.nist.gov/ThreeBodyTB.jl/)
This code is only the wrapper that downloads and installs that code.

## Performance Tips

- Julia can take advantage multiple threads. Try setting the environment variable below as appropriate for your machine.
    ```
    JULIA_NUM_THREADS=8
    export JULIA_NUM_THREADS
    ```

- Note that despite using pre-compilation where possible, some
  functions will run faster the second time you run them due to the
  jit.

- Note that you must delete the system image if you want to update the
  ThreeBodyTB.jl code and re-run the installation.
