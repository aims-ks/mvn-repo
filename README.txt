How to deploy jar to the mvn-repo.

1. Compile the jar
	mvn clean + mvn package

2. Deploy in this project
	mvn deploy:deploy-file -Durl=file:///path/to/mvn-repo/ -Dfile=sld-0.1.jar -DgroupId=au.gov.aims -DartifactId=sld -Dpackaging=jar -Dversion=0.1

	Example:
		/bin/bash /home/glafond/Desktop/projects/Intellij/idea-IU-143.1821.5/plugins/maven/lib/maven2/bin/mvn deploy:deploy-file -Durl=file:///home/glafond/Desktop/projects/Intellij/projects/mvn-repo/ -Dfile=/home/glafond/Desktop/projects/Intellij/projects/sld/target/sld-0.1.jar -DgroupId=au.gov.aims -DartifactId=sld -Dpackaging=jar -Dversion=0.1

3. Push to GitHub

4. Change the version number in the pom of your project to use the latest version.

