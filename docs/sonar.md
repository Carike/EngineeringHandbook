# Sonar

## About

These are the products from SonarSource:

1. [SonarQube Server]() is the on-premises version (formerly SonarQube) - [docs](https://docs.sonarsource.com/sonarqube-server/latest)
1. [SonarQube Cloud]() is the cloud/SaaS version (formerly SonarCloud) - [docs](https://docs.sonarsource.com/sonarqube-cloud)
1. [SonarQube IDE]() is the plugin installed on various IDEs (formerly SonarLint) 
1. [SonarQube Community](https://www.sonarsource.com/open-source-editions/sonarqube-community-edition/) - [docs](https://docs.sonarsource.com/sonarqube-community-build/)

## SonarQube IDE

For documentation for the various IDE's visit:

- [IntelliJ](https://docs.sonarsource.com/sonarqube-for-ide/intellij/)
- [Visual Studio](https://docs.sonarsource.com/sonarqube-for-ide/visual-studio/)
- [VS Code](https://docs.sonarsource.com/sonarqube-for-ide/vs-code/)
- [Eclipse](https://docs.sonarsource.com/sonarqube-for-ide/eclipse/)

[Connected mode](https://docs.sonarsource.com/sonarqube-for-ide/vs-code/team-features/connected-mode/)


### Setup Sonar IDE

1. Install the relevant plugin for the IDE you use. For example I will use VS Code
1. Configure [Connected mode](https://docs.sonarsource.com/sonarqube-for-ide/vs-code/team-features/connected-mode/)
  1. Info then is: 
    1. SonarQube server: [Your URL], 
    1. Username/Token: [Generate [user token](https://docs.sonarqube.org/latest/user-guide/user-token/) and paste token value], 
    1. Password: [Leave blank]

For Visual Studio:
1. Within “Team Explorer“ click on SonarQube. 
1. Info on the popup is:
  1. SonarQube server: [Your URL],
  1. Username/Token: [Generate token and paste token value],
  1. Password: [Leave blank]


## Sonar

## URLs

- https://www.sonarsource.com/open-source-editions/

## Issues when used in Azure Pipelines


On PR with SonarQube policy starts "waiting"

Error in pipeline is due to no test being present that could be executed. Once a simple test was added pipeline ran successfully.

```
2025-02-03T08:14:15.2515200Z INFO: Sensor Generic Coverage Report
2025-02-03T08:14:15.2516442Z INFO: Parsing /agent/_work/_temp/SonarQube.xml
2025-02-03T08:14:15.2595609Z INFO: ------------------------------------------------------------------------
2025-02-03T08:14:15.2602368Z INFO: EXECUTION FAILURE
2025-02-03T08:14:15.2602776Z INFO: ------------------------------------------------------------------------
2025-02-03T08:14:15.2604120Z INFO: Total time: 8.377s
2025-02-03T08:14:15.3098717Z INFO: Final Memory: 26M/100M
2025-02-03T08:14:15.3099441Z INFO: ------------------------------------------------------------------------
2025-02-03T08:14:15.3109298Z ##[error]ERROR: Error during SonarScanner execution
ERROR: Error during parsing of the generic coverage report '/agent/_work/_temp/SonarQube.xml'. Look at SonarQube documentation to know the expected XML format.
ERROR: Caused by: /agent/_work/_temp/SonarQube.xml (No such file or directory)
ERROR:
2025-02-03T08:14:15.3141194Z ERROR: Error during SonarScanner execution
2025-02-03T08:14:15.3141858Z ERROR: Error during parsing of the generic coverage report '/agent/_work/_temp/SonarQube.xml'. Look at SonarQube documentation to know the expected XML format.
2025-02-03T08:14:15.3142506Z ERROR: Caused by: /agent/_work/_temp/SonarQube.xml (No such file or directory)
2025-02-03T08:14:15.3142925Z ERROR: 
2025-02-03T08:14:15.6485104Z ##[error]The SonarScanner did not complete successfully
2025-02-03T08:14:15.6486466Z The SonarScanner did not complete successfully
2025-02-03T08:14:15.6487348Z ##[error]08:14:15.648  Post-processing failed. Exit code: 1
2025-02-03T08:14:15.6488065Z 08:14:15.648  Post-processing failed. Exit code: 1
2025-02-03T08:14:15.6542192Z ##[error][ERROR] SonarQube Server: Error while executing task Analyze: The process '/usr/bin/dotnet' failed with exit code 1
2025-02-03T08:14:15.6543610Z ##[error]The process '/usr/bin/dotnet' failed with exit code 1
2025-02-03T08:14:15.6584103Z ##[section]Finishing: Run Code Analysis
```