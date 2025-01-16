# Database Structure
Entity-Relationship diagram for the database in the API. Please note that this document is subject to updates when the 
Analyst gives us updates on the project strucutre.
```mermaid
erDiagram

    user {
        VARCHAR(32) uid PK
        TEXT username
        TEXT email
        BLOB image
        VARCHAR(16) imageMimeType
        TEXT description
        VARCHAR(32) pronouns
        TEXT passwordHash
        BOOLEAN isAccountConfirmed
        %% check in future if OPT should be added %%
    }
        
    cat {
        VARCHAR(32) uid PK
        VARCHAR(128) name
        INTEGER age
        TEXT description
        DATE whenLastSeen
        VARCHAR(32) whereLastSeen
        VARCHAR(32) race
        VARCHAR(16) furColor
        INTEGER weight
        BOOLEAN isStray
        BLOB image
        VARCHAR(16) imageMimeType
        INTEGER price
        VARCHAR(32) owner FK
    }
    
    cartItem {
        VARCHAR(32) uid PK
        VARCHAR(32) owner FK
        VARCHAR(32) cat FK
    }

    wishListItem {
        VARCHAR(32) uid PK
        VARCHAR(32) owner FK
        VARCHAR(32) cat FK
    }
    
    user |o--o{ token : has
    user |o--o{ cat : owns
    user |o--o{ cartItem : wants
    user |o--o{ wishListItem : dreamsOfOwning
```

## Details on the Database
- **Type**: MariaDB

## SQL Schema
```sql
CREATE TABLE IF NOT EXISTS users(
    uid VARCHAR(32) PRIMARY KEY,
    username VARCHAR(32) NOT NULL,
    email VARCHAR(64) NOT NULL,
    image BLOB,
    imageMimeType VARCHAR(16),
    description TEXT,
    pronouns VARCHAR(32),
    passwordHash TEXT NOT NULL,
    isAccountConfirmed BOOLEAN NOT NULL DEFAULT FALSE
);

CREATE TABLE IF NOT EXISTS cats(
    uid VARCHAR(32) PRIMARY KEY,
    name VARCHAR(128) NOT NULL,
    age INTEGER,
    description TEXT,
    whenLastSeen DATE,
    whereLastSeen VARCHAR(32),
    race VARCHAR(32),
    furColor VARCHAR(16),
    weight INTEGER,
    isStray BOOLEAN,
    image BLOB,
    imageMimeType VARCHAR(16),
    price INTEGER,
    owner VARCHAR(32),
    FOREIGN KEY(owner) REFERENCES users(uid)
);

CREATE TABLE cartItems(
    uid VARCHAR(32) PRIMARY KEY,
    owner VARCHAR(32), cat VARCHAR(32),
    FOREIGN KEY(owner) REFERENCES users(uid),
    FOREIGN KEY(cat) REFERENCES cats(uid)
);

CREATE TABLE wishListItems(
    uid VARCHAR(32) PRIMARY KEY,
    owner VARCHAR(32), cat VARCHAR(32),
    FOREIGN KEY(owner) REFERENCES users(uid),
    FOREIGN KEY(cat) REFERENCES cats(uid)
);


CREATE TABLE cartItems(
    uid VARCHAR(32) PRIMARY KEY,
    owner VARCHAR(32), cat VARCHAR(32),
    FOREIGN KEY(owner) REFERENCES users(uid),
    FOREIGN KEY(cat) REFERENCES cats(uid)
);

CREATE TABLE wishListItems(
    uid VARCHAR(32) PRIMARY KEY,
    owner VARCHAR(32), cat VARCHAR(32),
    FOREIGN KEY(owner) REFERENCES users(uid),
    FOREIGN KEY(cat) REFERENCES cats(uid)
);

```


