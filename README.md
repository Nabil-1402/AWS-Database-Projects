# AWS Database Projects

A collection of hands-on AWS database projects focused on developing practical experience with Amazon DynamoDB, AWS CloudShell, and the AWS Command Line Interface (CLI).

These projects explore how NoSQL data is structured, loaded, queried, and updated in DynamoDB. Each project includes a PDF report documenting the implementation process, key concepts, challenges, and lessons learned.

## Projects

| Project | Summary | Key skills |
| --- | --- | --- |
| [Load Data into DynamoDB](./Load-Data-Into-DynamoDB/legendary-aws-databases-dynamodb.pdf) | Created five DynamoDB tables and loaded multiple items using AWS CloudShell and CLI commands. Compared DynamoDB's flexible item-and-attribute model with relational database structures. | DynamoDB tables, partition keys, items and attributes, provisioned capacity, AWS CloudShell, AWS CLI, batch writes |
| [Query Data with DynamoDB](./Query-Data-From-DynamoDB/legendary-aws-databases-query.pdf) | Queried DynamoDB data through the AWS Management Console and CLI, explored partition and sort keys, and used a transaction to update related data atomically. | Key design, `get-item`, query options, strongly consistent reads, projection expressions, consumed capacity, transactions |

## Project 1: Load Data into DynamoDB

This project introduces DynamoDB's core data model and demonstrates how AWS resources can be managed through command-line tooling.

### What I did

- Created five DynamoDB tables.
- Used AWS CloudShell and the AWS CLI to create four tables programmatically.
- Loaded multiple records using `aws dynamodb batch-write-item`.
- Inspected items with different sets of attributes to understand DynamoDB's flexible schema.
- Explored read capacity units (RCUs), write capacity units (WCUs), and their effect on performance and cost.
- Compared DynamoDB's NoSQL model with a traditional relational database.

### Key takeaway

DynamoDB allows items in the same table to contain different attributes. This flexibility is useful when storing related records that do not all share an identical structure. Partition keys also help DynamoDB distribute data and retrieve targeted items efficiently.

## Project 2: Query Data with DynamoDB

This project builds on the first project by exploring data access patterns and transactional operations.

### What I did

- Created and populated DynamoDB tables for querying.
- Retrieved items through the AWS Management Console and AWS CLI.
- Used partition keys and sort keys to identify records.
- Explored query options including `--consistent-read`, `--projection-expression`, and `--return-consumed-capacity`.
- Investigated why a query using a non-key attribute could not be performed efficiently with the existing table design.
- Ran a transaction that added a comment and updated the related forum's comment count as one atomic operation.

### Key takeaway

DynamoDB table design should begin with the application's access patterns. Queries require the partition key, so retrieving data through a different attribute may require a secondary index or a redesigned key structure.

Transactions protect data consistency by ensuring that every grouped operation succeeds or the entire transaction is cancelled.

## Technologies Used

- Amazon DynamoDB
- AWS CloudShell
- AWS CLI
- AWS Management Console
- NoSQL data modelling

## Repository Structure

```text
AWS-Database-Projects/
├── Load-Data-Into-DynamoDB/
│   └── legendary-aws-databases-dynamodb.pdf
├── Query-Data-From-DynamoDB/
│   └── legendary-aws-databases-query.pdf
└── README.md
```

## Learning Outcomes

Through these projects, I developed a practical understanding of:

- The differences between NoSQL and relational data models.
- How DynamoDB stores data using tables, items, and attributes.
- How partition and sort keys influence data uniqueness and query capabilities.
- How to automate database operations using AWS CloudShell and the AWS CLI.
- How capacity settings relate to database performance and cost.
- How DynamoDB transactions maintain consistency across related operations.
- Why access patterns should guide DynamoDB table and key design.

## Author

**Nabil Ahmed**

- [GitHub](https://github.com/Nabil-1402)
- [LinkedIn](https://www.linkedin.com/in/nabil-ahmed-712b65278)

## Acknowledgements

These projects were completed as part of the [NextWork](https://learn.nextwork.org/) AWS learning programme.
