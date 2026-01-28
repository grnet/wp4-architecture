# 6. Trust, Security & Governance

## 6.1 Trust Ecosystem
Relation to QTSP and Trust Registry.

## 6.2 Security Measures
Signatures, authentication, revocation, key lifecycle.



### 6.2.X PID and EBWOID Revocation Scenarios
A robust and harmonized revocation mechanism for PID and EBWOID is a critical component of the European Digital Identity Wallet ecosystem. This function is not merely a technicality; it is a fundamental pillar of trust, security, and legal compliance.

The essential first step in designing a comprehensive and responsive revocation system is to identify and categorize all potential situations that necessitate the invalidation of a PID or EBWOID. This analysis ensures that the resulting framework can address a wide range of real-world events, from user-initiated requests to administrative actions and security incidents.

#### 6.2.X.Y Common Triggers for PID and EBWOID Revocation
Several revocation triggers are common to both natural persons (PID) and legal persons (EBWOID). These events form the core set of scenarios the system must be prepared to handle:

* **Explicit User Request:** A direct request from the user or an authorized representative to revoke their data.
   * _Example: A change in ownership of a company could be a reason for authorized representatives to revoke the EBWOID._
     
* **Data Inaccuracy or Modification:** Revocation initiated by the provider when the holder's underlying data is found to be inaccurate or has been officially modified.
   * _Example: A user changes their last name and the PID needs to be reissued._
     
* **Regulatory Changes:** Revocation required by regulatory changes that result in an incompatible PID/EBWOID, such as required attribute added, attribute removed or renamed.
   * _Example:  A new obligatory attribute is introduced in the EBWOID following a new regulation._
     
* **Loss, Theft, or Compromise:** Notification that the user's credentials or authentication device has been lost, stolen, or otherwise compromised.
   * _Example: Theft of a YubiKey, potentially allowing adversaries to use a business's wallet_
     
* **Provider Revocation:** Revocation due to revocation of wallet unit certificate (e.g. as a result of Wallet Provider compromise) or PID/LPID Provider certificate.
   * _Example: A Wallet provider fails to meet mandatory security compliance standards, resulting in the withdrawal of their authorization to operate in the eIDAS Trust Framework and is thus not allowed to provide wallet solutions anymore._
     
* **Abusive or Fraudulent Use:** Detection of abusive, fraudulent, or unauthorized activities associated with the identity data.
   * _Example: An economic operator observes that the business wallet is used for unauthorized transactions by representatives of the company._
   * _Example2: A law enforcement agency asks the PID provider by court order for revoation of a criminal users' PID._
     
* **Prolonged Inactivity:** Revocation/Cancelling of reissuance due to extended periods of non-use, as defined by the provider's policy.
   * _Example: A new PID is issued to replace an expiring one, but the user fails to actively ano,,ccept or "pick up" the new credential within the allowed grace period, leading the         provider to revoke/cancel the unclaimed PID to prevent it from remaining in a pending state._
     
* **Violation of Service Terms:** A breach of contractual obligations, service terms of use, or other applicable regulations by the holder.
   * _Example: The EBWOID Issuers terms of service specify an annual fee for issued attestations which the business fails to pay._
     
* **End-of-life Revocation Events:** End of life lifecycle events for natural respectively legal persons.
  * _Example PID: Death of holder_
  * _Example EBWOID: Termination or dissolution of the legal entity/busienss activity such as liquidation of a company._



### 6.2.X Regulatory and Policy Framework: Article 5 Obligations
All activities and deliverables under this task are anchored in the legal framework established by the European Union. Specifically, Regulation (EU) 2024/2977 provides the legal requirements for the EUDI Wallet ecosystem. Article 5 of this regulation, titled “Revocation of personal identification data”, sets forth the foundational obligations for the revocation of personal identification data, establishing the non-negotiable legal baseline that this project will implement.

#### 6.2.X.Y Provider Obligations
The regulation places several key obligations on providers to ensure a transparent, secure, and reliable revocation process.

    1. Public Revocation Policies Providers are required to publish clear, written, and publicly accessible policies detailing their procedures for managing validity status and the specific conditions under which data will be revoked.
    2. Exclusive Revocation Authority The authority to revoke data is strictly limited. Only the provider that originally issued the PID or LPID is permitted to revoke it.
    3. Timely User Notification Following a revocation, providers must inform the affected user within 24 hours through a secure channel. The notification must be concise, easily accessible, and explain the reasons for the revocation in simple and clear language.
    4. Public Validity Status Providers must make the validity status of issued data publicly available. This requires the design of a highly-available, low-latency service endpoint, likely employing mechanisms like OCSP or CRLs, that can be queried without compromising user privacy through correlatable requests.
    5. Irreversibility Once data has been revoked, the action cannot be undone. This ensures finality and prevents the re-use of credentials that have been declared invalid.
    
#### 6.2.X.Y Conditions for Mandatory Revocation
Article 5, Paragraph 4, specifies the circumstances under which a provider is required to execute a revocation without delay:
    
  * Upon an explicit request from the wallet user to whom the data was issued.
  * If the wallet unit certificate associated with the issued data has been revoked.
  * In other specific situations defined by the provider within their publicly available policies.
    
These legal mandates define what must be done. The next step is to address the practical challenges of how to implement these rules across the diverse technical and organizational landscapes of the Member States.


## 6.3 Governance Responsibilities
Who owns what in the consortium.


