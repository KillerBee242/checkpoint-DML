# checkpoint-DML

**1. Insertion dans la table Customer :**

```sql
INSERT INTO Customer (Customer_id, customer_Name, customer_Tel)
VALUES ('C01', 'ALI', 71321009);

INSERT INTO Customer (Customer_id, customer_Name, customer_Tel)
VALUES ('C02', 'ASMA', 77345823);
```

**2. Insertion dans la table Product :**

```sql
INSERT INTO Product (Product_id, Product_Name, Category, Price)
VALUES ('P01', 'Samsung Galaxy S20', 'Smartphone', 3299);

INSERT INTO Product (Product_id, Product_Name, Category, Price)
VALUES ('P02', 'ASUS Notebook', 'PC', 4599);
```

**3. Insertion dans la table Orders :**

```sql
INSERT INTO Orders (Customer_id, Product_id, OrderDate, Quantity, Total_amount)
VALUES ('C01', 'P02', NULL, 2, 9198);

INSERT INTO Orders (Customer_id, Product_id, OrderDate, Quantity, Total_amount)
VALUES ('C02', 'P01', TO_DATE('28/05/2020', 'DD/MM/YYYY'), 1, 3299);
```

**Explications et points importants :**

*   **`INSERT INTO table_name (column1, column2, ...)` :**  Spécifie la table dans laquelle insérer et les colonnes concernées.
*   **`VALUES (value1, value2, ...)` :**  Fournit les valeurs à insérer dans les colonnes correspondantes.
*   **Guillemets simples :** Les valeurs de type chaîne de caractères (VARCHAR2) doivent être entourées de guillemets simples.
*   **`NULL` :**  Pour insérer une valeur nulle (comme `OrderDate` dans le premier enregistrement de `Orders`).
*   **`TO_DATE` :**  Pour insérer une date dans un format spécifique (ici 'DD/MM/YYYY').  C'est important car le format de date par défaut peut varier selon la configuration de la base de données.  Assurez-vous d'adapter le format si nécessaire.
*   **Ordre des insertions :** Il est crucial d'insérer d'abord les données dans les tables `Customer` et `Product` (les tables "parent") avant d'insérer dans la table `Orders` (la table "enfant"), car `Orders` contient des clés étrangères qui référencent les clés primaires de `Customer` et `Product`.
