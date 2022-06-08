.. raw:: html

    <img src="https://github.com/jcmgray/quimb/blob/develop/docs/_static/quimb_logo_title.png" width="450px">
(but not quite)


About this backend:

- General-use quantum information library (QUIMB) repurposed for a GPU-accelerated tensor network backend for medium-large scale noisy quantum circuit simulation.
- Supports NVIDIA GPUs, tested on Lambda workstation (2x NVIDIA RTX A6000).
- Requires `cupy` to interface between Python and CUDA.
- Written in Python, slow on CPU-only nodes (compared to C/C++ backends).
- Uses opt_einsum format for contraction path logic; can be interfaced with cuQuantum/cuTensorNet.


**NOTES**:

- Offloading matrix multiplications to GPU has very little overhead with the right preparation, and allows them to be executed *much* more quickly. 
- There is currently an issue with the `copy()` function in the TN classes, especially when doing a `virtual` copy. This copy function is pointed to `deepcopy` in all inherited classes to circumvent this issue; however, this slows down sampling and it may be necessary to implement virtual TN handling within the child classes as well. 


The **official documentation of QUIMB**, the original software package, can be found at: `<http://quimb.readthedocs.io/en/latest/>`_. 
