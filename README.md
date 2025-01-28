# Transparent service framework

### Preamble

In environment with lack of thrust to actor identity and motive we don't have enough tools to transparantly validate even open sourced service we are using.
With files that we are downloading form the trustworsy sources we have hash sum for file that can be calculated on user side to verify that this is exactly the same file.
With complex service including platform based on IaC components and userfacing web service we have limited tooling to verify is code shared in public actually the same code that working on the servers.

### Framework goal

The objective of this project is to establish a trustworthy and transparent verification framework for validating that a deployed system accurately reflects its source code, infrastructure configurations, and intended state.

Modern platforms are composed of various components, including codebases, infrastructure-as-code (IaC) definitions, containerized services, and runtime configurations. While deployment processes can generate fingerprints of the expected and runtime states, these fingerprints often come from the same system under control, which introduces a critical trust issue: users have no independent assurance that the system was deployed correctly.

This project aims to solve this problem by enabling users to independently verify the deployed platform through the following mechanisms:

1. Generate a Trusted Fingerprint of the Expected State: During deployment, produce a cryptographically secure fingerprint of the source code, IaC definitions, and configurations. Digitally sign this fingerprint and publish it alongside the source artifacts for transparency and immutability.

2. Expose Verifiable Runtime State: Provide a way to query raw runtime information (e.g., container image hashes, configurations, infrastructure metadata) directly from the deployed platform. This ensures that the actual running system can be independently verified.

3. Facilitate User-Driven Validation: Offer tools for users to:
   * Retrieve the published expected fingerprint.
   * Query the runtime environment for its state.
   * Compute and compare the runtime fingerprint with the expected one to validate the integrity of the deployment.

By bridging the gap between expected and runtime states, this project empowers end-users to validate deployments independently, fostering trust, transparency, and compliance in modern platform deployments.

### Key Benefits

* Trust: Users can confirm that the deployed system aligns with the source code and configurations.
* Transparency: Publish cryptographically signed fingerprints for public verification.
* Independence: Validation tools enable users to calculate and compare fingerprints without relying solely on the provider.