################## BASE IMAGE ######################
FROM biocontainers/biocontainers:latest

################## METADATA ######################
LABEL base_image="biocontainers:latest"
LABEL version="1"
LABEL software="PeptideShaker"
LABEL software.version="1.16.16"
LABEL about.summary="interpretation of proteomics identification results"
LABEL about.home="http://compomics.github.io/projects/peptide-shaker.html"
LABEL about.documentation="http://compomics.github.io/projects/peptide-shaker.html"
LABEL about.license_file="https://github.com/compomics/peptide-shaker/blob/master/README.txt"
LABEL about.license="SPDX:Apache-2.0"
LABEL about.tags="Proteomics"
LABEL extra.identifiers.biotools="peptideshaker"

################## MAINTAINER ######################
MAINTAINER Felipe da Veiga Leprevost <felipe@leprevost.com.br>

RUN ZIP=PeptideShaker-1.16.16.zip && \
    wget http://genesis.ugent.be/maven2/eu/isas/peptideshaker/PeptideShaker/1.16.16/$ZIP -O /tmp/$ZIP && \
    unzip /tmp/$ZIP -d /home/biodocker/bin/ && \
    rm /tmp/$ZIP && \
    bash -c 'echo -e "#!/bin/bash\njava -jar /home/biodocker/bin/PeptideShaker-1.16.16/PeptideShaker-1.16.16.jar $@"' > /home/biodocker/bin/PeptideShaker && \
    chmod +x /home/biodocker/bin/PeptideShaker

ENV PATH /home/biodocker/bin/PeptideShaker:$PATH

WORKDIR /data/
