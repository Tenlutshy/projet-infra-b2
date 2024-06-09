### DHCP

```powershell
# Import the DHCP Server module
Import-Module DHCPServer

# Variables
$DomainName = "boo.lan"
$DNSServer = "10.33.10.1"
$LeaseTime = 600 # Default lease time in seconds
$MaxLeaseTime = 7200 # Max lease time in seconds

# VLAN 10.33.10.0/24
$Scope1 = @{
    Name = "VLAN10.33.10.0"
    Subnet = "10.33.10.0"
    Mask = "255.255.255.0"
    StartRange = "10.33.10.1"
    EndRange = "10.33.10.253"
    Router = "10.33.10.254"
    Broadcast = "10.33.10.255"
}

# VLAN 10.33.20.0/28
$Scope2 = @{
    Name = "VLAN10.33.20.0"
    Subnet = "10.33.20.0"
    Mask = "255.255.255.240"
    StartRange = "10.33.20.1"
    EndRange = "10.33.20.13"
    Router = "10.33.20.14"
    Broadcast = "10.33.20.15"
}

# VLAN 10.33.30.0/29
$Scope3 = @{
    Name = "VLAN10.33.30.0"
    Subnet = "10.33.30.0"
    Mask = "255.255.255.248"
    StartRange = "10.33.30.1"
    EndRange = "10.33.30.5"
    Router = "10.33.30.6"
    Broadcast = "10.33.30.7"
}

# Function to add DHCP Scope
function Add-DHCPRange {
    param (
        $Scope
    )
    
    # Add the DHCP Scope
    Add-DhcpServerv4Scope -Name $Scope.Name -StartRange $Scope.StartRange -EndRange $Scope.EndRange -SubnetMask $Scope.Mask -State Active
    
    # Set the scope options
    Set-DhcpServerv4OptionValue -ScopeId $Scope.Subnet -DnsDomain $DomainName -DnsServer $DNSServer -Router $Scope.Router
    Set-DhcpServerv4Scope -ScopeId $Scope.Subnet -LeaseDuration ([TimeSpan]::FromSeconds($LeaseTime)) -MaxLeaseDuration ([TimeSpan]::FromSeconds($MaxLeaseTime))
}

# Add scopes
Add-DHCPRange -Scope $Scope1
Add-DHCPRange -Scope $Scope2
Add-DHCPRange -cope $Scope3

Write-Host "DHCP configuration completed."
```
