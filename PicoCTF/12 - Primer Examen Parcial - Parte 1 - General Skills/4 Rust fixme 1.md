Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag!Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz).

Hints:
1.-Cargo is Rust's package manager and will make your life easier. See the getting started page [here](https://doc.rust-lang.org/book/ch01-03-hello-cargo.html)
2.-[println!](https://doc.rust-lang.org/std/macro.println.html)
3.-Rust has some pretty great compiler error messages. Read them maybe?

### Solucion

```

Nos proporcionan una carpeta que con cargo build no coree bien por errores de sintaxis:

use xor_cryptor::XORCryptor;

fn main() {
    // Key for decryption
    let key = String::from("CSUCKS"); < Faltaba comilla // How do we end statements in Rust?

    // Encrypted flag values
    let hex_values = ["41", "30", "20", "63", "4a", "45", "54", "76", "01", "1c", "7e", "59", "63", "e1", "61", "25", "7f", "5a", "60", "50", "11", "38", "1f", "3a", "60", "e9", "62", "20", >

    // Convert the hexadecimal strings to bytes and collect them into a vector
    let encrypted_buffer: Vec<u8> = hex_values.iter()
        .map(|&hex| u8::from_str_radix(hex, 16).unwrap())
        .collect();

    // Create decrpytion object
    let res = XORCryptor::new(&key);
    if res.is_err() {
        return; < estrito mal ret // How do we return in rust?
    }
    let xrc = res.unwrap();

    // Decrypt flag and print it out
    let decrypted_buffer = xrc.decrypt_vec(encrypted_buffer);
    println!(
        "{}:?", < No tenia las llaves// How do we print out a variable in the println function? 
        String::from_utf8_lossy(&decrypted_buffer)
    );
}

ahora si deja hacer:
──(erik㉿kali)-[~/fixme1/src]
└─$ cargo build            
   Compiling rust_proj v0.1.0 (/home/erik/fixme1)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.41s
                                                                                
┌──(erik㉿kali)-[~/fixme1/src]
└─$ cargo run  
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.01s
     Running `/home/erik/fixme1/target/debug/rust_proj`
picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}:?
```