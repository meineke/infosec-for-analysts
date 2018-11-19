
~~~mermaid
sequenceDiagram
Participant Client
Participant Server
Client --> Server: (Client hello)
Client ->> Server: "I support TLS versions A,B,C"
Client ->> Server: "And I support cipher suites 1, 2, 3"
Server --> Client: (Server hello)
Server ->> Client: "We'll use TLS version 1.2"
Server ->> Client: "We'll use cipher suite xyz"
Server ->> Client: Server certificate
Note left of Client: Client decides <br/> whether it trusts <br/> server certificate
Client --> Server: Client generates symmetric session key
Client --> Server: Client encrypts session key with server's public key
Client ->> Server: (encrypted session key)
~~~