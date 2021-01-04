# ServiceNow-ShippingRequest
A custom shipping request form and workflow that allows users to place a shipping request and leverages ServiceNow's robust tracking tables to log the entire process.

## Technologies Used
- ServiceNow Platform
- ServiceNow Service Catalog
- ServiceNow Workflow Editor

## Features
- Custom Form with auto-population scripts and controlled UI
- Entire request process powered by a workflow with approvals and task checking

## Getting Started
Import the XML file that contains the update set for the form and workflow. Some of the form variables have reference qualifiers that the company must not be empty so it will not display options that are in the global domain. This update set was created in Paris version, build tag: glide-paris-06-24-2020__patch1-hotfix3-09-23-2020.

## Usage
Once your instance has successfully committed the update, access the service catalog through the service portal and select Facilities. Then select the Shipping Request item which will take you to the form. Once the form is submitted it will create a record in the Requests table as well as one in the Requested Items table. This will start the workflow called SC Shipping Request. The workflow will proceed and require one or two approvals depending on the option selected for shipping type. Then it will create catalog tasks and a dynamic number of events based on the value given in the number of envelopes question in the form. Once all the tasks are closed the record in the Requested Items table will also close, either closed complete or closed incomplete, depending on if the tasks were closed complete or closed incomplete.

## License
This project uses the standard MIT License
