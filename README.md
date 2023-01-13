# Install Neo4j Enterprise Edition v.5 in Ubuntu and Conf

### Install Java 17
    sudo apt install openjdk-17-jre-headless -y

### Download Neo4j Enterprise (For now Version 5.3.0)
    wget https://neo4j.com/artifact.php?name=neo4j-enterprise-5.3.0-unix.tar.gz -O neo4j-enterprise-5.3.0-unix.tar.gz

### Un-tar Neo4j Packages
     tar -xvf neo4j-enterprise-5.3.0-unix.tar.gz

### Edit and insert teks below in conf file path /home/neo4j-enterprise-5.3.0/conf/neo4j.conf

    dbms.default_listen_address=0.0.0.0
    dbms.default_advertised_address=(your ip)
    dbms.bloom.license_file=/home/ddi/neo4j-enterprise-5.3.0/licenses/bloom.txt
    gds.enterprise.license_file=/home/ddi/neo4j-enterprise-5.3.0/licenses/gds.txt
    dbms.security.procedures.unrestricted=gds.*,bloom.*
    dbms.security.procedures.allowlist=gds.*,bloom.*
    server.unmanaged_extension_classes=com.neo4j.bloom.server=/bloom
    dbms.security.http_auth_allowlist=/,/browser.*,/bloom.*

    server.memory.heap.initial_size=29g
    server.memory.heap.max_size=29g
    server.memory.pagecache.size=67800m

### Download Plugins for Graph Data Science, APOC, and Bloom.

For Graph Data Science

    wget https://github.com/neo4j/graph-data-science/releases/download/2.2.6/neo4j-graph-data-science-2.2.6.jar
    
For APOC

    wget https://github.com/neo4j-contrib/neo4j-apoc-procedures/releases/download/5.3.1/apoc-5.3.1-extended.jar

For Bloom

    wget https://neo4j.com/download-thanks-bloom/?version=2.6.0 -O neo4j-bloom-2.6.0.jar

### Start Neo4j in file path /home/neo4j-enterprise-5.3.0/bin

    ./neo4j start 
    

