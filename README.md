<img align="right" top="100" src="./asset.png">

# foundry-peppermint • ![license](https://img.shields.io/github/license/0xClandestine/foundry-peppermint?label=license) ![solidity](https://img.shields.io/badge/solidity-^0.8.13-lightgrey)

A **Clean**, **Robust** Template for Foundry Projects.

## Getting Started

Click [`use this template`](https://github.com/0xClandestine/foundry-peppermint/generate) to create a new repository with this repo as the initial state.

Or, if your repo already exists, run:
```sh
forge init --template https://github.com/0xClandestine/foundry-peppermint
git submodule update --init --recursive
forge install
```

## Creating a new test

I don't want to have to think about avoiding contract naming collision, so each new test file
is prefixed with a number, and all the contract names in that file have that same number as a suffix.

There's now a script to generate a new file with a contract and empty test function. Just run the following replacing `<test_name>` with the name of your test (file naming conventions apply, avoid spaces).  Or omit the test name to invoke _interactive mode_.

```sh
./newTest.sh <test name>
```

## Yul code

Occasionally it's helpful to generate the Yul intermediate representation to understand what's
happening underneath the hood. In that case, I'll just use a command like the following to
put the IR into the `./ir` dir. Using a `.sol` extension gives pretty decent syntax highlighting
for readability.

```
forge inspect Target16 ir >! ir/bytesArgLenCheck16.yul.sol
```

Yul code can be compiled with `solc --strict-assembly`.

## Blueprint

```ml
lib
├─ forge-std — https://github.com/foundry-rs/forge-std
├─ solbase — https://github.com/Sol-DAO/solbase
scripts
├─ Deploy.s.sol — Simple Deployment Script
src
├─ Greeter — A Minimal Greeter Contract
test
└─ Greeter.t — Exhaustive Tests
```


## Development

**Setup**
```bash
forge install
```

**Building**
```bash
forge build
```

**Testing**
```bash
forge test
```

## License

[AGPL-3.0-only](https://github.com/0xClandestine/foundry-peppermint/blob/master/LICENSE)


## Acknowledgements

- [solidity-sandbox](https://github.com/maurelian/solidity-sandbox)
- [foundry-peppermint](https://github.com/0xClandestine/foundry-peppermint)
- [foundry](https://github.com/foundry-rs/foundry)
- [solmate](https://github.com/Rari-Capital/solmate)
- [forge-std](https://github.com/brockelmore/forge-std)
- [forge-template](https://github.com/foundry-rs/forge-template)
- [foundry-toolchain](https://github.com/foundry-rs/foundry-toolchain)


## Disclaimer

_These smart contracts are being provided as is. No guarantee, representation or warranty is being made, express or implied, as to the safety or correctness of the user interface or the smart contracts. They have not been audited and as such there can be no assurance they will work as intended, and users may experience delays, failures, errors, omissions, loss of transmitted information or loss of funds. The creators are not liable for any of the foregoing. Users should proceed with caution and use at their own risk._