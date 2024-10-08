def encrypt(text, shift):
    result = ""
    for i in range(len(text)):
        char = text[i]
        if char.isupper():
            result += chr((ord(char) + shift - 65) % 26 + 65)
        elif char.islower():
            result += chr((ord(char) + shift - 97) % 26 + 97)
        else:
            result += char
    return result

def decrypt(text, shift):
    return encrypt(text, -shift)

plaintext = input("Masukkan teks yang ingin dienkripsi: ")
shift = int(input("Masukkan nilai shift: "))

encrypted_text = encrypt(plaintext, shift)
decrypted_text = decrypt(encrypted_text, shift)

print(f"\nTeks Asli: {plaintext}")
print(f"Teks Terenkripsi: {encrypted_text}")
print(f"Teks Terdekripsi: {decrypted_text}")
