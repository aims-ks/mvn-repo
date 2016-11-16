How to deploy jar to the mvn-repo.

1. Compile the jar
	mvn clean + mvn package

2. Deploy in this project
	Replace "/path/to" with the path to the "mvn-repo" folder on your local computer.
	Replace "<LIBRARY>" and "<VERSION>" with the name and version of the library you want to add to the repository.
		mvn deploy:deploy-file -Durl=file:///path/to/mvn-repo/ -Dfile=<LIBRARY>-<VERSION>.jar -DgroupId=au.gov.aims -DartifactId=<LIBRARY> -Dpackaging=jar -Dversion=<VERSION>

	Examples (using the "mvn" command bundled in IntelliJ):
		/bin/bash /home/glafond/Desktop/projects/Intellij/idea-IU/plugins/maven/lib/maven2/bin/mvn deploy:deploy-file -Durl=file:///home/glafond/Desktop/projects/Intellij/projects/mvn-repo/ -Dfile=/home/glafond/Desktop/projects/Intellij/projects/sld/target/sld-0.1.jar -DgroupId=au.gov.aims -DartifactId=sld -Dpackaging=jar -Dversion=0.1
		/bin/bash /home/glafond/Desktop/projects/Intellij/idea-IU/plugins/maven/lib/maven2/bin/mvn deploy:deploy-file -Durl=file:///home/glafond/Desktop/projects/Intellij/projects/mvn-repo/ -Dfile=/home/glafond/Desktop/projects/Intellij/projects/layers2svg/target/layers2svg-0.1.jar -DgroupId=au.gov.aims -DartifactId=layers2svg -Dpackaging=jar -Dversion=0.1

3. Push to GitHub
	cd /path/to/mvn-repo/
	git add -A
	git push -u origin master

4. Change the version number in the pom of your project to use the latest version.
