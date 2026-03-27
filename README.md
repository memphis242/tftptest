# `tftptest` - A TFTP Test Server
This is a TFTP server that supports simulating a variety of TFTP faults for the sake of TFTP client testing (see full list below). Although it can be used as a TFPT server, it is really not designed for that purpose.

A guiding principle in developing this test TFTP server is to keep it as focused and as simple as possible while supporting the ability to use this in (thorough) automated testing of a TFTP client application.

- Only a single client is supported - the TFTP client app that you're trying to test
- Performance is prioritized but only as far as testing necessitates
- Minimal flexibility beyond TFTP fault simulation is supported (e.g., TFTP root directory, listening port/IP address)

## Basic Usage
```bash
TODO
```

## List of TFTP Test Fault Cases
Below is a list of fault conditions one might want to test a TFTP client against:

1. RRQ timeout
2. WRQ timeout
3. File not found
4. Insufficient permissions (read)
5. Insufficient permissions (write)
6. Files larger than 65535 blocks - 65535 x 512 = 33,553,920 ≈ 34 MB (write)
7. Files larger than 65535 blocks - 65535 x 512 = 33,553,920 ≈ 34 MB (read)
8. File size exact multiple of 512 (write)
9. File size exact multiple of 512 (read)
10. Mid-transfer timeout - no DATA to ACK (read)
11. Mid-transfer timeout - no ACK to DATA (write)
12. Mid-transfer timeout - no ACK to final DATA (write)
13. Mid-transfer timeout - no final DATA < 512 bytes (read)
14. Duplicate final DATA packet (read)
15. Duplicate final ACK packet (write)
16. Duplicate DATA packet mid-transfer (read)
17. Duplicate ACK packet mid-transfer (write) - Sorcerer's Apprentice bug!
18. Arbitrary error packet reception and termination of session (read) x7
19. Arbitrary error packet reception and termination of session (write) x7
20. No ACK for DATA packet n but received ACK for DATA packet n+1 (write)
21. Dropped/skipped DATA packet n (read)
22. DATA packets out-of-order (read)
23. ACK packets out-of-order (write)
24. Invalid block # in ACK packet (write)
25. Invalid block # in DATA packet (read)
26. Invalid number of bytes in data packet (too many) (read)
27. Invalid number of bytes in data packet (does not match actual payload) (read)
28. Invalid opcode in packet (read)
29. Invalid opcode in packet (write)
30. Invalid error code in ERROR packet (write)
31. Invalid error code in ERROR packet (read)
32. Wrong transfer ID - incorrect src port of peer (read)
33. Wrong transfer ID - incorrect src port of peer (write)
