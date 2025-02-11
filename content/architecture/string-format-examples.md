# String.Format for numerics examples

## About this document

This document provides examples of numeric formatting in the **nanoFramework** CLR. The examples are part of the Unit Test Framework and can be found in the [CoreLibrary repository](https://github.com/nanoframework/CoreLibrary) as part of the [Arithmetic unit tests](https://github.com/nanoframework/CoreLibrary/blob/develop/Tests/NFUnitTestArithmetic/UnitTestFormat.cs).  When running the unit test for a specifier the example data is gathered and displayed in the Test Output after a successful test run. Each format specifier is attempted for the signed integers (SByte, Int16, Int32, Int64), unsigned integers (Byte, UInt16, UInt32, UInt64) and floating-point (Single/Double) number types.  Negative numbers are not attempted for unsigned integer types (n/a will appear), and the value must be within the range of the integer type (i.e. must be between -128 and +128 for SByte) otherwise n/a will appear.  The Decimal and Hexadecimal types ONLY support integer number types.  For all of the examples both upper and lower case versions of the specifier are tested, however only lower case g and x have any effect on the output.

## <a id="decimal">D-Decimal</a>

[Decimal Format Specifier](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-numeric-format-strings#DFormatString)

     Value Format SByte   Int16   Int32   Int64 Byte UInt16 UInt32 UInt64
       123 D        123     123     123     123  123    123    123    123
       123 d        123     123     123     123  123    123    123    123
       129 D        n/a     129     129     129  129    129    129    129
       129 d        n/a     129     129     129  129    129    129    129
      -129 D        n/a    -129    -129    -129  n/a    n/a    n/a    n/a
      -129 d        n/a    -129    -129    -129  n/a    n/a    n/a    n/a
       128 D        n/a     128     128     128  128    128    128    128
       128 d        n/a     128     128     128  128    128    128    128
      -128 D       -128    -128    -128    -128  n/a    n/a    n/a    n/a
      -128 d       -128    -128    -128    -128  n/a    n/a    n/a    n/a
      -128 D2      -128    -128    -128    -128  n/a    n/a    n/a    n/a
      -128 d2      -128    -128    -128    -128  n/a    n/a    n/a    n/a
      1234 D2       n/a    1234    1234    1234  n/a   1234   1234   1234
      1234 d2       n/a    1234    1234    1234  n/a   1234   1234   1234
     -1234 D        n/a   -1234   -1234   -1234  n/a    n/a    n/a    n/a
     -1234 d        n/a   -1234   -1234   -1234  n/a    n/a    n/a    n/a
      1234 D6       n/a  001234  001234  001234  n/a 001234 001234 001234
      1234 d6       n/a  001234  001234  001234  n/a 001234 001234 001234
     -1234 D6       n/a -001234 -001234 -001234  n/a    n/a    n/a    n/a
     -1234 d6       n/a -001234 -001234 -001234  n/a    n/a    n/a    n/a

## <a id="fixed">F-Fixed-point</a>

[Fixed-point Format Specifier](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-numeric-format-strings#FFormatString)

         Value Format   SByte        Int16        Int32        Int64     Byte      UInt16      UInt32      UInt64       Single       Double
           123 F       123.00       123.00       123.00       123.00   123.00      123.00      123.00      123.00       123.00       123.00
           123 f       123.00       123.00       123.00       123.00   123.00      123.00      123.00      123.00       123.00       123.00
           129 F          n/a       129.00       129.00       129.00   129.00      129.00      129.00      129.00       129.00       129.00
           129 f          n/a       129.00       129.00       129.00   129.00      129.00      129.00      129.00       129.00       129.00
          -129 F          n/a      -129.00      -129.00      -129.00      n/a         n/a         n/a         n/a      -129.00      -129.00
          -129 f          n/a      -129.00      -129.00      -129.00      n/a         n/a         n/a         n/a      -129.00      -129.00
           128 F          n/a       128.00       128.00       128.00   128.00      128.00      128.00      128.00       128.00       128.00
           128 f          n/a       128.00       128.00       128.00   128.00      128.00      128.00      128.00       128.00       128.00
           128 F4         n/a     128.0000     128.0000     128.0000 128.0000    128.0000    128.0000    128.0000     128.0000     128.0000
           128 f4         n/a     128.0000     128.0000     128.0000 128.0000    128.0000    128.0000    128.0000     128.0000     128.0000
          -128 F      -128.00      -128.00      -128.00      -128.00      n/a         n/a         n/a         n/a      -128.00      -128.00
          -128 f      -128.00      -128.00      -128.00      -128.00      n/a         n/a         n/a         n/a      -128.00      -128.00
          -128 F2     -128.00      -128.00      -128.00      -128.00      n/a         n/a         n/a         n/a      -128.00      -128.00
          -128 f2     -128.00      -128.00      -128.00      -128.00      n/a         n/a         n/a         n/a      -128.00      -128.00
          1234 F2         n/a      1234.00      1234.00      1234.00      n/a     1234.00     1234.00     1234.00      1234.00      1234.00
          1234 f2         n/a      1234.00      1234.00      1234.00      n/a     1234.00     1234.00     1234.00      1234.00      1234.00
         -1234 F          n/a     -1234.00     -1234.00     -1234.00      n/a         n/a         n/a         n/a     -1234.00     -1234.00
         -1234 f          n/a     -1234.00     -1234.00     -1234.00      n/a         n/a         n/a         n/a     -1234.00     -1234.00
          1234 F6         n/a  1234.000000  1234.000000  1234.000000      n/a 1234.000000 1234.000000 1234.000000  1234.000000  1234.000000
          1234 f6         n/a  1234.000000  1234.000000  1234.000000      n/a 1234.000000 1234.000000 1234.000000  1234.000000  1234.000000
         -1234 F6         n/a -1234.000000 -1234.000000 -1234.000000      n/a         n/a         n/a         n/a -1234.000000 -1234.000000
         -1234 f6         n/a -1234.000000 -1234.000000 -1234.000000      n/a         n/a         n/a         n/a -1234.000000 -1234.000000
        123.78 F3         n/a          n/a          n/a          n/a      n/a         n/a         n/a         n/a      123.780      123.780
        123.78 f3         n/a          n/a          n/a          n/a      n/a         n/a         n/a         n/a      123.780      123.780
        123.78 F1         n/a          n/a          n/a          n/a      n/a         n/a         n/a         n/a        123.8        123.8
        123.78 f1         n/a          n/a          n/a          n/a      n/a         n/a         n/a         n/a        123.8        123.8
     1234.8999 F3         n/a          n/a          n/a          n/a      n/a         n/a         n/a         n/a     1234.900     1234.900
     1234.8999 f3         n/a          n/a          n/a          n/a      n/a         n/a         n/a         n/a     1234.900     1234.900

## <a id="general">G-General</a>

[General Format Specifier](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-numeric-format-strings#GFormatString)

         Value Format    SByte    Int16    Int32    Int64 Byte  UInt16  UInt32  UInt64    Single    Double
           123 G           123      123      123      123  123     123     123     123       123       123
           123 g           123      123      123      123  123     123     123     123       123       123
           129 G           n/a      129      129      129  129     129     129     129       129       129
           129 g           n/a      129      129      129  129     129     129     129       129       129
          -129 G           n/a     -129     -129     -129  n/a     n/a     n/a     n/a      -129      -129
          -129 g           n/a     -129     -129     -129  n/a     n/a     n/a     n/a      -129      -129
           128 G           n/a      128      128      128  128     128     128     128       128       128
           128 g           n/a      128      128      128  128     128     128     128       128       128
           128 G4          n/a      128      128      128  128     128     128     128       128       128
           128 g4          n/a      128      128      128  128     128     128     128       128       128
          -128 G          -128     -128     -128     -128  n/a     n/a     n/a     n/a      -128      -128
          -128 g          -128     -128     -128     -128  n/a     n/a     n/a     n/a      -128      -128
          -128 G2     -1.3E+02 -1.3E+02 -1.3E+02 -1.3E+02  n/a     n/a     n/a     n/a  -1.3E+02  -1.3E+02
          -128 g2     -1.3e+02 -1.3e+02 -1.3e+02 -1.3e+02  n/a     n/a     n/a     n/a  -1.3e+02  -1.3e+02
          1234 G2          n/a  1.2E+03  1.2E+03  1.2E+03  n/a 1.2E+03 1.2E+03 1.2E+03   1.2E+03   1.2E+03
          1234 g2          n/a  1.2e+03  1.2e+03  1.2e+03  n/a 1.2e+03 1.2e+03 1.2e+03   1.2e+03   1.2e+03
         -1234 G           n/a    -1234    -1234    -1234  n/a     n/a     n/a     n/a     -1234     -1234
         -1234 g           n/a    -1234    -1234    -1234  n/a     n/a     n/a     n/a     -1234     -1234
          1234 G6          n/a     1234     1234     1234  n/a    1234    1234    1234      1234      1234
          1234 g6          n/a     1234     1234     1234  n/a    1234    1234    1234      1234      1234
         -1234 G6          n/a    -1234    -1234    -1234  n/a     n/a     n/a     n/a     -1234     -1234
         -1234 g6          n/a    -1234    -1234    -1234  n/a     n/a     n/a     n/a     -1234     -1234
        123.78 G3          n/a      n/a      n/a      n/a  n/a     n/a     n/a     n/a       124       124
        123.78 g3          n/a      n/a      n/a      n/a  n/a     n/a     n/a     n/a       124       124
      123.7841 G5          n/a      n/a      n/a      n/a  n/a     n/a     n/a     n/a    123.78    123.78
      123.7841 g5          n/a      n/a      n/a      n/a  n/a     n/a     n/a     n/a    123.78    123.78
      123.7851 G5          n/a      n/a      n/a      n/a  n/a     n/a     n/a     n/a    123.79    123.79
      123.7851 g5          n/a      n/a      n/a      n/a  n/a     n/a     n/a     n/a    123.79    123.79
        123.78 G5          n/a      n/a      n/a      n/a  n/a     n/a     n/a     n/a    123.78    123.78
        123.78 g5          n/a      n/a      n/a      n/a  n/a     n/a     n/a     n/a    123.78    123.78
        123.78 G4          n/a      n/a      n/a      n/a  n/a     n/a     n/a     n/a     123.8     123.8
        123.78 g4          n/a      n/a      n/a      n/a  n/a     n/a     n/a     n/a     123.8     123.8
     1234.8999 G5          n/a      n/a      n/a      n/a  n/a     n/a     n/a     n/a    1234.9    1234.9
     1234.8999 g5          n/a      n/a      n/a      n/a  n/a     n/a     n/a     n/a    1234.9    1234.9
     1234.8999 G6          n/a      n/a      n/a      n/a  n/a     n/a     n/a     n/a    1234.9    1234.9
     1234.8999 g6          n/a      n/a      n/a      n/a  n/a     n/a     n/a     n/a    1234.9    1234.9
     1234.8999 G7          n/a      n/a      n/a      n/a  n/a     n/a     n/a     n/a    1234.9    1234.9
     1234.8999 g7          n/a      n/a      n/a      n/a  n/a     n/a     n/a     n/a    1234.9    1234.9
     -1234.901 G7          n/a      n/a      n/a      n/a  n/a     n/a     n/a     n/a -1234.901 -1234.901
     -1234.901 g7          n/a      n/a      n/a      n/a  n/a     n/a     n/a     n/a -1234.901 -1234.901

## <a id="number">N-Number</a>

[Number Format Specifier](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-numeric-format-strings#NFormatString)

            Value Format   SByte         Int16         Int32         Int64     Byte       UInt16       UInt32       UInt64        Single        Double
              123 N       123.00        123.00        123.00        123.00   123.00       123.00       123.00       123.00        123.00        123.00
              123 n       123.00        123.00        123.00        123.00   123.00       123.00       123.00       123.00        123.00        123.00
              129 N          n/a        129.00        129.00        129.00   129.00       129.00       129.00       129.00        129.00        129.00
              129 n          n/a        129.00        129.00        129.00   129.00       129.00       129.00       129.00        129.00        129.00
             -129 N          n/a       -129.00       -129.00       -129.00      n/a          n/a          n/a          n/a       -129.00       -129.00
             -129 n          n/a       -129.00       -129.00       -129.00      n/a          n/a          n/a          n/a       -129.00       -129.00
              128 N          n/a        128.00        128.00        128.00   128.00       128.00       128.00       128.00        128.00        128.00
              128 n          n/a        128.00        128.00        128.00   128.00       128.00       128.00       128.00        128.00        128.00
              128 N4         n/a      128.0000      128.0000      128.0000 128.0000     128.0000     128.0000     128.0000      128.0000      128.0000
              128 n4         n/a      128.0000      128.0000      128.0000 128.0000     128.0000     128.0000     128.0000      128.0000      128.0000
             -128 N      -128.00       -128.00       -128.00       -128.00      n/a          n/a          n/a          n/a       -128.00       -128.00
             -128 n      -128.00       -128.00       -128.00       -128.00      n/a          n/a          n/a          n/a       -128.00       -128.00
             -128 N2     -128.00       -128.00       -128.00       -128.00      n/a          n/a          n/a          n/a       -128.00       -128.00
             -128 n2     -128.00       -128.00       -128.00       -128.00      n/a          n/a          n/a          n/a       -128.00       -128.00
             1234 N2         n/a      1,234.00      1,234.00      1,234.00      n/a     1,234.00     1,234.00     1,234.00      1,234.00      1,234.00
             1234 n2         n/a      1,234.00      1,234.00      1,234.00      n/a     1,234.00     1,234.00     1,234.00      1,234.00      1,234.00
            -1234 N          n/a     -1,234.00     -1,234.00     -1,234.00      n/a          n/a          n/a          n/a     -1,234.00     -1,234.00
            -1234 n          n/a     -1,234.00     -1,234.00     -1,234.00      n/a          n/a          n/a          n/a     -1,234.00     -1,234.00
             1234 N6         n/a  1,234.000000  1,234.000000  1,234.000000      n/a 1,234.000000 1,234.000000 1,234.000000  1,234.000000  1,234.000000
             1234 n6         n/a  1,234.000000  1,234.000000  1,234.000000      n/a 1,234.000000 1,234.000000 1,234.000000  1,234.000000  1,234.000000
            -1234 N6         n/a -1,234.000000 -1,234.000000 -1,234.000000      n/a          n/a          n/a          n/a -1,234.000000 -1,234.000000
            -1234 n6         n/a -1,234.000000 -1,234.000000 -1,234.000000      n/a          n/a          n/a          n/a -1,234.000000 -1,234.000000
         1234.567 N2         n/a           n/a           n/a           n/a      n/a          n/a          n/a          n/a      1,234.57      1,234.57
         1234.567 n2         n/a           n/a           n/a           n/a      n/a          n/a          n/a          n/a      1,234.57      1,234.57
        -1234.567 N2         n/a           n/a           n/a           n/a      n/a          n/a          n/a          n/a     -1,234.57     -1,234.57
        -1234.567 n2         n/a           n/a           n/a           n/a      n/a          n/a          n/a          n/a     -1,234.57     -1,234.57
        123456.78 N2         n/a           n/a           n/a           n/a      n/a          n/a          n/a          n/a    123,456.78    123,456.78
        123456.78 n2         n/a           n/a           n/a           n/a      n/a          n/a          n/a          n/a    123,456.78    123,456.78
     1234567.1210 N2         n/a           n/a           n/a           n/a      n/a          n/a          n/a          n/a  1,234,567.12  1,234,567.12
     1234567.1210 n2         n/a           n/a           n/a           n/a      n/a          n/a          n/a          n/a  1,234,567.12  1,234,567.12

## <a id="hexadecimal">X-Hexadecimal</a>

[Hexadecimal Format Specifier](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-numeric-format-strings#XFormatString)

     Value Format SByte  Int16    Int32            Int64 Byte UInt16 UInt32 UInt64
         0 X2        00     00       00               00   00     00     00     00
         0 x2        00     00       00               00   00     00     00     00
        +0 X          0      0        0                0    0      0      0      0
        +0 x          0      0        0                0    0      0      0      0
        -0 X          0      0        0                0    0      0      0      0
        -0 x          0      0        0                0    0      0      0      0
        12 X          C      C        C                C    C      C      C      C
        12 x          c      c        c                c    c      c      c      c
        12 X2        0C     0C       0C               0C   0C     0C     0C     0C
        12 x2        0c     0c       0c               0c   0c     0c     0c     0c
       127 X         7F     7F       7F               7F   7F     7F     7F     7F
       127 x         7f     7f       7f               7f   7f     7f     7f     7f
       129 X        n/a     81       81               81   81     81     81     81
       129 x        n/a     81       81               81   81     81     81     81
       128 X4       n/a   0080     0080             0080 0080   0080   0080   0080
       128 x4       n/a   0080     0080             0080 0080   0080   0080   0080
      1234 X        n/a    4D2      4D2              4D2  n/a    4D2    4D2    4D2
      1234 x        n/a    4d2      4d2              4d2  n/a    4d2    4d2    4d2
      1234 X6       n/a 0004D2   0004D2           0004D2  n/a 0004D2 0004D2 0004D2
      1234 x6       n/a 0004d2   0004d2           0004d2  n/a 0004d2 0004d2 0004d2
      -127 X         81   FF81 FFFFFF81 FFFFFFFFFFFFFF81  n/a    n/a    n/a    n/a
      -127 x         81   ff81 ffffff81 ffffffffffffff81  n/a    n/a    n/a    n/a
      -128 X         80   FF80 FFFFFF80 FFFFFFFFFFFFFF80  n/a    n/a    n/a    n/a
      -128 x         80   ff80 ffffff80 ffffffffffffff80  n/a    n/a    n/a    n/a
      -128 X4      0080   FF80 FFFFFF80 FFFFFFFFFFFFFF80  n/a    n/a    n/a    n/a
      -128 x4      0080   ff80 ffffff80 ffffffffffffff80  n/a    n/a    n/a    n/a
      -129 X        n/a   FF7F FFFFFF7F FFFFFFFFFFFFFF7F  n/a    n/a    n/a    n/a
      -129 x        n/a   ff7f ffffff7f ffffffffffffff7f  n/a    n/a    n/a    n/a
     -1234 X        n/a   FB2E FFFFFB2E FFFFFFFFFFFFFB2E  n/a    n/a    n/a    n/a
     -1234 x        n/a   fb2e fffffb2e fffffffffffffb2e  n/a    n/a    n/a    n/a
     -1234 X6       n/a 00FB2E FFFFFB2E FFFFFFFFFFFFFB2E  n/a    n/a    n/a    n/a
     -1234 x6       n/a 00fb2e fffffb2e fffffffffffffb2e  n/a    n/a    n/a    n/a
