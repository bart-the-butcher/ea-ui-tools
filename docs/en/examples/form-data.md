# Example of a Data Editing Form

## Introduction

This article discusses an example model of a simple form used for data editing.

## Model

![Modify form](../../img/modify-form-model.png)

The above diagram shows the user interface model of a simple data modification form.

The form is launched with attribute settings described in the `Component attributes processing rules` requirement. For an editing form, the most common input data is the identifier of the record to be modified.

The form data is managed according to the rules described in `UI data processing rules`. This requirement describes the rules for executing the `getSomething` operation, which reads the editable data and saves it in the component’s state.

The form consists of the following elements:

* data editing panel
* operations panel

Both have details linked by the `UI Details` relationship.

The editing panel defines the form that will be visible to the user and will serve as a tool for modifying data. The panel displays the data read from the component’s state and allows for its modification.

The operations panel displays two buttons:

* `Modify`
* `Cancel`

Pressing the `Modify` button triggers the `putSomething` operation, which is connected to it by the `UI Call` relationship and saves the form’s state. In ambiguous situations, an `element rule` can be used to describe operation call details.
