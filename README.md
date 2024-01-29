### Link Shortener Documentation

#### Design Overview:
The `LinkShortener` class is designed to provide a basic URL shortening service through a simple command-line interface. It utilizes two hash maps (`shortToLongMap` and `longToShortMap`) to efficiently map between short and long URLs. The design includes a basic hash function for generating short URLs and handles collisions by regenerating short URLs until a unique one is found.

#### Class Members:
1. **shortToLongMap**: A `HashMap` that maps short URLs to their corresponding long URLs.
2. **longToShortMap**: A `HashMap` that maps long URLs to their corresponding short URLs.

#### Methods:
1. **generateShortUrl(String longUrl)**:
   - Generates a short URL based on the hash code of the long URL.
   - Uses the first 6 characters of the hexadecimal representation of the hash code as the short URL.

2. **shortenUrl(String longUrl)**:
   - Shortens a long URL using the `generateShortUrl` method.
   - Handles collisions by regenerating short URLs until a unique one is found.
   - Updates both the `shortToLongMap` and `longToShortMap` with the mapping.

3. **expandUrl(String shortUrl)**:
   - Expands a short URL to its original long form by looking up the mapping in the `shortToLongMap`.
   - Returns a message if the short URL is not found.

4. **main(String[] args)**:
   - Implements a simple command-line interface for user interaction.
   - Allows users to choose between shortening a URL and expanding a short URL.
   - Utilizes a loop for continuous interaction until the user decides to exit.

#### Features:
1. **Collision Handling**:
   - The code addresses potential collisions by regenerating short URLs until a unique one is found.

2. **User Interaction**:
   - The program provides a straightforward command-line interface for users to shorten and expand URLs.

3. **Efficient Mapping**:
   - Uses two hash maps to efficiently map between short and long URLs.

#### Challenges Encountered:
1. **Hash Function Limitations**:
   - The code relies on the default `hashCode` method, which may have limitations in terms of avoiding collisions for certain input patterns. A more sophisticated hash function could be considered for improved collision avoidance.

2. **No Persistence**:
   - The current implementation does not persist data between program executions. If the program is terminated, all shortened URLs will be lost. Introducing a persistent storage solution could be a potential improvement.

3. **Security Considerations**:
   - The code does not address potential security concerns, such as validation of input URLs or protection against malicious attempts to manipulate the shortening process. Enhanced security measures should be considered for a production-level system.

### Conclusion:
The `LinkShortener` provides a basic and functional URL shortening service with room for improvements, such as a more robust hash function, persistent storage, and enhanced security measures.
