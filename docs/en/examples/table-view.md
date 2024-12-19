# Example of a Tabular Data List User Interface with a Filter Panel

## Introduction

This article discusses an example of modeling a user interface for a typical data list. This list consists of a filter panel and a tabular data list.

## Model

![Table component view](../../img/data-table-view-model.png)

The above diagram shows the model of the user interface component that handles displaying data in a tabular list format.

The rules for storing and managing data within the component are described in the `UI data processing rules` requirement.

The component consists of two elements:

* a set of fields that allow for entering search criteria,
* a table that displays the searched data.

The two elements listed above have details shown as panels connected by the `UI Details` relationship.

Search criteria data is a simple form including:

* a field for entering text data,
* a button that supports reading and refreshing the tabular summary of the data.

Pressing the `Search` button results in calling the `getSomething` operation, which reads the data. After reading, the tabular list is refreshed. The rules for handling the operation call are described in `Search rules`. The `getSomething` operation is associated to the button by the `UI Call` relationship.

In the diagram, the tabular list is presented as two rows (panels were used for this). The first row is the header. The next row represents the data shown in the table. The header shows the labels of the data fields displayed in the data rows. The data line shows the field names of the list items returned by the `getSomething` operation. A detailed description of the data mapping rules is included in the, associated with the panel, requirement `Table display rules`.

Each row in the first column of the list item displays a context menu. In the diagram, this element is detailed in the form of a panel containing a menu navigation list item. The user sees the `View` option by default. When the user clicks on the expand button, a list of available options is displayed. The panel is positioned underneath the menu (in the diagram this is represented as a `UI Show` relationship with a `Position` attribute equal to `Below`). The rules for displaying and handling menu options are contained in the `Options display rules` requirement.

Selecting the `Modify` option launches the `modify-form` component. The modification component has its design in the diagram `UI Design: Modify-form`.
