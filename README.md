# **Molecule Protocol v3**

Molecule Protocol v3 is an **open-source data ownership tooling project** that empowers users to own, control, and manage their data across four data types: **Proprietary Data**, **Behavioral Data**, **Verifiable Credential Data**, and **Derivative Data**. This README covers **Behavioral Data**, providing the framework to securely capture, store, and share user-generated interaction data in a privacy-preserving, decentralized ecosystem.

The protocol integrates **Arweave**, **DIDs**, **encryption**, and **AI agents**, utilizing the **DOPA token** (**Data Ownership Protocol Agent**) to incentivize and govern data sharing.

---

## **Key Features**

1. **Behavioral Data Ownership**:
   - Captures user interactions (e.g., clicks, views) locally by default.
   - Encrypted backups to **Arweave** ensure data permanence and accessibility.

2. **Data Sovereignty**:
   - Users retain full control over data, with **DIDs** enabling cross-device synchronization.
   - Sharing permissions are managed via **SmartWeave Contracts**, ensuring transparency.

3. **Two-Tower Recommendation Engine**:
   - Uses behavioral data to generate personalized feeds for content (news, products, and videos, etc.).
   - Combines user embeddings and content embeddings in a shared vector space.

4. **Decentralized Marketplace**:
   - Enables users to share data securely and receive compensation in **DOPA tokens**.

---

## **Architecture Overview**

### **1. Behavioral Data Capture**
- Data is structured as JSON and captured locally on the user's device.
- Example Schema:
  ```json
  {
    "event_type": "click",
    "content_id": "arweave_cid_5678",
    "timestamp": "2024-12-18T12:00:00Z",
    "metadata": {
      "device": "mobile",
      "location": "US"
    }
  }
  ```

### **2. Storage and Aggregation**
- **Local Storage**: Behavioral data remains private by default.
- **Encrypted Backup to Arweave**:
  - Data is encrypted with user-specific keys before being stored.
  - Tagged with the user's **DID** for cross-device aggregation.

### **3. Data Sharing and Governance**
- **SmartWeave Contracts**:
  - Handle user authorization for data sharing.
  - Specify access scope, duration, and compensation terms.
- **Marketplace**:
  - Enables businesses to request user data for AI training or analytics.
  - Users receive **DOPA tokens** as compensation.

### **4. Content Storage**
- Content (e.g., articles, products, and videos, etc.) is stored on Arweave with unique **CIDs**.
- Metadata includes tags, embeddings, and publisher information.
- Example Metadata:
  ```json
  {
    "cid": "arweave_cid_1234",
    "type": "video",
    "tags": ["technology", "AI"],
    "embedding": [0.23, 0.45, 0.67]
  }
  ```

### **5. Two-Tower Recommendation Engine**
- **User Tower**:
  - Generates user embeddings from behavioral data.
  - Trained locally or in privacy-preserving environments.
- **Item Tower**:
  - Generates content embeddings from metadata stored on Arweave.
- **Inference**:
  - Matches user and content embeddings to generate personalized feeds.

---

## **Technical Stack**

### **Core Components**
1. **Data Capture**:
   - Local tracking via SDKs (browser, mobile).
   - Offline-first with encrypted backups to Arweave.
2. **Storage**:
   - Behavioral data: Encrypted JSON on Arweave.
   - Content: Metadata and embeddings stored with **CIDs**.
3. **Identity**:
   - **DIDs** for user identification and cross-device synchronization.
4. **Data Sharing**:
   - **SmartWeave Contracts** for permission management.
   - Tokenized marketplace with **DOPA tokens**.

### **Tools and Frameworks**
- **Arweave**: Permanent decentralized storage.
- **ArDrive**: User-friendly interface for managing data.
- **DIDs**: Decentralized Identifiers for user ownership.
- **TensorFlow/PyTorch**: AI models for feed generation.
- **FAISS**: Fast similarity search for recommendations.

---

## **Example Workflow**

### **1. Behavioral Data Workflow**
1. **Capture**:
   - Track user interactions locally.
   - Example: User clicks a product.
   - Captured Event:
     ```json
     {
       "event_type": "click",
       "content_id": "arweave_cid_5678"
     }
     ```
2. **Encrypt and Store**:
   - Data is encrypted locally and backed up to Arweave.
3. **Data Sharing**:
   - User authorizes access via SmartWeave Contract.
   - DOPA tokens are distributed as compensation.

### **2. Feed Generation**
1. **Training**:
   - User embeddings (behavioral data) and content embeddings (Arweave metadata) are trained in a Two-Tower model.
2. **Inference**:
   - Compute similarity between embeddings to rank and recommend content.

---

## **DOPA Token**

- **Utility**:
  - Payment for data access.
  - Staking for ecosystem governance.
- **Incentives**:
  - Rewards users for sharing data.
  - Drives adoption and governance.

### **DOPA Tokenomics**

#### **Token Overview**
- **Total Supply**: 1 billion tokens.
- **Launch Mechanism**: Default bonding curve on [Protocol.land](https://protocol.land), ensuring token price increases as supply decreases.
- **Primary Utility**:
  - **Incentivize Data Sharing**: Rewards for users contributing behavioral data.
  - **Access Behavioral Data**: Payment for AI agents and companies to access user-shared data.
  - **Governance**: Token holders vote on ecosystem improvements and fee structures.

#### **Key Stakeholders and Token Flows**
1. **Users**:
   - **Role**: Data providers; own and control their behavioral data.
   - **Token Flow**:
     - Earn tokens for sharing behavioral data with authorized parties.
     - Pay tokens for value-added services like analytics or advanced recommendations.
   - **Rewards Mechanism**:
     - Flat rewards based on shared data volume.
     - Bonus rewards for high-value interactions (e.g., frequent, high-quality data).

2. **AI Agents/Developers**:
   - **Role**: Build and use tools for feed generation or analytics.
   - **Token Flow**:
     - Pay tokens to access user behavioral data (via SmartWeave contracts).
     - Receive tokens as grants for building ecosystem tools.
   - **Access Fees**:
     - Dynamic pricing based on requested data scope and duration.

3. **Ecosystem Participants**:
   - **Role**: Operate infrastructure and maintain protocol services (e.g., validators, SmartWeave execution).
   - **Token Flow**:
     - Earn transaction fees for facilitating SmartWeave contract operations.
   - **Fee Breakdown**:
     - 5% transaction fees for data-sharing contracts (adjustable via governance).

4. **Governance**:
   - Token holders decide:
     - Reward distribution structure.
     - Fee adjustments for ecosystem operations.
     - Future roadmap priorities.

#### **Example Token Flow**
- **User A** authorizes sharing behavioral data with AI Agent B for feed generation.
- **AI Agent B** pays **100 DOPA tokens** via a SmartWeave contract.
- Tokens are distributed as:
  - **80 tokens** to User A (data provider).
  - **10 tokens** to ecosystem participants (transaction fees).
  - **10 tokens** to a governance fund for future grants.

---

### **Codebase for Behavioral Data Management**

The repository will be similar to the original `ao.zip` code but designed for managing **behavioral data**. Below is the structure and key components.

#### **Repository Structure**
```
behavioral-data-toolkit/
├── contracts/
│   ├── SmartWeaveBehavioralDataContract.js
├── src/
│   ├── index.js
│   ├── utils/
│   │   ├── encryption.js
│   │   ├── arweaveUpload.js
│   └── components/
│       ├── dataCapture.js
│       ├── dataBackup.js
├── examples/
│   ├── uploadBehavioralData.js
│   ├── accessBehavioralData.js
└── README.md
```

---

### **Core Functionalities**

#### **1. Behavioral Data Toolkit**
Provides tools to:
- **Capture Behavioral Data**:
  - SDK for apps to locally capture behavioral events.
  - Example behavioral events:
    - Clicks, views, purchases.
    - Metadata: device, location, timestamp.

- **Encrypt and Backup to Arweave**:
  - Automatically encrypt data locally before uploading to Arweave.
  - Users can manage their backups via ArDrive.

#### **2. SmartWeave Access Contracts**
- Smart contracts define:
  - Scope of access (data type, duration).
  - Payment terms (in DOPA tokens).
- Example:
  ```javascript
  const contract = {
    id: "behavioral-data-contract",
    owner: "user_arweave_wallet",
    authorizedParties: ["ai_agent_wallet"],
    accessDuration: "30d",
    fee: 100, // DOPA tokens
  };
  ```

---

### **Code Examples**

#### **1. Capturing Behavioral Data**
```javascript
const dataCapture = require("./src/components/dataCapture");

dataCapture.trackEvent({
  eventType: "click",
  contentId: "arweave_cid_5678",
  metadata: { device: "mobile", location: "US" },
});
```

#### **2. Encrypt and Backup Data**
```javascript
const { encryptData, uploadToArweave } = require("./src/utils/encryption");

(async () => {
  const eventData = {
    eventType: "view",
    contentId: "arweave_cid_1234",
    timestamp: Date.now(),
  };

  // Encrypt data
  const encryptedData = await encryptData(eventData, userPrivateKey);

  // Upload to Arweave
  const cid = await uploadToArweave(encryptedData);
  console.log(`Data uploaded with CID: ${cid}`);
})();
```

#### **3. Data Sharing via SmartWeave**
```javascript
const SmartWeave = require("./contracts/SmartWeaveBehavioralDataContract");

(async () => {
  const contract = new SmartWeave({
    userWallet: "user_wallet_address",
    dopaFee: 100,
    accessDuration: "30d",
    authorizedParties: ["ai_agent_wallet"],
  });

  // Deploy contract
  await contract.deploy();
  console.log("SmartWeave Contract Deployed");
})();
```

---

## **Quick Start**

### **1. Capture Behavioral Data**
Integrate the Molecule Protocol SDK:
```javascript
Molecule.trackEvent({
  type: "click",
  contentId: "arweave_cid_5678",
  metadata: { device: "mobile" }
});
```

### **2. Backup to Arweave**
Use the ArDrive API to encrypt and store data.

### **3. Authorize Data Sharing**
Deploy SmartWeave Contracts to manage permissions:
```solidity
contract DataSharing {
  mapping(address => bool) public authorized;

  function authorize(address entity) external {
    authorized[entity] = true;
  }

  function revoke(address entity) external {
    authorized[entity] = false;
  }
}
```

---

## **Future Roadmap**

1. **Support for All Data Types**:
   - Expand tooling for proprietary, verifiable credential, and derivative data.
2. **Federated Learning**:
   - Enable local model training for enhanced privacy.
3. **Advanced Tokenomics**:
   - Introduce staking mechanisms and governance models.

---

Molecule Protocol v3 represents the next evolution of data ownership, empowering users to control and monetize their behavioral data while enabling advanced AI-driven recommendations.

Note: Moving project from Github to Protocol.Land, code will be available by end of December 2024.
