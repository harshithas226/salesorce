# salesorce
Datatable using LWC
Introduction
Lightning web components (LWC) are custom HTML elements built using HTML , modern JavaScript and LWC uses core Web Components standards and provides only what’s necessary to perform well in browsers supported by Salesforce. Because it’s built on code that runs natively in browsers, Lightning Web Components is lightweight and delivers exceptional performance. Most of the code you write is standard JavaScript and HTML.

Datatable in LWC
OOB lighting-datatable component displays tabular data where each column can be displayed based on the data type. It has lot of great features inbuilt, but if we have data with more than 100 rows that needs to render on page, we should either Implement Pagination or Infinite scroll for better user experience.

In this article we will focus on creating generic data table component with key features like (Pagination, Row selection, Static Headers and Global Search ). Source code for this article is in lwcDatatable repo.

Create Generic Component
First we will create generic data table component and we call the Component as lwcDatatableUtility.

Create a lightning web components with Component Name as "lwcDatatableUtility".
Replace code in lwcDatatableUtility.js, lwcDatatableUtility.html, lwcDatatableUtility.css from lwcDatatableUtility.
Deploy the lwcDatatableUtility component to your Org.
Now we have generic Data table component ready to use and we can plug this to your own components.
Plug-In Generic Component(lwcDataTableUtility ) to your Component
To use generic lwcDataTableUtility component in your own component.

Declare below variables in lwcDatatableUtility.js which we will be using to send Data to lwcDatatableUtility to render Table
allRecords
columns
To Render Table we need to include lwcDatatableUtility in .html page as below.
You can reference updateMultipleCases component on how to use lwcDataTableUtility**.**

<c-lwc-datatable-utility records={allRecords} 
total-records={allRecords.length} 
columns = {columns}
key-field="Id"
show-search-box="true"            
max-row-selection={allRecords.length}
onpaginatorchange={handlePaginatorChange}
onsetselectedrecords={handleAllSelectedRows}>
</c-lwc-datatable-utility>
Data Table in LWC 
