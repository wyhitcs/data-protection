# Reduction of access control decisions

# Reduction of access control decisions

## Outline

Access Decision Sets

Decision Reduction

Safe Reduction

Conclusion

## Access Decision Sets

###Access Control
![AccessControl](image/AccessControl.png)

## Decision Sets

 ![DecisionSets](image/DecisionSets.png)

## Combining Operators

 ![CombiningOperators](image/CombiningOperators.png)

 ![CombiningOperators2](image/CombiningOperators2.png)

#### Exercise

 ![exercisestrongdisjunctions](image/exercisestrongdisjunctions.png)

## Decision Reduction

### Reducing decision sets

Deal with non-conclusive decisions 

Ensure compatibility of operators when language evolves over time 

* e.g. from XACML v2 to XACML v3 

Reuse operators over smaller decision sets 

Enable interoperability between systems

###Decision Reduction

A **decision reduction** maps a decision set into a smaller decision set by mapping all decisions of a set to decisions of a subset, while leaving the decisions in the subset unchanged

 ![DecisionReduction](image/DecisionReduction.png)

###Sample Reduction

 ![SampleReduction](image/SampleReduction.png)

#### Example

 ![ReductionExample](image/ReductionExample.png)

Example 1: XACML v3

 ![1ReductionXAMCL](image/1ReductionXAMCL.png)

 ![2ReductionXAMCL](image/2ReductionXAMCL.png)

 ![3ReductionXAMCL](image/3ReductionXAMCL.png)

 ![4ReductionXAMCL](image/4ReductionXAMCL.png)

 ![5ReductionXAMCL](image/5ReductionXAMCL.png)

 ![6ReductionXAMCL](image/6ReductionXAMCL.png)

 ![7ReductionXAMCL](image/7ReductionXAMCL.png)

 ![8ReductionXAMCL](image/8ReductionXAMCL.png)

 ![9ReductionXAMCL](image/9ReductionXAMCL.png)

 ![10ReductionXAMCL](image/10ReductionXAMCL.png)

Example 2: From XACML v3 to XACML v2

 ![ReductionXAMCLv3tov2](image/ReductionXAMCLv3tov2.png)

 ![2ReductionXAMCLv3tov2](image/2ReductionXAMCLv3tov2.png)

Example 3: From PTaCL to XACML v3

 ![PTaCL](image/PTaCL.png)

## Safe Reduction

How to ensure that a reduction can be performed at any level of policy composition without changing the final decision?

 ![SafeReduction](image/SafeReduction.png)

### Safety of Operator Composition

 ![SafetyofOperatorComposition](image/SafetyofOperatorComposition.png)

 ![SafetyofOperatorComposition2](image/SafetyofOperatorComposition2.png)

### Safety Analysis of XACML v3

 ![SafetyAnalysisofXACMLv3](image/SafetyAnalysisofXACMLv3.png)

 ![2SafetyAnalysisofXACMLv3](image/2SafetyAnalysisofXACMLv3.png)

 ![3SafetyAnalysisofXACMLv3](image/3SafetyAnalysisofXACMLv3.png)

### Redefine operators

 ![Redefineoperator](image/Redefineoperator.png)

Example: First applicable

 ![ExampleFirstapplicable](image/ExampleFirstapplicable.png)

Example: Only one applicable

 ![ExampleOnlyoneapplicable](image/ExampleOnlyoneapplicable.png)

Safety Analysis of XACML v3 (2,3) ![SafetyAnalysisofXACMLv3(2,3)](image/SafetyAnalysisofXACMLv32,3.png)

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