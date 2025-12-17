# NVGT Pwned Passwords Checker

A simple library for NVGT to check if a password has been leaked in data breaches.

It uses the [Have I Been Pwned](https://haveibeenpwned.com/) API.

## Is it Safe?

Yes! Your password is **never sent** to the internet. The library uses k-anonymity - only the first 5 characters of the SHA1 hash are sent, so your real password stays safe on your device.

## How to Use

1. Include the library in your script:
```
#include "pwned_passwords.nvgt"
```

2. Check a password:
```
string error;
int result = check_pwned_password("your_password", error);

if (result == PWNED_ERROR) {
    // Something went wrong, check error message
} else if (result == PWNED_SAFE) {
    // Password is safe, not found in breaches
} else {
    // Password was found! result = how many times it was leaked
}
```

## Example

See `password checker.nvgt` for a simple example that shows an input box and checks the password.

## License

MIT License - see [LICENSE](LICENSE) file.

## Contributing

Edits and contributions are very welcome! Feel free to open issues or pull requests.

---

If you find this useful, you can support me here:

[![PayPal](https://img.shields.io/badge/PayPal-Donate-blue)](https://paypal.me/hmdqr/)
