# TheArtOfUnitTesting-C

This project is aimed to apply principles described within book ["The Art of Unit Testing: with examples in C#"](https://www.amazon.com/Art-Unit-Testing-examples/dp/1617290890) to the C programming language by using different unit testing frameworks.

## CMock 

See https://github.com/ThrowTheSwitch/CMock

This framework uses `ruby` scipt anguage to parse header files of the ***Unit of Work***, and then it generares header and source files with a fake objects.

### Trouble 1

Got error when run `cmock.rb` script:

`cmock_file_writer.rb:30:in 'initialize': No such file or directory @ rb_sysopen - mocks/`

Solution: create destination folder for generated mock objects.

### Trouble 2

Depends on the `Unity` test framework.

Solution: Add `Unity` framework as dependency.

### Trouble 3

Leak of `CMakeLists.txt` files.

Solution: add custom `CMakeLists.txt` files to build `CMock` and `Unity` frameworks. 

