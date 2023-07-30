sudo apt update
sudo apt install openjdk-8-jdk -y

wget https://artifacts.opensearch.org/logstash/logstash-oss-with-opensearch-output-plugin-7.16.3-macos-x64.tar.gz

tar -zxvf logstash-oss-with-opensearch-output-plugin-7.16.3-macos-x64.tar.gz
cd logstash-7.16.3/
./bin/logstash-plugin install --preserve logstash-input-opensearch

nano  logstash-input-opensearch.conf 
./bin/logstash -f logstash-input-opensearch.conf
./bin/logstash -f logstash-input-opensearch.conf --config.reload.automatic 
