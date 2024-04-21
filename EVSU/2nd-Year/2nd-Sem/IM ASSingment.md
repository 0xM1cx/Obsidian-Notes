SHAWN MICHAEL SUDARIA - BSIT 2B
**Customer**

| Customer_ID | F_Name | L_Name | Customer_Address | Customer_Email     |
| ----------- | ------ | ------ | ---------------- | ------------------ |
| Cust001     | Bob    | Smith  | 123 Broadway Dr  | bsmith@gmail.com   |
| Cust002     | Jill   | Thomas | 12 Kellogg ave   | jthomas@gmail.com  |
| Cust003     | Bob    | Smith  | 5 maple street   | smith5@hotmail.com |
**Subscription**

| Subscription ID | Customer ID | Email Subscription |
| --------------- | ----------- | ------------------ |
| Sub001          | Cust001     | Baseball           |
| Sub002          | Cust001     | Basketball         |
| Sub003          | Cust002     | Baseball           |
| Sub004          | Cust003     | Golf               |
**Catalog**

| Catalog ID | Customer ID | Mail Catalog |
| ---------- | ----------- | ------------ |
| Cat001     | Cust001     | Basketball   |
| Cat002     | Cust001     | Golf         |
| Cat003     | Cust002     | Baseball     |
| Cat004     | Cust003     | Golf         |
| Cat005     | Cust003     | Baseball     |
**Manufacturer**

| Manufacturer ID | Manufacturer Name | Manufacturer Addresss |
| --------------- | ----------------- | --------------------- |
| Man001          | Spaulding         | 1 Spaulding Drive     |
| Man002          | Louisvile slugger | 345 Slugger ave       |
| Man003          | Rawlings          | 23 Rawlings Court     |
| Man004          | Titleist          | 1234 Titleist Road    |

**Products**

| Product ID | Product Name | Product Details | Product Cost | Manufacturer ID |
| ---------- | ------------ | --------------- | ------------ | --------------- |
| Prod001    | Basketball   | 29.5 INCHES     | $25          | Man001          |
| Prod002    | Bat          | 33 INCHES       | $35          | Man002          |
| Prod003    | Softball     | 4 Path          | $6           | Man003          |
| Prod004    | Bat          | 32 INCHES       | $45          | Man003          |
| Prod005    | Golf Balls   | 1 Dozen         | $44          | Man004          |
| Prod006    | Basketball   | 1 Dozen         | $44          | Man004          |
**Order Details**

| Order ID | Customer ID | Order Date | Order Total |
| -------- | ----------- | ---------- | ----------- |
| Ord001   | Cust001     | 09/08/2018 | $60         |
| Ord002   | Cust001     | 12/05/2018 | $25         |
| Ord003   | Cust002     | 10/08/2018 | $57         |
| Ord004   | Cust003     | 12/08/2018 | $88         |
| Ord005   | Cust003     | 12/08/2018 | $88         |
**Line Details****

| Line Id | Order ID | Product ID | Quantity | Total |
| ------- | -------- | ---------- | -------- | ----- |
| L001    | Ord001   | Prod001    | 1        | $25   |
| L002    | Ord001   | Prod002    | 1        | $35   |
| L003    | Ord002   | Prod001    | 1        | $25   |
| L004    | Ord003   | Prod003    | 2        | $12   |
| L005    | Ord003   | Prod004    | 1        | $45   |
| L006    | Ord04    | Prod005    | 2        | $88   |
| L007    | Ord005   | Prod006    | 2        | $88   |


## Activity 3
The objective is to mitigate/reduce the redundancy of the head of the family. One head for the entire family.

```sql
DSWDForm(
	ID
	FormType
	FH_ID
);
```

```
FamilyHead(
	FH_ID, 
	LAF_ID, 
	L_name, 
	F_name, 
	M_name, 
	Name_EXT, 
	B_Date, 
	MotherMaidenName,  
	CardPresented, 
	NumSenior,
	NumVulnMothers,
	NumPWD,
	Others
); 
```

```
FamInfo(
	FamMem_ID, 
	FH_ID, 
	F_name, 
	L_Name, 
	Relation, 
	Age, 
	Sex, 
	Education, 
	Occupation, 
	Remarks
);
```

```mysql
PersonalDetails(
	PD_ID,
	FH_ID,		
	Age,
	CardNumber,
	Phone,
	Net_Income,
	Sex,
	Occupation,
	Adderss,
	Birthplace
);
```

```
LocationAffectedFam(
	LAF_ID, 
	Region, 
	Province, 
	District, 
	Barangay, 
	City, 
	EvacCenter
);
```

```
Receiver(
	RID,
	FamMem_ID,
	Type,
	QTY,
	COST,
	Provider
);
```