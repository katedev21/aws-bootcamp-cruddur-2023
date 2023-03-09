# Week 2 — Distributed Tracing


## Required Homework

### Video Review
* Watched [FREE AWS Cloud Project Bootcamp - Update 2023-02-23 Video](https://youtu.be/gQxzMvk6BzM).
* Watched [Week 2 - Live Streamed Video – Honeycomb.io Setup](https://www.youtube.com/live/2GD9xCzRId4?feature=share).
* Watched [Week 2 - Instrument X-Ray Video](https://youtu.be/n2DTsuBrD_A).
* Watched [Week 2 – X-Ray Subsegments Solved Video](https://youtu.be/4SGTW0Db5y0)
* Watched [Week 2 - CloudWatch Logs Video](https://youtu.be/ipdFizZjOF4).
* Watched [Week 2 - Rollbar Video](https://youtu.be/xMBDAb5SEU4).
* Watched [Week 2 – Github Codespaces Crash Course Video](https://youtu.be/L9KKBXgKopA).

### Actions

#### Honeycomb

* Completed all steps during the livestream to set up Honeycomb distributed tracing.
* Confirmed trace data is showing up in Web UI

![image](https://user-images.githubusercontent.com/96145786/224062718-6be01c33-5142-4b15-b948-73cc7c8db9dc.png)

#### AWS X-Ray

* Completed all steps to implement AWS X-Ray tracing
* Note:  The X-Ray Trace Groups are under **X-Ray > New Console > CloudWatch > Settings > Traces > View Settings > Groups**.
* [Github - AWS X-Ray SDK Python](https://github.com/aws/aws-xray-sdk-python)
* Able to get X-Ray Traces showing up in **CloudWatch > X-Ray Traces > Traces**


#### AWS CloudWatch

* Completed all the steps to implement CloudWatch logs.
* Used [Watchtower](https://pypi.org/project/watchtower/) as a log handler for AWS CloudWatch.
* Used [Logging](https://docs.python.org/3/library/logging.html) to manage generating the logs.
* Left all logging for CloudWatch and X-Ray enabled in code as I'm not concerned about a slight amount of spend from log generation, if there is any.
* Confirmed log streams are able to be displayed in CloudWatch


#### Rollbar

* [Rollbar Docs](https://docs.rollbar.com/docs/flask) for Flask do say we need to install blinker.
* [Rollbar Docs](https://docs.rollbar.com/docs/python) for Python.
* Was able to get the test "Hello World" warnings to show up in Rollbar UI


## Spending Considerations
* Watched [Week 2 - Spend Considerations Video](https://www.youtube.com/watch?v=2W3KeqCjtDY).
* Completed Spend Quiz.

## Security Considerations
* Watched [Week 2 - Security Considerations Video](https://youtu.be/bOf4ITxAcXc).
* Completed Security Quiz.




## Publications

* [AWS Cloud Project Bootcamp – Week 2: Unofficial Homework Guide](https://www.linuxtek.ca/2023/02/26/aws-cloud-project-bootcamp-week-2-unofficial-homework-guide/)
