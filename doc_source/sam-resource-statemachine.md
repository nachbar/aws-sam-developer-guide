# AWS::Serverless::StateMachine<a name="sam-resource-statemachine"></a>

Creates an AWS Step Functions state machine, which enables you to orchestrate Lambda functions and other AWS resources to form complex and robust workflows\.

For more information about Step Functions see [AWS Step Functions Developer Guide](https://docs.aws.amazon.com/step-functions/latest/dg/welcome.html)\.

## Syntax<a name="sam-resource-statemachine-syntax"></a>

To declare this entity in your AWS SAM template, use the following syntax:

### YAML<a name="sam-resource-statemachine-syntax.yaml"></a>

```
Type: AWS::Serverless::StateMachine
Properties:
  [Definition](#sam-statemachine-definition): Map
  [DefinitionSubstitutions](#sam-statemachine-definitionsubstitutions): Map
  [DefinitionUri](#sam-statemachine-definitionuri): String | [S3Location](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-stepfunctions-statemachine.html#cfn-stepfunctions-statemachine-definitions3location)
  [Events](#sam-statemachine-events): [EventSource](sam-property-statemachine-statemachineeventsource.md)
  [Logging](#sam-statemachine-logging): [LoggingConfiguration](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-stepfunctions-statemachine.html#cfn-stepfunctions-statemachine-loggingconfiguration)
  [Name](#sam-statemachine-name): String
  [Policies](#sam-statemachine-policies): String | List | Map
  [Role](#sam-statemachine-role): String
  [Tags](#sam-statemachine-tags): Map
  [Type](#sam-statemachine-type): String
```

## Properties<a name="sam-resource-statemachine-properties"></a>

 `Definition`   <a name="sam-statemachine-definition"></a>
The state machine definition as an object, where the format of the object matches the format of your AWS SAM template file, for example JSON or YAML\. State machine definitions adhere to the [Amazon States Language](https://docs.aws.amazon.com/step-functions/latest/dg/concepts-amazon-states-language.html)\.  
For an example of an in\-line state machine definition, see [Examples](#sam-resource-statemachine--examples)\.  
One of `Definition` or `DefinitionUri` must be provided\.  
*Type*: Map  
*Required*: Conditional  
*AWS CloudFormation Compatibility*: This property is unique to AWS SAM and doesn't have an AWS CloudFormation equivalent\.

 `DefinitionSubstitutions`   <a name="sam-statemachine-definitionsubstitutions"></a>
A map \(string to string\) that specifies the mappings for placeholder variables in the state machine definition\. This enables the customer to inject values obtained at runtime, for example from intrinsic functions, in the state machine defintion\.  
*Type*: Map  
*Required*: No  
*AWS CloudFormation Compatibility*: This property is similar to the `[DefinitionSubstitutions](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-stepfunctions-statemachine.html#cfn-stepfunctions-statemachine-definitionsubstitutions)` property of an `AWS::StepFunctions::StateMachine`\. If any intrinsic functions are specified in an in\-line state machine definition, AWS SAM adds entries to this property in order to inject them in the state machine definition\.

 `DefinitionUri`   <a name="sam-statemachine-definitionuri"></a>
The Amazon S3 URI or local file path of the state machine definition written in [Amazon States Language](https://docs.aws.amazon.com/step-functions/latest/dg/concepts-amazon-states-language.html)\.  
If a local file path is provided, the template must go through the workflow that includes the `sam deploy` or `sam package` command, in order for the definition to be transformed properly\.  
One of `Definition` or `DefinitionUri` must be provided\.  
*Type*: String \| [S3Location](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-stepfunctions-statemachine.html#cfn-stepfunctions-statemachine-definitions3location)  
*Required*: Conditional  
*AWS CloudFormation Compatibility*: This property is passed directly to the `[DefinitionS3Location](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-stepfunctions-statemachine.html#cfn-stepfunctions-statemachine-definitions3location)` property of an `AWS::StepFunctions::StateMachine`\.

 `Events`   <a name="sam-statemachine-events"></a>
Specifies the events that trigger this state machine\. Events consist of a type and a set of properties that depend on the type\.  
*Type*: [EventSource](sam-property-statemachine-statemachineeventsource.md)  
*Required*: No  
*AWS CloudFormation Compatibility*: This property is unique to AWS SAM and doesn't have an AWS CloudFormation equivalent\.

 `Logging`   <a name="sam-statemachine-logging"></a>
Defines which execution history events are logged and where they are logged\.  
*Type*: [LoggingConfiguration](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-stepfunctions-statemachine.html#cfn-stepfunctions-statemachine-loggingconfiguration)  
*Required*: No  
*AWS CloudFormation Compatibility*: This property is passed directly to the `[LoggingConfiguration](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-stepfunctions-statemachine.html#cfn-stepfunctions-statemachine-loggingconfiguration)` property of an `AWS::StepFunctions::StateMachine`\.

 `Name`   <a name="sam-statemachine-name"></a>
The name of the state machine\.  
*Type*: String  
*Required*: No  
*AWS CloudFormation Compatibility*: This property is passed directly to the `[StateMachineName](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-stepfunctions-statemachine.html#cfn-stepfunctions-statemachine-statemachinename)` property of an `AWS::StepFunctions::StateMachine`\.

 `Policies`   <a name="sam-statemachine-policies"></a>
One or more policies that the execution role for this state machine needs\.  
This property accepts a single string or a list of strings, and can be the name of AWS managed IAM policies, AWS SAM policy templates, or inline IAM policy document\(s\) formatted as a Map\.  
One of `Role` or `Policies` must be provided\.  
If the `Role` property is set, this property is ignored\.  
*Type*: String \| List \| Map  
*Required*: Conditional  
*AWS CloudFormation Compatibility*: This property is unique to AWS SAM and doesn't have an AWS CloudFormation equivalent\.

 `Role`   <a name="sam-statemachine-role"></a>
The ARN of an IAM role to use as this state machine's execution role\.  
One of `Role` or `Policies` must be provided\.  
*Type*: String  
*Required*: Conditional  
*AWS CloudFormation Compatibility*: This property is passed directly to the `[RoleArn](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-stepfunctions-statemachine.html#cfn-stepfunctions-statemachine-rolearn)` property of an `AWS::StepFunctions::StateMachine`\.

 `Tags`   <a name="sam-statemachine-tags"></a>
A map \(string to string\) that specifies the tags added to the State Machine and the corresponding IAM execution role\.  
*Type*: Map  
*Required*: No  
*AWS CloudFormation Compatibility*: This property is passed directly to the `[Tags](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-stepfunctions-statemachine.html#cfn-stepfunctions-statemachine-tags)` property of an `AWS::StepFunctions::StateMachine`\.

 `Type`   <a name="sam-statemachine-type"></a>
The type of the state machine\.  
Valid values: STANDARD or EXPRESS  
*Type*: String  
*Required*: No  
*Default*: STANDARD  
*AWS CloudFormation Compatibility*: This property is passed directly to the `[StateMachineType](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-stepfunctions-statemachine.html#cfn-stepfunctions-statemachine-statemachinetype)` property of an `AWS::StepFunctions::StateMachine`\.

## Return Values<a name="sam-resource-statemachine-return-values"></a>

### Ref<a name="sam-resource-statemachine-return-values-ref"></a>

When you provide the logical ID of this resource to the Ref intrinsic function, Ref returns the ARN of the underlying `AWS::StepFunctions::StateMachine` resource\.

For more information about using the Ref function, see [Ref](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/intrinsic-function-reference-ref.html)\. 

### Fn::GetAtt<a name="sam-resource-statemachine-return-values-fn--getatt"></a>

Fn::GetAtt returns a value for a specified attribute of this type\. The following are the available attributes and sample return values\. 

For more information about using Fn::GetAtt, see [Fn::GetAtt](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/intrinsic-function-reference-getatt.html)\. 

`Name`  <a name="Name-fn::getatt"></a>
Returns the name of the state machine, such as `HelloWorld-StateMachine`\.

## Examples<a name="sam-resource-statemachine--examples"></a>

### State Machine Definition File<a name="sam-resource-statemachine--examples--state-machine-definition-file"></a>

Following is an example of a state machine defined with a definition file\. The `my_state_machine.asl.json` file must be written in [Amazon States Language](https://docs.aws.amazon.com/step-functions/latest/dg/concepts-amazon-states-language.html)\.

In this example, the `DefinitionSubstitution` entries are needed for the state machine to include resources declared in the SAM template file\.

#### YAML<a name="sam-resource-statemachine--examples--state-machine-definition-file--yaml"></a>

```
MySampleStateMachine:
  Type: AWS::Serverless::StateMachine
  Properties:
    DefinitionUri: statemachine/my_state_machine.asl.json
    Role: arn:aws:iam::123456123456:role/service-role/my-sample-role
    DefinitionSubstitutions:
      MyFunctionArn: !GetAtt MyFunction.Arn
      MyDDBTable: !Ref TransactionTable
```

### In\-line State Machine Definition<a name="sam-resource-statemachine--examples--in-line-state-machine-definition"></a>

Following is an example of an in\-line state machine definition\.

In this example, the AWS SAM template file is written in YAML, so the state machine definition is also in YAML\. In order to declare an in\-line state machine definition in JSON, you can write your AWS SAM template file in JSON\.

#### YAML<a name="sam-resource-statemachine--examples--in-line-state-machine-definition--yaml"></a>

```
MySampleStateMachine:
  Type: AWS::Serverless::StateMachine
  Properties:
    Definition:
      StartAt: MyLambdaState
      States:
        MyLambdaState:
          Type: Task
          Resource: arn:aws:lambda:us-east-1:123456123456:function:my-sample-lambda-app
          End: true
    Role: arn:aws:iam::123456123456:role/service-role/my-sample-role
```