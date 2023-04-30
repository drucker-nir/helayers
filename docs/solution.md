A generic flow for designing an FHE solution:

1. Identify and define the application to be executed using FHE.
2. Collect and compare the properties of different application implementations.
3. Define the entities and their roles in the chosen solutions.
4. Identify the capabilities of the entities in terms of bandwidth and CPU capabilities.
5. Identify whether the entities should use hybrid encryption.
6. Refine the threat model.
7. Identify where and how to use a KMS solution.

**Steps 1 and 2** narrow down the number of possible implementations and focus the solution designer on specific requirements for key sizes. For every such implementation, the designer should re-evaluate Steps 3-7, and eventually choose the one that best meets the design criteria. 

**Step 3, The different entities.** In Step 3, the solution designer should define the [entities](security.md) involved in the applications, e.g., unique persons, or groups of entities such as companies or organizations. For example, in [Scenario 3](security.md), the designer can choose the model owner as all the employees of company *CompA*, while setting the users as the users of *CompA*. Now, for every FHE key, the designer should set the entities that are allowed to use it. In the above example, the employees should have access to the secret and public keys, while CompA users should have access only to the public keys. 

**Step 4, Bandwidth and compute capabilities.** The entities' bandwidth and compute capabilities define the type of application they can run. For example, we cannot expect an IoT device-based entity to perform massive computations. On the other hand, when an entity has large compute powers it can perform some pre-computations on the data and eliminate some possibly slower FHE computations from the server. In this way, it can reduce the overall latency and costs of running the application on a cloud environment and even reduce the overall bandwidth. 

**Step 5, Using hybrid encryption**. Hybrid encryption is recommended when the end devices can suffer from latency, bandwidth, or battery issues. In this case, it is better to leave the complex computations to the powerful server. Even though there may be fast low-end software/hardware device implementations of HE algorithms, these are not always available to the solution designer, who will not likely purchase a large fleet of IoT devices while replacing its current fleet. If the decision to use the hybrid encryption is taken, the designer should still consider the following two aspects. 

- Using a standard symmetric encryption cipher such as AES, can result in a very high decryption latency given the cryptographic solutions available today. While this is expected to improve it may take time until such solutions are available and can operate at scale.
- Faster symmetric encryption ciphers are not yet standardized and therefore can lead to compliance issues. 

**Step 6,7, Refine the threat model and identify the KMS capabilities.** By now, the designer already defined the solution's different keys and the entities who should gain access to each one of them. It is left to define the level of trust expected from the cloud server. Specifically, we refer to three different trust definitions for the users: a) private data; b) secret keys; c) evaluation and public keys. 

Handling public and evaluation keys. The solutions below assume that the cloud uses the evaluation and public keys during the HE computations. Thus, at least the HE service application should have access to these keys. We recommend that only this service get access to the evaluation keys, and only the solution's users be granted access to the public key. The reason is that HE schemes are malleable and using these practices reduces the overall attack surface.

Handling secret keys. Similar to modern symmetric encryption solutions, different levels of trust can be considered. The most strict scenario is when the cloud provider is completely untrusted, i.e., we do not want the cloud to be able to see  the secret keys. Trivially, this is achieved by maintaining a private KMS, which comes with some maintenance costs that can be high when operating at scale. For example, it requires generating and uploading the evaluation keys to the cloud, which can result in high bandwidth consumption. 

It is possible to move the burden of managing a KMS service to the cloud by relaxing the trust assumptions. For example, by assuming that only a certain "small" part of the cloud is trusted i.e., the KMS. Here, the KMS may generate the secret keys or envelope keys and may be able to use them to decrypt the user's data. Under the following two trust assumptions, we may have a trustworthy solution:

- The KMS deletes the keys after generating them, and it does not hold a copy of these keys. 
- The keys or their encryption are stored in a separate location from the KMS. This can be a different cloud service, a different cloud, or even at the user's end. 

Another option is to ask the cloud KMS to generate the secret keys without revealing them to the users, i.e., the secret keys never leave the KMS. Here,  all HE decryption operations are performed by the KMS and sent encrypted to the users by using some symmetric encryption mechanism e.g., [TLS 1.3](https://datatracker.ietf.org/doc/html/rfc8446). In this construction, we need to trust the authorization and authentication mechanisms provided by the KMS to ensure that the KMS does not send confidential data to unauthorized entities.
