# PythonServiceCosting
This is a simple Python 3 script for consuming a list of Services, their types, their dependencies, and their costs and exporting an xlsx file that calculates total cost for each service plus the cost from predecessor services and to successor services.

## Requirements
This script requires the following modules:

* openpyxl
* networkx

It also requires that [Graphviz](http://www.graphviz.org/ "Graphviz") be installed locally and accessible via the user path.


## Inputs

This script expects a `services.xlsx` file with the following columns:
* **Service** - the name of the service
* **Service Type** - Whether the service is 'Business Facing' or 'IT Supporting'
* **Service Dependencies** - a semicolon separate list of services that this service depends on
* **Cost** - A number representing the cost of the service

## Outputs

This script will output two files

`graphviz.txt`

This is a text file that contains Dot language for drawing a digraph of the services.

`service_costs.xlsx`

This xlsx files contains a tab for all services that displays their base costs, predecessor costs and successor costs.  Successor costs are calculated at a flat percentage at first but can be tweaked after.

Due to the possiblity of circular relationships among the services, iterative formulas may need to be enabled.  To do this go to File -> Options -> Forumlas and check "Enable iterative formulas"
