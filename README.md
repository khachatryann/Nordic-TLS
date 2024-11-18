# PSA TLS

The PSA TLS program shows how to perform a TLS handshake and send encrypted messages with Cortex-M Security Extensions (CMSE) enabled, in both Non-Secure Processing Environment (NSPE) and Secure Processing Environment (SPE).

## The sample performs the following operations:

- Configuration of the PSA TLS sample as either a server or client.
- TLS handshake initiation and message exchange:
  - As a server, it waits for the "ClientHello" message and initiates the handshake.
  - As a client, it attempts to connect to the server and sends the "ClientHello" message.
- Certificate management:
  - Certificates can be signed with ECDSA or RSA, with ECDSA being the default.
  - TLS certificates and keys are stored securely when running with CMSE.  
- Cipher suite selection:
  - Supports most TLS v1.2 cipher suites, excluding certain combinations like RSA and AES256 in CMSE-enabled applications
- TAP adapter functionality:
  - The program uses TAP adapters in Linux to send Ethernet frames to a connected PC. 
  
## Testing

After programming the sample to your development kit, complete the following steps to test it:

1. Connect a terminal emulator like nRF Connect Serial Terminal to the serial port.
2. Compile and program the application.
3. Observe the logs from the application using the terminal emulator.
4. Depending on the configuration, use OpenSSL to perform the client-server handshake or observe the behavior of the sample as a server or client.