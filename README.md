# CloudFormation Template Repository

This repository contains a collection of AWS CloudFormation templates designed to be used as nested stacks for our organization's infrastructure deployment.

## Overview

These templates provide reusable components for building and managing our AWS resources. By using nested stacks, we can modularize our infrastructure and improve maintainability, reusability, and organization of our CloudFormation code.

## Usage

To use these templates as nested stacks:

1. Reference the desired template in your main stack using the `AWS::CloudFormation::Stack` resource type.
2. Provide the necessary parameters as defined in each template.
3. Use the outputs from nested stacks as needed in your main stack or other nested stacks.

### Example:

```yaml
Resources:
  VPCStack:
    Type: AWS::CloudFormation::Stack
    Properties:
      TemplateURL: https://s3.amazonaws.com/cfn-stack-template-storage/VPC/with-managed-nats.yaml
      Parameters:
        VPCName: project-name-vpc
```

## Best Practices

- Keep each template focused on a specific resource or group of related resources.
- Use parameters to make templates flexible and reusable.
- Leverage cross-stack references to share information between nested stacks.
- Include descriptions for each template, parameter, and output.
- Use consistent naming conventions across all templates.
