---
title: Test Execution
deprecated: false
hidden: false
metadata:
  robots: index
---
![](https://files.readme.io/d85b6cfdb7b782a352a58012a19c8762645ad5ae10af44c6df3a20bf945fd351-test-execution.png)

<br />

## Overview

Test Execution is the process of running your Test Suites against your Voiceflow applications to validate functionality, responses, and user experience flows.

## How Test Execution Works

### Manual Execution

You can run tests immediately in several ways:

* **From Test Suites Page**: Click the "Run Test" button on any test suite card
* **From Test Suite Editor**: Use the "Execute Test" button when viewing/editing a suite

### Status Indicators

* **Pending** ⏳: Test has been submitted and is waiting to start
* **Running** 🔄: Test is currently executing
* **Completed** ✅: Test finished successfully with all validations
* **Failed** ❌: Test failed due to validation errors or system issues
* **Scheduled** 📅: Test is queued for future execution

## Test Execution History

### Viewing Executions

Navigate to **Test Executions** to see:

* **Complete History**: All your past test executions
* **Execution Details**: Date, time, duration, and status for each run
* **Suite Information**: Which test suite was executed
* **Trigger Type**: Whether the test was run manually or scheduled

### Execution Details

![](https://files.readme.io/851bdd066c3939cda2661e15a804629e0878ba035492c0b93264046c5481c0ef-test-execution-detail.png)

<br />

Click on any execution to view:

* **Test Logs**: Detailed step-by-step execution logs
* **Results**: Pass/fail status for each test case
* **Timing Information**: How long each test case took
* **Error Details**: Specific failure reasons and debugging information

## Execution Types

* Manual Executions: Triggered by user action
* Scheduled Executions: Automated runs at specified times

## Understanding Test Results

### Success Criteria

A test execution is considered successful when:

* All test cases pass their validation criteria
* No system errors occur during execution
* All API calls complete successfully

### Failure Analysis

When tests fail, review:

* **Validation Errors**: Which specific validations failed
* **Response Differences**: How actual responses differed from expected
* **System Issues**: API connectivity or timeout problems
* **Configuration Errors**: Incorrect test setup or parameters

### Logs and Debugging

Execution logs provide detailed information for debugging tests.

## Execution Limits and Considerations

### API Limitations

* Respect Voiceflow API rate limits
* Monitor Voiceflow token usage to avoid quota exhaustion
* Plan execution timing to optimize resources

### Performance Factors

* Test complexity affects execution time
* Network latency impacts overall duration
* API response times vary based on bot complexity

### Data Retention

* Execution history is retained for your account
* Logs and results are available for analysis
* Export capabilities for external reporting