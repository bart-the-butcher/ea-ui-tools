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

The search data is a simple form that includes:

* a field for entering text data,
* a button that refreshes the list data based on the entered search criteria.

Pressing the `Search` button triggers the `getSomething` operation, which reads the data and refreshes the list. The handling rules for this operation are described in `Search principles`.

The `getSomething` operation is linked to the button by the `UI Call` relationship.

The data list is presented in two rows. The first row defines the header visible to the user, listing the names of the displayed data. The second row provides information for implementers, showing the data from the retrieved list to be displayed to the user. Execution details are included in the requirement `Table display rules` associated with the panel.

In the first column of the list, a context menu is displayed. This element has a detail showing that handling it should be done as an element containing one active option, `View`, and the ability for the user to expand other options by pressing a button. The expanded view is displayed as a panel containing buttons arranged vertically. Display and handling rules are included in the requirement `Options display rules`.

Selecting the `Modify` option launches the `modify-form` component. The modification component has its design in the diagram `UI Design: Modify-form`.
