# SMB Enumeration Findings

## Target
172.17.0.2

## Key Findings
- SMB service accessible
- Anonymous login allowed
- Shared directories exposed
- OS and NetBIOS information leaked

## File Upload Test
A test file was created and uploaded to confirm write access.

## Security Risk
Open SMB shares can lead to data theft, malware uploads, and lateral movement.

## Mitigation
- Disable anonymous SMB access
- Enforce strong authentication
- Restrict share permissions

