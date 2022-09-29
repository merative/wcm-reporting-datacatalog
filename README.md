# Watson Care Manager Reporting Data Catalog

IBM Watson® Care Manager supports human-centered contact tracing through structured interviews and provides care teams a platform for supporting the holistic needs of individuals affected by COVID-19 and beyond. Bridge the gap between health and social needs, collaborate across departments and jurisdictions, and automate care management workflows to support ongoing care.

Watson Care Manager is a rapidly deployable, HIPAA-enabled, and cloud-based SaaS solution that connects stakeholders and supports coordination and delivery of services

Watson Care Manager Reporting is a solution allowing clients to view their WCM transactional data.  WCM Reporting now introduces a Bring-Your-Own-Tool (BYOT) approach allowing clients use their local Business Intelligence (BI) tooling.   

Main use cases for WCM Reporting BYOT are the creation of curated content typically in the form of Reports or Dashboards, or to support self-service reporting using your local business intelligence tooling or by copying data locally to report against.

The IBM Watson® Care Manager Reporting application is built on IBM® DB2® Warehouse. For more information on IBM Db2 Warehouse, see the IBM documentation.


The data catalog for WCM Reporting BYOT is available at this URL: [https://merative.github.io/wcm-reporting-datacatalog](https://merative.github.io/wcm-reporting-datacatalog)

The Git repository for the data catalog is located as at this URL: [https://github.com/merative/wcm-reporting-datacatalog](https://github.com/merative/wcm-reporting-datacatalog)

The WCM SaaS offering includes a Warehouse for BYOT workloads, a data refresh cycle runs every two hours copies data from the application to the warehouse. So that you are aware of when the last data refresh happened, a Data Refresh table is available. This table contains two data items, the Last Refresh Date which shows the last refresh date and time and the Last Refresh Status, for example, Complete or In Progress. Applicaion data that is recorded after the last refresh date is not available. Coordinated Universal Time (UTC) is the time standard used in all reports that display a time, including the last data refresh date and time.
