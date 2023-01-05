# Shared solution project analysis

## Challenge
The `SharedSolution` contains projects such as `Contoso.Common` that are used in other solutions like `BackendSolution` and `TestingSolution`.

The `SharedSolution` projects are linked in the consumer solutions like `BackendSolution` and `TestingSolution`.

When we open a shared project like `Contoso.Common` from a consumer solution like `BackendSolution` we want to see the usage for each method in the `Contoso.Common` project. This information can be used to determine if a method can safely be deleted or changes.

## Problem Origin
Changes made to a common project often impacted others solution. Some of these solution where not opened often and had broken code because of a change in the common library. The broken code was 

## Solutions
### Phase 1
1. A command line tool can be ran to determine how many usages a specific method of a project has. This count should include usages from other solutions in the same repository.

### Phase 2
1. A Visual Studio should be created that shows the usages of a specific methode above the method signature.

### Phase 3
1. When a user changes a method in a shared project it should show which projects are no longer compatible with the new method signature.


## Example setup
This repository contains a sample setup. The expected analysis result for this repository should be:

### Contoso.Common project
- `ILoggingService.LogInformation` 1 usage
- `DateFormatter.GetShortDateString` 2 usages
