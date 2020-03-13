Bootstrap: docker
From: container-registry.phenomenal-h2020.eu/phnmnl/rbase:dev_v3.4.1-2xenial0_cv0.2.14
%files
passatutto/Passatutto /usr/local/bin/Passatutto
scripts/*.r /usr/local/bin/
runTest1.sh /usr/local/bin/runTest1.sh
%labels
software.version=201604
version=0.1
software=Passatutto
MAINTAINER PhenoMeNal-H2020 Project ( phenomenal-h2020-users@googlegroups.com )
Description="Metabolite pep score generator"
%post






R -e 'install.packages(c("R.utils","tools"),repos = "http://cran.us.r-project.org")'
# Update & upgrade sources
apt-get -y update

# Install development files needed
apt-get -y install wget default-jre-headless unzip

# Clean up
apt-get -y clean && apt-get -y autoremove && rm -rf /var/lib/{cache,log}/ /tmp/* /var/tmp/*



chmod +x /usr/local/bin/*.r

# Add testing to container
chmod +x /usr/local/bin/runTest1.sh

# Define Entry point script
#ENTRYPOINT ["java", "-cp", "/usr/local/bin/passatutto.jar"]
%runscript
exec /bin/bash "$@"
%startscript
exec /bin/bash "$@"
