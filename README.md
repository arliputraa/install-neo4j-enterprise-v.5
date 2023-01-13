# Install Neo4j Enterprise Edition v.5 in Ubuntu and Conf

### Install Java 17
    sudo apt install openjdk-17-jre-headless -y

### Download Neo4j Enterprise (For now Version 5.0.3)
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

    wget https://github.com/neo4j-contrib/neo4j-apoc-procedures/releases/download/5.3.0/apoc-5.3.0-extended.jar

For Bloom

    wget https://neo4j.com/download-thanks-bloom/?version=2.6.0 -O neo4j-bloom-2.6.0.zip 
    
### create file licenses bloom & gds

in file path /home/ddi/neo4j-enterprise-5.3.0/licenses/bloom.txt & gds.txt

bloom.txt

eyJhbGciOiJQUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Im1lc2EuZHlhc3RhbWFAcGVydXJpLmNvLmlkIiwiZXhwIjoxNjczOTY3NjAwLCJmZWF0dXJlVmVyc2lvbiI6IioiLCJvcmciOiJQVC4gUGVnYWRpYWFuIChQZXJzZXJvKSIsInB1YiI6Im5lbzRqLmNvbSIsInF1YW50aXR5IjoiMSIsInJlZyI6Ik1lc2EgRHlhc3RhbWEiLCJzY29wZSI6IlRyaWFsIiwic3ViIjoibmVvNGotYmxvb20tc2VydmVyIiwidmVyIjoiKiIsImlzcyI6Im5lbzRqLmNvbSIsIm5iZiI6MTY3MTQyMTY2NywiaWF0IjoxNjcxNDIxNjY3LCJqdGkiOiJwSl9iLTI2UlcifQ.hR-FrXA0YfqBw7x2tblDMD3LY6gNnMIKmXC5abYEi9WKZG0e8kePtx7LVLKlqzAZ_JrldJH39K-XU-0vxy6rWnwEOjbLpxuhTK5mw4teyi08vy3HC8hcyVy70TXpzVbPBBSENWK62rOsYBVQWGPP9_k590LDsjSqrr9OROEM2G5-ZCn1yB6m7vRomo_h1yNmdl8Ytd9dw5ifJrudIcJpUnoWVehBV8fpa5_STvPkkdMjBDE4aAQ7gNnQCVp-q7xvoL-SUBj0CqGLAQfdDoKiXWs3XJLddkPMHjTAc-R04AMS0WqYwJoEIkpRGgcLWOMfYy6F1mnI8uWULK5Ga8Gx8w

gds.txt

eyJhbGciOiJQUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Im1lc2EuZHlhc3RhbWFAcGVydXJpLmNvLmlkIiwiZXhwIjoxNjczOTY3NjAwLCJmZWF0dXJlVmVyc2lvbiI6IioiLCJvcmciOiJQVC4gUGVnYWRpYWFuIChQZXJzZXJvKSIsInB1YiI6Im5lbzRqLmNvbSIsInF1YW50aXR5IjoiMSIsInJlZyI6Ik1lc2EgRHlhc3RhbWEiLCJzY29wZSI6IlRyaWFsIiwic3ViIjoibmVvNGotZ2RzIiwidmVyIjoiKiIsImlzcyI6Im5lbzRqLmNvbSIsIm5iZiI6MTY3MTQyMTY5OCwiaWF0IjoxNjcxNDIxNjk4LCJqdGkiOiJZa2hHYWwxVy0ifQ.vFEw8ImpWicdcPtOzJSoK-sqXKjK3dmGl9HL13qkq1Kch18jnS9sID9OV1XDXTVCbqelT1ht51KmCCp3P0EdGYtU2Qoobjm4oJqGjH7KYlqfHQaxTaQJRv_B6A2ooFlzOX9VuHExSPa5puDzcoGBtGz8zWedahEn8mD2U9FbdPd3DM51SfE8RVLJ4Yvc1gOMlmol4HHUdYb8PK6zPJXD_2KQiNT-apXynjIreaQ5nN0_wG1Ze-mczZT6WUP33me5o-GrdG9kj3ZmSXGMv76JsmZvV1DylQMu7uHrTnF6KsFNmiAwf_jKkV1gY2TNbmcHFLhftTeCasQavShEg3PASQ

### Start Neo4j in file path /home/neo4j-enterprise-5.3.0/bin

    ./neo4j start 
    

