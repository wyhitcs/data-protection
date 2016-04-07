# Reduction of access control decisions

# Reduction of access control decisions

## Outline

Access Decision Sets

Decision Reduction

Safe Reduction

Conclusion

## Access Decision Sets

###Access Control
![AccessControl](AccessControl.png)

## Decision Sets

 ![DecisionSets](DecisionSets.png)

## Combining Operators

 ![CombiningOperators](CombiningOperators.png)

 ![CombiningOperators2](CombiningOperators2.png)

#### Exercise

 ![exercisestrongdisjunctions](exercisestrongdisjunctions.png)

## Decision Reduction

### Reducing decision sets

Deal with non-conclusive decisions 

Ensure compatibility of operators when language evolves over time 

* e.g. from XACML v2 to XACML v3 

Reuse operators over smaller decision sets 

Enable interoperability between systems

###Decision Reduction

A **decision reduction** maps a decision set into a smaller decision set by mapping all decisions of a set to decisions of a subset, while leaving the decisions in the subset unchanged

 ![DecisionReduction](DecisionReduction.png)

###Sample Reduction

 ![SampleReduction](SampleReduction.png)

#### Example

 ![ReductionExample](ReductionExample.png)

Example 1: XACML v3

 ![1ReductionXAMCL](1ReductionXAMCL.png)

 ![2ReductionXAMCL](2ReductionXAMCL.png)

 ![3ReductionXAMCL](3ReductionXAMCL.png)

 ![4ReductionXAMCL](4ReductionXAMCL.png)

 ![5ReductionXAMCL](5ReductionXAMCL.png)

 ![6ReductionXAMCL](6ReductionXAMCL.png)

 ![7ReductionXAMCL](7ReductionXAMCL.png)

 ![8ReductionXAMCL](8ReductionXAMCL.png)

 ![9ReductionXAMCL](9ReductionXAMCL.png)

 ![10ReductionXAMCL](10ReductionXAMCL.png)

Example 2: From XACML v3 to XACML v2

 ![ReductionXAMCLv3tov2](ReductionXAMCLv3tov2.png)

 ![2ReductionXAMCLv3tov2](2ReductionXAMCLv3tov2.png)

Example 3: From PTaCL to XACML v3

 ![PTaCL](PTaCL.png)

## Safe Reduction

How to ensure that a reduction can be performed at any level of policy composition without changing the final decision?

 ![SafeReduction](SafeReduction.png)

### Safety of Operator Composition

 ![SafetyofOperatorComposition](SafetyofOperatorComposition.png)

 ![SafetyofOperatorComposition2](SafetyofOperatorComposition2.png)

### Safety Analysis of XACML v3

 ![SafetyAnalysisofXACMLv3](SafetyAnalysisofXACMLv3.png)

 ![2SafetyAnalysisofXACMLv3](2SafetyAnalysisofXACMLv3.png)

 ![3SafetyAnalysisofXACMLv3](3SafetyAnalysisofXACMLv3.png)

### Redefine operators

 ![Redefineoperator](Redefineoperator.png)

Example: First applicable

 ![ExampleFirstapplicable](ExampleFirstapplicable.png)

Example: Only one applicable

 ![ExampleOnlyoneapplicable](ExampleOnlyoneapplicable.png)

Safety Analysis of XACML v3 (2,3) ![SafetyAnalysisofXACMLv3(2,3)](SafetyAnalysisofXACMLv3(2,3).png)

## Conclusion

Decision Reduction

* Deal with non-conclusive decisions
* Reuse combining algorithms
* Enable Interoperability

Safe Decision Reduction

* Ensure that a reduction can be performed at any level of policy composition without changing the final decision

Safety Analysis of XACML v3

* XACML v3 is NOT safe!!
* Decision set depends on combining operators