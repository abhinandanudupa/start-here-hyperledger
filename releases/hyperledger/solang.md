---
layout: default
title: solang
parent: Hyperledger
grand_parent: Releases
has_children: false
permalink: /releases/hyperledger/solang
---

# solang <span class="fs-3 right-align">[GitHub](https://github.com/hyperledger/solang){: .btn .mr-4 }</span>


<div>
    <table>
        <tr>
            <td colspan="2">
                <b>
                    v0.1.13: Genoa
                </b>
            </td>
        </tr>
        <tr>
            <td>
                <span class="chip">
                    v0.1.13
                </span>
            </td>
            <td>
                ### Changed
- Introduce sub-commands to the CLI. Now we have dedicated sub-commands for
  `compile`, `doc`, `shell-completion` and the `language-server`, which makes
  for a cleaner CLI.
  [seanyoung](https://github.com/seanyoung)
- On Solana, emitted events are encoded with Borsh encoding following the Anchor
  format.
  [LucasSte](https://github.com/LucasSte)
- The ewasm target has been removed, since ewasm is not going to implemented on
  Ethereum. The target has been reused for an new EVM target, which is not complete
  yet.
  [seanyoung](https://github.com/seanyoung)
- Substrate: Concrete contracts must now have at least one public function. A
  public function is in a contract, if it has public or external functions, if
  it has a receive or any fallback function or if it has public storage items
  (those will yield public getters). This aligns solang up with `ink!`.
  [xermicus](https://github.com/xermicus)

### Added
- Solana v1.11 is now supported.
  [seanyoung](https://github.com/seanyoung)
- On Solana, programs now use a custom heap implementation, just like on
  Substrate. As result, it is now possible to `.push()` and `.pop()` on
  dynamic arrays in memory.
  [seanyoung](https://github.com/seanyoung)
- Arithmetic overflow tests are implemented for all integer widths,
  [salaheldinsoliman](https://github.com/salaheldinsoliman)
- Add an NFT example for Solana
  [LucasSte](https://github.com/LucasSte)
- Add a wrapper for the Solana System Program
  [LucasSte](https://github.com/LucasSte)
- The selector for functions can be overriden with the `selector=hex"abcd0123"`
  syntax.
  [seanyoung](https://github.com/seanyoung)
- Shell completion is available using the `solang shell-completion` subcommand.
  [xermicus](https://github.com/xermicus)
- Add support for the `create_program_address()` and `try_find_program_address()`
  system call on Solana
  [seanyoung](https://github.com/seanyoung)
- Substrate: The `print()` builtin is now supported and will write to the debug
  buffer. Additionally, error messages from the `require` statements will now be
  written to the debug buffer as well. The Substrate contracts pallet prints the
  contents of the debug buffer to the console for RPC ("dry-run") calls in case
  the `runtime::contracts=debug` log level is configured.
  [xermicus](https://github.com/xermicus)

### Fixed
- DocComments `/** ... */` are now permitted anywhere.
  [seanyoung](https://github.com/seanyoung)
- Function calls to contract functions via contract name are no longer possible,
  except for functions of base contracts.
  [xermicus](https://github.com/xermicus)

Signed-off-by: Sean Young <sean@mess.org>
            </td>
        </tr>
    </table>
    <a href="https://github.com/hyperledger/solang/releases/tag/v0.1.13" class=".btn">
        View on GitHub
    </a>
    <span class="right-align">
        Created At 2022-09-16 20:19:02 +0000 UTC
    </span>
</div>
