# Gift Processing Workflow

This document outlines the complete gift/donation processing workflow, including authorization levels, special gift types, and tax/acknowledgment handling.

```mermaid
flowchart TD
    A([Gift Received]) --> B{Amount?}

    B -->|Under $250\nOnline only| C([Auto Tax Receipt Only])

    B -->|$250 or more| D{Online or Offline?}

    D -->|ONLINE| E([Auto Receipt sent\nby system])
    D -->|OFFLINE| F{Prospect\nManaged?}

    E --> G{Prospect\nManaged?}

    %% ONLINE - Standard path
    G -->|No| H{Amount?}
    H -->|$250–$999| H1[Dir. of Donor Relations\nsigns combo letter]
    H -->|$1,000–$9,999| H2[AVP JK\nsigns combo letter]
    H -->|$10,000–$74,999| H3[VP SC\nsigns combo letter]
    H -->|$75,000+| H4[President FB\nsigns combo letter]

    %% ONLINE - Prospect managed
    G -->|Yes| I{Amount?}
    I -->|Under $1,000| I1[Prospect Mgr or\nSr. Dir. of Dev.\nsigns combo letter]
    I -->|$1,000–$9,999| I2[AVP JK\nsigns combo letter]

    H1 & H2 & H3 & H4 & I1 & I2 --> OL([Paper Tax/Ack\nCombo Letter sent])

    %% OFFLINE - Standard path
    F -->|No| J{Amount?}
    J -->|$250–$999| J1[Dir. of Donor Relations\nsigns combo letter]
    J -->|$1,000–$9,999| J2[AVP JK\nsigns combo letter]
    J -->|$10,000–$74,999| J3[VP SC\nsigns combo letter]
    J -->|$75,000+| J4[President FB\nsigns combo letter]

    %% OFFLINE - Prospect managed
    F -->|Yes| K{Amount?}
    K -->|Under $1,000| K1[Prospect Mgr or\nSr. Dir. of Dev.\nsigns combo letter]
    K -->|$1,000–$9,999| K2[AVP JK\nsigns combo letter]

    J1 & J2 & J3 & J4 & K1 & K2 --> OFL([Paper Tax/Ack\nCombo Letter sent])

    %% SPECIAL GIFT TYPE MODIFIERS
    OL & OFL --> MOD{Special Gift\nType?}

    MOD -->|Standard| DONE([✓ Done])

    MOD -->|Stock Gift| STK[Add to body:\nShares, High/Low/Median value\nTax/Ack Combo]
    MOD -->|IRA Gift| IRA[Add to body:\nIRA charitable distribution\nlanguage — Tax/Ack Combo]
    MOD -->|DAF Gift| DAF[Ack Only\nNO tax language\nConfirm with JK if needed]
    MOD -->|Legends Gala| GAL[Tax/Ack Combo\nAdd to body:\nTickets, tax-deductible amt,\nwhat purchased & donated to]
    MOD -->|Tribute Gift| TRIB{Tribute?}

    STK & IRA & DAF & GAL --> DONE

    TRIB -->|Donor| TRD[Tax/Ack Combo\nwith tribute language\nSigner per threshold]
    TRIB -->|Acknowledgee/Recipient| TRA[Ack Only\nNO tax language\nNotify of gift in their honor]

    TRD & TRA --> DONE

    %% Styles
    classDef terminal fill:#1B2E5E,color:#fff,stroke:#1B2E5E,rx:20
    classDef decision fill:#2E5090,color:#fff,stroke:#2E5090
    classDef action fill:#D6E4F7,color:#1B2E5E,stroke:#2E5090
    classDef special fill:#FDF3DC,color:#7A5700,stroke:#C8952A
    classDef warning fill:#D4EEEE,color:#0B4E4E,stroke:#0B6E6E
    classDef done fill:#1E7A4A,color:#fff,stroke:#1E7A4A,rx:20

    class A,C,E,OL,OFL terminal
    class B,D,G,H,I,J,K,F,MOD,TRIB decision
    class H1,H2,H3,H4,I1,I2,J1,J2,J3,J4,K1,K2,TRD,TRA action
    class STK,IRA,GAL special
    class DAF warning
    class DONE done
