# Simulated-Firewall
IP addresses are blocked if they appear in the fire wall rules

"import random" this library is used t

def create_random_ip():
    return f"192.168.1.{random.randint(0,255)}"

def check_firewall_rules(ip,rules):
    for adress,actions in rules.items():
        if adress == ip:
            return actions
        
    return "Allow"

def main():
    firewall_rules = {
        "192.168.1.54" : "Block",
        "192.168.1.23" : "Block",
        "192.168.1.10" : "Block",
        "192.168.1.1" : "Block",
        "192.168.1.14" : "Block",
        "192.168.1.220" : "Block",
        "192.168.1.16" : "Block",
        "192.168.1.4" : "Block",
        "192.168.1.88" : "Block"
    }

    for i in range(15):
        ip_address = create_random_ip()
        permission = check_firewall_rules(ip_address,firewall_rules)
        print(f"Ip Address: {ip_address}, Action: {permission}")

if __name__ == "__main__":
    main()


