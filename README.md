## DevOpsProject ##

# Configuration de Jenkins #

Plugins
	Install
		- Pipeline Maven Integration Plugin

Configuration globale des outils
	Configuration Maven
		Fournisseur de réglages par défaut
			=> Réglages Maven par défaut
		Fournisseur de réglages globaux par défaut 
			=> Réglages Globaux Maven sur le système de fichiers
			File path 
				=> /tmp/set.xml

	Maven
		Nom =>
		Install from Apache
			=> version 3.5.0


# Add tmp/set.xml to VM #

$ vim /tmp/set.xml
	$ i
	<settings>
		<servers>
			<server>
				<id>myMavenRepo.read</id>
				<username>myMavenRepo</username>
				<password>PASS</password>
			</server>
			<server>
				<id>myMavenRepo.write</id>
				<username>myMavenRepo</username>
				<password>PASS</password>
			</server>
		</servers>
	</settings>
	$ :wq
$ cd /tmp
$ chmod 777 set.xml