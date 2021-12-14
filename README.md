# Attacks on MtA using small Paillier

This project is a proof-of-concept for the small Paillier attack on threshold ECDSA protocols [GG18](https://eprint.iacr.org/2019/114.pdf) and [GG20](https://eprint.iacr.org/2020/540.pdf).
The details of this attack are presented in our [paper](https://eprint.iacr.org/2021/1621.pdf), section 2.3.

We stress that the library we are using to demonstrate the attack, is not susceptible to it, as Paillier size check is present in the code.
We commented out the check to show that without it the implementation would be vulnerable.

As described in the paper, we were able to choose Paillier `N` close to `q` and successfully completed signatures by reconstructing 
correct values after MtA.

## Run it

To run the project, [gmp](https://gmplib.org) is required. After cloning, run

`cargo test small_paillier_attack -- --nocapture`