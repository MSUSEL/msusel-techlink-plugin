# msusel-techlink-plugin
SonarQube plugin containing all extensions and widgets relevant to TechLink

*CURRENTLY UNDER EARLY CONSTRUTION. Readme updates coming soon*

## Useful Terminal Commands
>>>>>>> d964c7deec69bcdb9aa85d3163f86468638ea710
### Maven
- **Build and copy to plugins folder**
    1. `mvn clean package`
    2. `cp target/msusel-techlink-plugin-0.0.1.jar /Users/david/bin/sonarqube-5.6.7/extensions/plugins/`
    3. Restart server
- **Hot Deploy Plugin**
    1. Add the property `sonar.web.dev=true` to `conf/sonar.properties`
    2. Restart server
    3. Build and deploy with `mvn clean package org.codehaus.sonar:sonar-dev-maven-plugin::upload -DsonarHome=/Users/david/bin/sonarqube-5.6.7 -DsonarUrl=http://localhost:9000`
- **Hot Deploy Widget**
    1. Edit method `RubyRailsWidget#getTemplatePath()` in Widget.java class to return absolute path of erb file
        1. `return "/Users/david/LocalRepository/MSUSEL/msusel-techlink-plugin/src/main/resources/edu/montana/gsoc/msusel/sonar/techlink/tester_results.html.erb";`
    2. Package plugin to SonarQube plugins folder
    3. Restart server. Ruby changes on the fly will now display.

### SonarQube
- **Run SonarQube Scanner (not TFS plugin way)**
    1. Assuming a *sonar-project.properties* file exists in the root directory of the project
        - Run `sonar-scanner` from that directory
