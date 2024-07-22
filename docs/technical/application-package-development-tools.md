# Application Package Development Tools

## Introduction

The following tools have been implemented in the scope of the EOEPCA project to help packaging EO Applications and combining these Applications into Application Packages:

- The [**EO Application Packaging Assistant**](https://eoepca.readthedocs.io/projects/eo-app-packaging-assistant/en/latest/) is an online tool that allows building Docker images and generating [Command Line Tool](https://www.commonwl.org/v1.0/CommandLineTool.html) snippets formatted using the [Common Workflow Language](https://www.commonwl.org/) in an interactive manner. The output is generated according to the [OGC Best Practice for Earth Observation Application Package](https://docs.ogc.org/bp/20-089r1.html). The online [User Manual](https://eoepca.readthedocs.io/projects/eo-app-packaging-assistant/en/latest/user-manual/) details the tool user interface and its behaviour.

- The [**Application Package Editor**](https://eoepca.readthedocs.io/projects/eo-app-package-editor/en/latest/) is an online tool that provides users with an interactive editor for the Common Workflow Language used for realising Application Packages. The online [User Manual](https://eoepca.readthedocs.io/projects/eo-app-package-editor/en/latest/user-manual/) gives many insights about the tool user interface as well as guidelines on how to create your first Application Package.

The two tools may be used sequentially: the **EO Application Packaging Assistant** is used to package one or more applications and generate the corresponding `CommandLineTool` definitions. These definitions may be copied on the local system and then pasted in the **Application Package Editor** to integrate the applications as steps in an Application Package workflow.

## When to use the EO Application Packaging Assistant

EO data processing algorithms must be packaged in a certain manner and integrated in a workflow (possibly as only step) before they can be deployed and executed in an EOEPCA-compliant platform.

On one hand, the algorithm executable (scripts and/or pre-compiled binaries) and dependencies (libraries, configuration files and other static data files) must be packaged in a Docker image. This must contain all the files and libraries required to execute the algorithm.
On the other hand, the algorithm must be specified in a CWL object of type `CommandLineTool` (CLT). This object includes, among other information, an identifier, user friendly label and description, the list of input and output parameters with their type and default value, the reference to the Docker image containing the application, and the command and parameters to execute it on the given inputs.

The Assistant graphical interface facilitates the creation of these resources by integrating the following features:

- Ability to enter the information to be included in the CWL document (CLT snippet) in a structured manner.

- Ability to upload the algorithm files and selecting the dependencies.

- Ability to build the Docker image and perform a test-run (execution of the algorithm) using the default input values, if provided.

- Ability to push the resulting Docker image in a Docker repository (platform default or user-specified).

The Assistant generates the `CommandLineTool` snippet and allows saving it either on the server side (e.g. in the user workspace) or on the local system.

The `CommandLineTool` snippet may then be integrated in workflows using the Application Package Editor. To accomplish that, select the CLT text in the Assistant user interface and paste it in the Editor, as explained below.


## When to use the Application Package Editor

The Application Package Editor facilitates the creation of workflow definitions expressed using the CWL standard format. At the minimum, a CWL document must contain the definition of a workflow object (including its inputs, outputs, processing steps, and connections between the output and input parameters), and a series of `CommandLineTool` (CLT) objects that further describe each workflow step. Each CLT object contains the definition of an individual Application, as packaged using the EO Application Packaging Assistant introduced above.

The Editor integrates an [Application Package Validator](../application-package-validator/) library able to detect issues (errors, warnings and other notes) in AP CWL files.

The Editor's main features include:

- Ability to enter the AP main properties (incl. date, version, keywords, release notes, logo, authors and schemas) using an interactive form.

- Ability to define new CommandLineTool objects from scratch using a form or pasting CLT definitions (e.g. as copied in the EO Application Packaging Assistant interface). Pasted CLT definitions may be further edited using the same form.

- Ability to configure the workflow object properties (incl. identifier, label and description, inputs and ouputs lists), selecting CLT definitions as workflow steps, connecting inputs to compatible outputs, and specifying requirements.

- Ability to validate the resulting AP CWL document and inspect the detected issues in a report.

- Ability to store the AP CWL documents on the server side (e.g. in the user workspace) or on the local system.

Valid Application Packages may be deployed and executed using an EOEPCA ADES compatible service.
