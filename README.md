# `tftptest` - A TFTP Test Server
TODO

## List of TFTP Test Fault Cases
Below is a list of fault conditions one might want to test a TFTP client against:

1. RRQ timeout
1. WRQ timeout
1. File not found
1. Insufficient permissions (read)
1. Insufficient permissions (write)
1. Files larger than 65535 blocks - 65535 x 512 = 33,553,920 ≈ 34 MB (write)
1. Files larger than 65535 blocks - 65535 x 512 = 33,553,920 ≈ 34 MB (read)
1. File size exact multiple of 512 (write)
1. File size exact multiple of 512 (read)
1. Mid-transfer timeout - no DATA to ACK (read)
1. Mid-transfer timeout - no ACK to DATA (write)
1. Mid-transfer timeout - no ACK to final DATA (write)
1. Mid-transfer timeout - no final DATA < 512 bytes (read)
1. Duplicate final DATA packet (read)
1. Duplicate final ACK packet (write)
1. Duplicate DATA packet mid-transfer (read)
1. Duplicate ACK packet mid-transfer (write) - Sorcerer's Apprentice bug!
1. Error packet reception and termination of session (read) x7
1. Error packet reception and termination of session (write) x7
1. No ACK for DATA packet n but received ACK for DATA packet n+1 (write)
1. Dropped/skipped DATA packet n (read)
1. DATA packets out-of-order (read)
1. ACK packets out-of-order (write)
1. Invalid block # in ACK packet (write)
1. Invalid block # in DATA packet (read)
1. Invalid number of bytes in data packet (too many) (read)
1. Invalid number of bytes in data packet (does not match actual payload) (read)
1. Invalid opcode in packet (read)
1. Invalid opcode in packet (write)
1. Invalid error code in ERROR packet (write)
1. Invalid error code in ERROR packet (read)
1. Wrong transfer ID - incorrect src port of peer (read)
1. Wrong transfer ID - incorrect src port of peer (write)
