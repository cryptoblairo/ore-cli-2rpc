# Ore CLI Blairo

A custom command line interface for the Ore program whose customized to send less transactions to RPCs. (Actually using v1.1.1 ore cli version)

## Requirements

### Install Rust

To install my custom Ore CLI, you will need to have the **Rust** programming language installed. You can **install Rust** by following the instructions on the [Rust website](https://www.rust-lang.org/tools/install).

```sh
curl https://sh.rustup.rs -sSf | sh
```

### Install Solana

If you don't have Solana client installed yet, run the following commands

```sh
sh -c "$(curl -sSfL https://release.solana.com/v1.18.4/install)"
```

### Install the custom rpc

Install the ore client 2 rpc

```sh
cargo install ore-cli-blairo
```

## How to use ?

Use the command **ore2blairo** instead of **ore**.

### An example
```sh
ore2blairo mine \
    --rpc your_rpc \
    --keypair ~/.config/solana/id.json \
    --priority-fee 10000 \
    --threads 4 \
    --confirm-delay 3000 \
    --gateway-delay 2000 \
    --gateway-retries 50 \
    --dynamic-fee-url your_helius_or_triton_rpc \
    --dynamic-fee-strategy "helius" \
    --dynamic-fee-max 100000
```

### 'confirm_delay' & 'gateway_delay' options

You can add the **confirm_delay** & the **gateway_delay** (both optionnal) options to increase or decrease the sending rate to your rpc. 

By default, **confirm_delay** is at 3000 milliseconds and **gateway_delay** is at 2000 milliseconds.

If you have **low** credits with your rpc, I will suggest that you use a **gateway_delay** of 3000 milliseconds & a **confirm_delay** of 4000 milliseconds.
If you have **high** credits with your rpc, I will suggest that you use a **gateway_delay** of 500 milliseconds & a **confirm_delay** of 1500 milliseconds.

### 'gateway-retries' option

You can add the gateway-retries option (optionnal) to increase or decrease the number of time that you will submit a hash. No recommendation for this one, but don't set it to high, **by default** it's at **100**.

## Warnings

This project is developed by me and I am **not** a professional Rust developer, so use with **caution**. Always monitor your rpc credits.

## Donation & Tips

I am accepting donations and tips at this solana adress (ORE, SOL, USDC) :
**AwdcrnSqdzdEdsGkx2f2zxNA4dENBDjMdpBtMtVDCrKc**