# RDS Cross-Region Backup Automation Project

This project demonstrates the implementation of an automated RDS database backup solution that creates snapshots in one region and copies them to another region for disaster recovery purposes.

## Project Overview

The solution automates the process of:
- Creating RDS snapshots
- Copying snapshots across AWS regions
- Creating RDS instances from copied snapshots
- Scheduling automated daily backups using Lambda and CloudWatch Events

## Implementation Steps

### Step 1: Initial RDS Instance Setup
![Existing RDS Instance](screenshots/1%20existing%20RDS%20instance%20in%20Ireland%20region.png)

Shows the original RDS database instance running in the Ireland (eu-west-1) region that serves as the source database for our backup automation.

### Step 2: Manual Snapshot Creation
![Snapshot Creation](screenshots/2%20snapshot%20of%20main%20db%20instance%20created.png)

Demonstrates the creation of a manual snapshot from the main database instance. This snapshot serves as the baseline for cross-region replication.

### Step 3: Cross-Region Snapshot Copy
![Snapshot Copy](screenshots/3%20snapshot%20copied%20to%20a%20different%20region.png)

Shows the snapshot being copied to a different AWS region for disaster recovery purposes. This ensures data availability even if the primary region experiences issues.

### Step 4: Replica Database Creation
![Replica Database](screenshots/4%20replica%20db%20created%20in%20new%20region.png)

Displays the creation of a new RDS instance from the copied snapshot in the destination region, establishing a functional database replica.

### Step 5: Connection Verification
![Connection Test](screenshots/5%20new%20db%20instance%20connection%20successful.png)

Confirms successful connectivity to the newly created database instance in the destination region, validating the restoration process.

### Step 6: Retention Policy Configuration
![Retention Settings](screenshots/6%20retention%20period%20set.png)

Shows the configuration of snapshot retention policies to manage storage costs and comply with data retention requirements.

### Step 7: Lambda Function Implementation
![Lambda Function](screenshots/7%20lambda%20function%20created%20for%20automated%20backup.png)

Demonstrates the creation of a Lambda function that automates the entire backup process, including snapshot creation and cross-region copying.

### Step 8: IAM Permissions Setup
![IAM Permissions](screenshots/8%20provide%20necessary%20permissions%20to%20lambda%20role.png)

Shows the configuration of necessary IAM permissions for the Lambda function to perform RDS operations, including snapshot creation and cross-region copying.

### Step 9: CloudWatch Event Scheduling
![CloudWatch Event](screenshots/9%20cloudwatch%20event%20trigger%20added%20to%20lambda%20function.png)

Displays the setup of a CloudWatch Events rule that triggers the Lambda function on a daily schedule, automating the backup process.

## Architecture Benefits

- **Disaster Recovery**: Cross-region snapshots ensure data availability during regional outages
- **Automation**: Lambda function eliminates manual intervention
- **Cost Optimization**: Configurable retention policies manage storage costs
- **Reliability**: CloudWatch Events provide consistent scheduling
- **Monitoring**: Built-in AWS logging and monitoring capabilities

## Key Components

1. **Source RDS Instance**: Primary database in Ireland region
2. **Lambda Function**: Automates snapshot and copy operations
3. **CloudWatch Events**: Schedules daily backup execution
4. **IAM Roles**: Provides necessary permissions for automation
5. **Cross-Region Snapshots**: Ensures disaster recovery capability

This implementation provides a robust, automated solution for RDS database backup and disaster recovery across AWS regions.