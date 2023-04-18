## Microbit 504 Debugging

This repository contains data from several runs of the `copyhex`
program used to test transfers.

Two computers, micro:bits, and cables were used to test.

### Testing Setup

* Computer 1 (label D1): Acer Travelmate, P-series (TMP614-51-G2-5442) running
  Ubuntu Linux 22.04 with a custom kernel 6.0.7.

* Computer 2 (label D2): Dell unibody desktop running Windows 10
  Education build 1709 (managed on company domain). i5-8500 processor, 3.00 GHz.

* Two micro:bits 2.21 both running v0258-beta1-1-g5ecc8207. Labels:
  M1, M2.

* Two different USB cables (C1 and C2).

* On computer D1, both the left (label: U1) and right (label: U2)
  usb ports were tested. On computer D2 only one port was tested.


### Testing Results


* Run A (2023-04-17, left usb) (D1, M1, C1, U1)
    + Runs: 100. Failures: 7.
    + 2/100 - unable to decode hex file
    + 5/100 - transient
* Run B (2023-04-17 right usb) (D1, M1, C1, U2)
    + Runs: 100. Failures: 4.
    + 4/100 - transient
* Run C (2023-04-18, right usb) (C1, M2, C2, U2)
    + Runs: 100. Failures: 7.
    + 6/100 - transient
    + 1/100 - apparent corruption with `\x00` bytes in type?
* Run D attempts.
    + Four attempts at running the test script on Windows
    + Each one ends in an error after different amounts of time.
    * [5 success, 1 permission
      denied](serial_output_desktop_01_D2M2C2U2/script_output_with_error.txt)
    * [17 success, 1 invalid
      argument](serial_output_desktop_02_D2M2C2U2/script_output_with_error.txt)
    * [8 success, 1 permission
      denied](serial_output_desktop_03_D2M2C2U2/script_output_with_error.txt)
    * [6 success, 1 invalid
      argument](serial_output_desktop_04_D2M2C2U2/script_output_with_error.txt)

I think in my Windows environment, the testing script is not prepared
to handle the problems that come up.
