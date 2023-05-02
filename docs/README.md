# Merative Integrated Care Reporting

Merative Integrated Care is a rapidly deployable, HIPAA-enabled, and cloud-based SaaS solution that connects stakeholders and supports coordination and delivery of services

Merative Integrated Care Reporting is a solution allowing clients to view their transactional data.  Merative Integrated Care Reporting now introduces a Bring-Your-Own-Tool (BYOT) approach allowing clients use their local Business Intelligence (BI) tooling.   

Main use cases for Merative Integrated Care Reporting BYOT are the creation of curated content typically in the form of Reports or Dashboards, or to support self-service reporting using your local business intelligence tooling or by copying data locally to report against.

**Technical**

The Merative Integrated Care Reporting application is built on IBM® DB2® Warehouse. For more information on IBM Db2 Warehouse, see the IBM documentation.

The data catalog for Merative Integrated Care Reporting BYOT is available at this URL: https://merative.github.io/wcm-reporting-datacatalog

The Git repository for the data catalog is located at this URL: https://github.com/merative/wcm-reporting-datacatalog

The Merative Integrated Care SaaS offering includes a warehouse for BYOT workloads. A data refresh cycle, that runs every two hours, copies data from the application to the warehouse. So that you are aware of when the last data refresh happened, a Data Refresh table is available. This table contains two data items, the Last Refresh Date which shows the last refresh date and time and the Last Refresh Status, for example, Complete or In Progress. Application data that is recorded after the last refresh date is not available. Coordinated Universal Time (UTC) is the time standard used in all reports that display a time, including the last data refresh date and time.


© Merative US L.P. 2016, 2023. 
Merative is a trademark of Merative US L.P. in the United States and other countries.
