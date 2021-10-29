# Multiplicative-Inverse-Rust 
This rust code calculates the modular multiplicative inverse of a number making use the Euclidean algorithm.

    /*code that calculates the Modular multiplicative 
    inverse of a number using the Euclidean Algorithm*/ 

    fn mod_inv(a: isize, module: isize) -> isize {

    let mut mn = (module, a);
    let mut xy = (0, 1);
   
    while mn.1 != 0 {
      xy = (xy.1, xy.0 - (mn.0/mn.1) * xy.1);
      mn = (mn.1, mn.0 % mn.1);
    }
    //implementation of euclidean algorithm
    while xy.0 < 0 {
      xy.0 += module;
    }
    xy.0
    }
    //driver code
    fn main() {
      //function call
    println!("{}", mod_inv(29, 90)) /*input your interger and modulo respectively*/
    }
