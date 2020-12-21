# [CC4081] Security Operations - ELK stack

## Details
* Deployment
    ```shell
    docker-compose up -d
    ```
* Use  
  * To access both ElasticSearch and Kibana add to your */etc/hosts* the following:
    ```shell
    127.0.0.1	elastic.secop.edu
    127.0.0.1	kibana.secop.edu
    ```
  * Test it:
      * cURL - `curl -v elastic.secop.edu:80`
      * Browser - <http://kibana.secop.edu>
