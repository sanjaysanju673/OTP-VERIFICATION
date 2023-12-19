# OTP-VERIFICATION
import pyotp
secret_key = pyotp.random_base32()
otp = pyotp.TOTP(secret_key)
user_otp = otp.now()
print(f"Generated OTP: {user_otp}")
user_input_otp = input("Enter the OTP: ")

if otp.verify(user_input_otp):
    print("OTP is valid. Authentication successful!")
else:
    print("OTP is invalid. Authentication failed.")
