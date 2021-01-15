## DevOpsProject ##

# Add tmp/set.xml to VM #

$ vim /tmp/set.xml
	$ i
	<settings>
		<servers>
			<server>
				<id>myMavenRepo.read</id>
				<username>myMavenRepo</username>
				<password>DevOpsJEE404</password>
			</server>
			<server>
				<id>myMavenRepo.write</id>
				<username>myMavenRepo</username>
				<password>DevOpsJEE404</password>
			</server>
		</servers>
	</settings>
	$ :wq
$ cd /tmp
$ chmod 777 set.xml

# Configuration de Jenkins #

Configuration globale des outils
	Configuration Maven
		Fournisseur de réglages par défaut
			=> Réglages Maven par défaut
		Fournisseur de réglages globaux par défaut 
			=> Réglages Globaux Maven sur le système de fichiers
			File path 
				=> /tmp/set.xml

	Maven
		Nom => 3_5_0
		Install from Apache
			=> version 3.5.0

Plugins
	Install
		- Pipeline Maven Integration Plugin

# Pipeline Configuration #

Definition
	=> Pipeline script from SCM
	SCM	=> Git
		Repository URL
		=> https://github.com/NicolasGuillaumeSoulie/DevOpsProject/
		Branches to build 
		=> /main
		Script Path
		=> JenkinsFile


