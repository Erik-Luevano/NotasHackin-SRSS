The Rust saga continues? I ask you, can I borrow that, pleeeeeaaaasseeeee?Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/babfbee79718a6363826ba86300173ffde6d81577e9dd07d4130c53a7eecf6c3/fixme2.tar.gz).

Hints:
1.-https://doc.rust-lang.org/book/ch04-02-references-and-borrowing.html

### Solucion:

```
Nos dan otra carpeta a la cual le debemos hacer correcciones a un archivo main:

──(erik㉿kali)-[~/fixme1/src]
└─$ tar -xzf fixme2.tar.gz 
                                                                                
┌──(erik㉿kali)-[~/fixme1/src]
└─$ cd fixme2 
                                                                                
┌──(erik㉿kali)-[~/fixme1/src/fixme2]
└─$ cd src    
                                                                                
┌──(erik㉿kali)-[~/fixme1/src/fixme2/src]
└─$ nano main.rs 
                                                                                
┌──(erik㉿kali)-[~/fixme1/src/fixme2/src]
└─$ cat main.rs                
use xor_cryptor::XORCryptor;

fn decrypt(encrypted_buffer:Vec<u8>, borrowed_string: &mut String){ // How do we pass values to a function that we want to change?

    // Key for decryption
    let key = String::from("CSUCKS");

    // Editing our borrowed value
    borrowed_string.push_str("PARTY FOUL! Here is your flag: ");

    // Create decrpytion object
    let res = XORCryptor::new(&key);
    if res.is_err() {
        return; // How do we return in rust?
    }
    let xrc = res.unwrap();

    // Decrypt flag and print it out
    let decrypted_buffer = xrc.decrypt_vec(encrypted_buffer);
    borrowed_string.push_str(&String::from_utf8_lossy(&decrypted_buffer));
    println!("{}", borrowed_string);
}


fn main() {
    // Encrypted flag values
    let hex_values = ["41", "30", "20", "63", "4a", "45", "54", "76", "01", "1c", "7e", "59", "63", "e1", "61", "25", "0d", "c4", "60", "f2", "12", "a0", "18", "03", "51", "03", "36", "05", "0e", "f9", "42", "5b"];

    // Convert the hexadecimal strings to bytes and collect them into a vector
    let encrypted_buffer: Vec<u8> = hex_values.iter()
        .map(|&hex| u8::from_str_radix(hex, 16).unwrap())
        .collect();

    let mut party_foul = String::from("Using memory unsafe languages is a: "); // Is this variable changeable?
    decrypt(encrypted_buffer, &mut party_foul); // Is this the correct way to pass a value to a function so that it can be changed?
}

Basicamente solo faltaban > mut

┌──(erik㉿kali)-[~/fixme1/src/fixme2/src]
└─$ cargo build
   Compiling crossbeam-utils v0.8.20
   Compiling rayon-core v1.12.1
   Compiling either v1.13.0
   Compiling crossbeam-epoch v0.9.18
   Compiling crossbeam-deque v0.8.5
   Compiling rayon v1.10.0
   Compiling xor_cryptor v1.2.3
   Compiling rust_proj v0.1.0 (/home/erik/fixme1/src/fixme2)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 6.42s
                                                                                
┌──(erik㉿kali)-[~/fixme1/src/fixme2/src]
└─$ cargo run  
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.01s
     Running `/home/erik/fixme1/src/fixme2/target/debug/rust_proj`
Using memory unsafe languages is a: PARTY FOUL! Here is your flag: 

picoCTF{4r3_y0u_h4v1n5_fun_y31?}
      
```