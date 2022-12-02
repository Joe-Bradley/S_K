

# S-K

## Introduction

**S-K is an on-chain peer to peer option trading protocol built on Ethereum network**

## **Business scenario**

### Covered Call

<img src="/Users/joebradley/Desktop/Cover-call-ADD-V1-551e4fa02e3a4af2bb0768956e8c0cc7.webp" alt="Cover-call-ADD-V1-551e4fa02e3a4af2bb0768956e8c0cc7" style="zoom:75%;" />

### **Write Option** 

```mermaid
graph LR
a(seller):::class1 --> |specify option parameter and transfer MMD to option contract|b([blockchain]):::class2
b -->|record the seller and the option info|a(seller):::class1
classDef class1 fill:#ffaf;
classDef class2 fill:#00ccff;
classDef class3 fill:#ffe7ba;
classDef class4 fill:#ff83fa;
```

### **Buy Option**

```mermaid
graph LR
b([blockchain]):::class2 --> |receive option|c(buyer):::class4
c-->|pay premium cMMD|b
b -->|transfer premium cMMD|a(seller):::class1
classDef class1 fill:#ffaf;
classDef class2 fill:#00ccff;
classDef class3 fill:#ffe7ba;
classDef class4 fill:#ff83fa;
```

### **Exercise**

```mermaid
graph LR
c(buyer):::class4 --> |pay strike price cMMD|b([blockchain]):::class2
b --> |receive MMD|c
b -->|transfer strike price cMMD|a(seller):::class1
classDef class1 fill:#ffaf;
classDef class2 fill:#00ccff;
classDef class3 fill:#ffe7ba;
classDef class4 fill:#ff83fa;
```

### **Retrive & Cancel**

```mermaid
graph LR
b([blockchain]):::class2 --> |get MMD back |a(seller):::class1
classDef class1 fill:#ffaf;
classDef class2 fill:#00ccff;
classDef class3 fill:#ffe7ba;
classDef class4 fill:#ff83fa;
```

## Contract Information

| contract      | address                                    |
| ------------- | ------------------------------------------ |
| option        | 0xdB491786f7e1BDf8BA4a49089f9Fd580706505CF |
| stable_coin   | 0x5f4576A8Cf609c9104353eB75f67023C7488ceed |
| unstable_coin | 0xC2283AA608b5347555EDd7dDA5DC7BEA95025636 |
|               | 0xA0D3af97D8265112F74D68C21211B277a83E7BAF |

## **How to Use**

- prepare environment
  - cd Back-end
    - npm install --save-dev @openzeppelin/contracts
    - npm install dotenv
  - cd Front-end
    - npm install
- run tests
  - cd Back-end
    - npx hardhat test
- deploy contract
  - cd Back-end
    - npx hardhat run scripts/deploy.ts --network etherdata
- start webpage
  - cd Front-end
    - npm start

## Further Imporvement

we move from (peer to peer) to (peer to pool)

#### Liqiudity pool & Option buying

```mermaid
graph LR
a(provider):::class1 --> |ETH| b((Liqiudity pool)):::class2
d(liquidity provider):::class3 --> |any MMD tocken|b
b --> |issue tocken with option info|c(option buyer):::class4
c --> |pay premium|b
classDef class1 fill:#ffaf;
classDef class2 fill:#00ccff;
classDef class3 fill:#ffe7ba;
classDef class4 fill:#ff83fa;
```

#### Exercise Option

```mermaid
graph LR
b((Liqiudity pool)):::class2
b --> |receive ETH|c(option buyer):::class4
c --> |pay strike|b
classDef class1 fill:#ffaf;
classDef class2 fill:#00ccff;
classDef class3 fill:#ffe7ba;
classDef class4 fill:#ff83fa;
```

