# Cyber-security-codes
# File Hashing Script

This Python script calculates the hash value (MD5, SHA-1, or SHA-256) of a given file. Hashing is often used in cybersecurity and data integrity verification to check if files have been tampered with or to verify file integrity.

## How to Use

1. Save the script to a file, for example, `filehash_gen.py`.
2. Ensure you have a file you want to hash, e.g., `testfile.txt`.

### Usage Example

Here’s an example of how to use the script:

```python
import hashlib

def create_example_file():
    content = """This is an example test file.
    It contains sample text for demonstration purposes."""

    with open("testfile.txt", "w") as file:
        file.write(content)

    print("testfile.txt created successfully.")


def hash_file(filename, algorithm='md5'):
    hash_func = hashlib.new(algorithm)
    with open(filename, 'rb') as file:
        while chunk := file.read(4096):
            hash_func.update(chunk)
    return hash_func.hexdigest()

create_example_file()
filename = "testfile.txt"
print("MD5:", hash_file(filename, 'md5'))
print("SHA-1:", hash_file(filename, 'sha1'))
print("SHA-256:", hash_file(filename, 'sha256'))
