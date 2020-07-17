DEPRECATED
----------

This project is now **DEPRECATED**.

Please, use the maven repositories provided by
[GitHub Packages](https://github.com/orgs/aims-ks/packages) or the
[mvn-mirror-repo](https://github.com/aims-ks/mvn-mirror-repo)
for the mirrored libraries such as the edal libraries.

How to add this repo to your project
------------------------------------

Add this to your project .pom file:

```
    <repositories>
        <!-- AIMS ks maven repository on GitHub -->
        <repository>
            <id>aims-ks.mvn-repo</id>
            <name>AIMS Knowledge System MVN Repo</name>
            <url>https://raw.githubusercontent.com/aims-ks/mvn-repo/master/</url>
        </repository>
    </repositories>
```


How to deploy jar to the mvn-repo
---------------------------------

1. Update the mvn-repo project
	```
	cd /path/to/mvn-repo/
	git pull
	```

2. Compile the jar

	```
	mvn clean
	mvn package
	```

3. Deploy in this project

	Replace "/path/to" with the path to the "mvn-repo" folder on your local computer.

	Replace "[LIBRARY]" and "[VERSION]" with the name and version of the library you want to add to the repository.

	```
	mvn deploy:deploy-file -Durl=file:///path/to/mvn-repo/ -DpomFile=pom.xml -Dfile=[LIBRARY]-[VERSION].jar -DgroupId=au.gov.aims -DartifactId=[LIBRARY] -Dpackaging=jar -Dversion=[VERSION]
	```

	Examples (using the "mvn" command bundled in IntelliJ):
	```
	mvn deploy:deploy-file -Durl=file:///home/glafond/Desktop/projects/Intellij/projects/mvn-repo/ -DpomFile=/home/glafond/Desktop/projects/Intellij/projects/sld/pom.xml -Dfile=/home/glafond/Desktop/projects/Intellij/projects/sld/target/sld-0.1.6.jar -DgroupId=au.gov.aims -DartifactId=sld -Dpackaging=jar -Dversion=0.1.6
	mvn deploy:deploy-file -Durl=file:///home/glafond/Desktop/projects/Intellij/projects/mvn-repo/ -DpomFile=/home/glafond/Desktop/projects/Intellij/projects/layers2svg/pom.xml -Dfile=/home/glafond/Desktop/projects/Intellij/projects/layers2svg/target/layers2svg-0.1.11.jar -DgroupId=au.gov.aims -DartifactId=layers2svg -Dpackaging=jar -Dversion=0.1.11
	mvn deploy:deploy-file -Durl=file:///home/glafond/Desktop/projects/Intellij/projects/mvn-repo/ -DpomFile=/home/glafond/Desktop/projects/Intellij/projects/edal-common_fix-mem-leak/pom.xml -Dfile=/home/glafond/Desktop/projects/Intellij/projects/edal-common_fix-mem-leak/target/edal-common_fix-mem-leak-1.2.4.jar -DgroupId=uk.ac.rdg.resc -DartifactId=edal-common_fix-mem-leak -Dpackaging=jar -Dversion=1.2.4
	mvn deploy:deploy-file -Durl=file:///home/glafond/Desktop/projects/Intellij/projects/mvn-repo/ -DpomFile=/home/glafond/Desktop/projects/Intellij/projects/json/pom.xml -Dfile=/home/glafond/Desktop/projects/Intellij/projects/json/target/json-1.0.3.jar -DgroupId=au.gov.aims -DartifactId=json -Dpackaging=jar -Dversion=1.0.3
	```

4. Push to GitHub
	```
	cd /path/to/mvn-repo/
	git add -A
	git status
	git commit -m "Commit message"
	git push -u origin master
	```

5. Change the version number in the pom of your project to use the latest version.

