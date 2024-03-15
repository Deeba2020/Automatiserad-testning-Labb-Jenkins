Automatiserad testning – Labb Jenkins 
Syfte
Studenten ska efter slutförd kurs kunna designa tester för att testa en produkt på olika nivåer samt 
lösa sammansatta problem inom automatiserad testning genom att använda olika testverktyg och 
ramverk. I Labb Jenkins skapar vi en regressionstestsvit med hjälp av våra redan utvecklade enhets 
och systemtester och automatiserar körningen av dem med hjälp av en Pipeline i Jenkins som triggas 
av att nya commits pushas. 
Mål 
Målet med övningen är att pusha redan existerande tester samt ett Pipeline-skript till ett repo på 
Github för att sedan köra testerna via Jenkins. Därefter inspektera resultaten från testerna i Jenkins. 

inorder for the selenium to be visible in Jenkins follwing steps needs to be done:
1. go to this website https://wiki.jenkins.io/JENKINS/Configuring-Content-Security-Policy.html
2. copy System.setProperty("hudson.model.DirectoryBrowserSupport.CSP", "")
3. on Jenkins click on Manage Jenkins->Script Console -> paste this System.setProperty("hudson.model.DirectoryBrowserSupport.CSP", "") and click on Run -> Result should appear if run is successful

above steps will fix below issue

The default rule set results in the following: https://www.jenkins.io/doc/book/security/configuring-content-security-policy/
No JavaScript allowed at all
No plugins (object/embed) allowed
No inline CSS, or CSS from other sites allowed
No images from other sites allowed
No frames allowed
No web fonts allowed
No XHR/AJAX allowed
etc.



