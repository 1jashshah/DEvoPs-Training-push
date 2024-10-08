The goal of this capstone project is to combine shell scripting with
system monitoring and log management practices. You will create a set of
automated tools using shell scripts to manage logs, monitor system
performance using Prometheus and Node Exporter, and generate insights
using PromQL queries. The project will require a systematic approach,
covering scripting fundamentals, log management, and monitoring setup.

### **Project Deliverables:**

1.  **Shell Scripts for Basic Operations:**

    -   **Task:** Write shell scripts to perform basic system
        > operations, such as checking disk usage, memory usage, and CPU
        > load.

    -   **Deliverable:**

        -   A collection of scripts that output system performance
            > metrics.

        -   Scripts should include error handling and logging.

#!/bin/bash

while :

do

echo \"\"

echo \" 1. Show Disk Usage\"

echo \" 2. Show CPU USage\"

echo \" 3. Show Memory Usage\"

read -p \"ENter the right Number :\" choice

case \$choice in

1\) du ;;

2\) top ;;

3\) free -h ;;

\*) echo \"Invalid Number\" ;;

esac

done

![](vertopal_9bbf47cb8edd4a51a61a8a2e3722c214/media/image6.png){width="6.5in"
height="2.1944444444444446in"}

> ![](vertopal_9bbf47cb8edd4a51a61a8a2e3722c214/media/image13.png){width="6.5in"
> height="4.138888888888889in"}

2.  **Log Management Script:**

    -   **Task:** Develop a script to automate log management tasks such
        > as log rotation and archiving. This script should include the
        > ability to compress old logs and delete logs older than a
        > specified number of days.

    -   **Deliverable:**

        -   A shell script that performs log rotation based on
            > predefined conditions (e.g., log size, log age).

        -   A report generated by the script detailing which logs were
            > rotated, compressed, or deleted.

#!/bin/bash

\# Define the output file

OUTPUT_FILE=\"log_report.txt\"

\# Functions Of disk_usage , Check Memory and check CPU load

check_log() {

echo \"logs are shown below :-\"

cat /var/log/syslog \| tail -n 4

echo

}

\# Write the results to the output file if specified

if \[ -n \"\$OUTPUT_FILE\" \]; then

{

check_log

} \> \"\$OUTPUT_FILE\"

echo \"Report saved to \$OUTPUT_FILE\"

fi

![](vertopal_9bbf47cb8edd4a51a61a8a2e3722c214/media/image11.png){width="6.5in"
height="2.5555555555555554in"}

3.  **Advanced Shell Scripting - Loops, Conditions, Functions, and Error
    > Handling:**

    -   **Task:** Refactor the previous scripts to include loops,
        > conditionals, and functions for modularity. Implement error
        > handling to manage potential issues during script execution.

    -   **Deliverable:**

        -   Modular shell scripts that use functions for repeatable
            > tasks.

        -   Error-handling mechanisms in place for scenarios like
            > missing files, insufficient permissions, etc.

        -   Logs that track script execution and any errors encountered.

#!/bin/bash

\# Define the output file

OUTPUT_FILE=\"log_report.txt\"

\# Functions Of disk_usage , Check Memory and check CPU load

check_log() {

echo \"logs are shown below :-\"

cat /var/log/syslog \| tail -n 4

echo

}

\# Write the results to the output file if specified

if \[ -n \"\$OUTPUT_FILE\" \]; then

{

check_log

} \> \"\$OUTPUT_FILE\"

echo \"Report saved to \$OUTPUT_FILE\"

fi

![](vertopal_9bbf47cb8edd4a51a61a8a2e3722c214/media/image3.png){width="6.5in"
height="0.3472222222222222in"}

![](vertopal_9bbf47cb8edd4a51a61a8a2e3722c214/media/image7.png){width="6.010416666666667in"
height="5.458333333333333in"}

4.  **Log Checking and Troubleshooting:**

    -   **Task:** Write a script that reads through system and
        > application logs, identifies common issues (e.g., out of
        > memory, failed service starts), and provides troubleshooting
        > steps based on log analysis.

    -   **Deliverable:**

        -   A script that parses logs for errors or warnings and outputs
            > possible root causes.

        -   Documentation on the types of logs checked and the issues
            > identified.

        -   A troubleshooting guide based on common errors found in the
            > logs.

![](vertopal_9bbf47cb8edd4a51a61a8a2e3722c214/media/image8.png){width="6.010416666666667in"
height="5.458333333333333in"}

![](vertopal_9bbf47cb8edd4a51a61a8a2e3722c214/media/image1.png){width="6.5in"
height="0.2638888888888889in"}

**Installation and Setup of Prometheus and Node Exporter:**

-   **Task:** Install and configure Prometheus and Node Exporter on the
    > system. Ensure that Node Exporter is properly configured to
    > collect system metrics.

-   **Deliverable:**

    -   A documented installation and configuration process for
        > Prometheus and Node Exporter.

    -   A running instance of Prometheus scraping metrics from Node
        > Exporter.

![](vertopal_9bbf47cb8edd4a51a61a8a2e3722c214/media/image5.png){width="6.5in"
height="1.5833333333333333in"}

![](vertopal_9bbf47cb8edd4a51a61a8a2e3722c214/media/image4.png){width="6.5in"
height="1.5833333333333333in"}

Run ./prometheus

![](vertopal_9bbf47cb8edd4a51a61a8a2e3722c214/media/image9.png){width="6.5in"
height="3.25in"}

![](vertopal_9bbf47cb8edd4a51a61a8a2e3722c214/media/image2.png){width="6.5in"
height="1.4583333333333333in"}

**Prometheus Query Language (PromQL) Basic Queries:**

-   **Task:** Create a series of PromQL queries to monitor system
    > performance, such as CPU usage, memory usage, and disk I/O.

-   **Deliverable:**

    -   A set of PromQL queries that can be used to monitor key system
        > metrics.

    -   A dashboard setup guide or configuration that visualizes these
        > metrics in Prometheus or Grafana.

![](vertopal_9bbf47cb8edd4a51a61a8a2e3722c214/media/image10.png){width="4.880208880139983in"
height="2.4618514873140858in"}

![](vertopal_9bbf47cb8edd4a51a61a8a2e3722c214/media/image12.png){width="4.755208880139983in"
height="2.399179790026247in"}

> **Final Report and Presentation:**

-   **Task:** Prepare a final report documenting all scripts, the
    > installation and configuration of monitoring tools, and the output
    > of your PromQL queries.

-   **Deliverable:**

    -   A comprehensive project report covering all steps, scripts, and
        > results.
