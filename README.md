# port-scanner
import socket

target = input("Enter a target IP: ")

print(f"Scanning {target}...")

for port in range(1, 100):
    sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    result = sock.connect_ex((target, port))

    if result == 0:
        print(f"Port {port} is OPEN")
    
    sock.close()
