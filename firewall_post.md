## Windows Server Connections - reference for other systems

New-NetFirewallRule -DisplayName "Veeam UDP" -Direction Outbound -LocalPort 135,137-139,445 -Protocol UDP -Action Allow

New-NetFirewallRule -DisplayName "Veeam TCP" -Direction Outbound -LocalPort 135,137-139,445,6160,2500-3300,6161,6162,49152-65535 -Protocol TCP -Action Allow

#### Add DataDomain

New-NetFirewallRule -DisplayName "Veeam TCP DD" -Direction Outbound -LocalPort 111,2049,2052 -Protocol TCP -Action Allow

#### Add StoreOnce

New-NetFirewallRule -DisplayName "Veeam TCP DD" -Direction Outbound -LocalPort 9387,9388 -Protocol TCP -Action Allow

### Backup Server 

New-NetFirewallRule -DisplayName "Veeam UDP" -Direction Outbound -LocalPort 53 -Protocol UDP -Action Allow

New-NetFirewallRule -DisplayName "Veeam TCP" -Direction Outbound -LocalPort 443, 10443, 433, 902, 22, 1433, 80 -Protocol UDP -Action Allow

For remote management add 3389 to TCP

## Proxy Server

New-NetFirewallRule -DisplayName "Veeam UDP" -Direction Outbound -LocalPort 135,137-139,445 -Protocol UDP -Action Allow

New-NetFirewallRule -DisplayName "Veeam TCP" -Direction Outbound -LocalPort 135,137-139,445,6160,2500-3300,6161,6162,49152-65535,6210,443,902 -Protocol TCP -Action Allow

## Repository Server/ Gateway

New-NetFirewallRule -DisplayName "Veeam UDP" -Direction Outbound -LocalPort 135,137-139,445 -Protocol UDP -Action Allow

New-NetFirewallRule -DisplayName "Veeam TCP" -Direction Outbound -LocalPort 135,137-139,445,6160,2500-3300,6161,6162,49152-65535 -Protocol TCP -Action Allow

## Mount server, if seperate

New-NetFirewallRule -DisplayName "Veeam UDP" -Direction Outbound -LocalPort 135,137-139,445 -Protocol UDP -Action Allow

New-NetFirewallRule -DisplayName "Veeam TCP" -Direction Outbound -LocalPort 135,137-139,445,6160,2500-3300,6161,6162,49152-65535,6170,9401,22 -Protocol TCP -Action Allow

## MS Server running vPower NFS Service Connections

New-NetFirewallRule -DisplayName "Veeam UDP" -Direction Outbound -LocalPort 1058,1063,2049,111 -Protocol UDP -Action Allow

New-NetFirewallRule -DisplayName "Veeam TCP" -Direction Outbound -LocalPort 6160,6161,111,2500-3300 -Protocol TCP -Action Allow

## Tape server

New-NetFirewallRule -DisplayName "Veeam UDP" -Direction Outbound -LocalPort 135,137-139,445 -Protocol UDP -Action Allow

New-NetFirewallRule -DisplayName "Veeam TCP" -Direction Outbound -LocalPort 135,137-139,445,6160,2500-3300,6161,6162,49152-65535, 6166 -Protocol TCP -Action Allow

