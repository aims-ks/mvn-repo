How to add this repo to your project
------------------------------------

Add this to your project .pom file:
    <repositories>
        <!-- AIMS ks maven repository on GitHub -->
        <repository>
            <id>aims-ks.mvn-repo</id>
            <name>AIMS Knowledge System MVN Repo</name>
            <url>https://raw.githubusercontent.com/aims-ks/mvn-repo/master/</url>
        </repository>
    </repositories>


How to deploy jar to the mvn-repo
---------------------------------

1. Compile the jar
	mvn clean + mvn package

2. Deploy in this project
	Replace "/path/to" with the path to the "mvn-repo" folder on your local computer.
	Replace "<LIBRARY>" and "<VERSION>" with the name and version of the library you want to add to the repository.
		mvn deploy:deploy-file -Durl=file:///path/to/mvn-repo/ -DpomFile=pom.xml -Dfile=<LIBRARY>-<VERSION>.jar -DgroupId=au.gov.aims -DartifactId=<LIBRARY> -Dpackaging=jar -Dversion=<VERSION>

	Examples (using the "mvn" command bundled in IntelliJ):
		/bin/bash /home/glafond/Desktop/projects/Intellij/idea-IU/plugins/maven/lib/maven2/bin/mvn deploy:deploy-file -Durl=file:///home/glafond/Desktop/projects/Intellij/projects/mvn-repo/ -DpomFile=/home/glafond/Desktop/projects/Intellij/projects/sld/pom.xml -Dfile=/home/glafond/Desktop/projects/Intellij/projects/sld/target/sld-0.1.6.jar -DgroupId=au.gov.aims -DartifactId=sld -Dpackaging=jar -Dversion=0.1.6
		/bin/bash /home/glafond/Desktop/projects/Intellij/idea-IU/plugins/maven/lib/maven2/bin/mvn deploy:deploy-file -Durl=file:///home/glafond/Desktop/projects/Intellij/projects/mvn-repo/ -DpomFile=/home/glafond/Desktop/projects/Intellij/projects/layers2svg/pom.xml -Dfile=/home/glafond/Desktop/projects/Intellij/projects/layers2svg/target/layers2svg-0.1.10.jar -DgroupId=au.gov.aims -DartifactId=layers2svg -Dpackaging=jar -Dversion=0.1.10

		/bin/bash /home/glafond/Desktop/projects/Intellij/idea-IU/plugins/maven/lib/maven2/bin/mvn deploy:deploy-file -Durl=file:///home/glafond/Desktop/projects/Intellij/projects/mvn-repo/ -DpomFile=/home/glafond/Desktop/projects/Intellij/projects/edal-common_fix-mem-leak/pom.xml -Dfile=/home/glafond/Desktop/projects/Intellij/projects/edal-common_fix-mem-leak/target/edal-common_fix-mem-leak-1.2.4.jar -DgroupId=uk.ac.rdg.resc -DartifactId=edal-common_fix-mem-leak -Dpackaging=jar -Dversion=1.2.4

3. Push to GitHub
	cd /path/to/mvn-repo/
	git add -A
	git status
	git commit -m "Commit message"
	git push -u origin master

4. Change the version number in the pom of your project to use the latest version.
