# tôi deploy 2 app, 1 app game, 2 là nginx rồi mount logs của 2 app này ra folder /var/log/storage/xxx/ của node
# dùng filebeat cào logs đó, cào luon trên node
# lưu ý trace quyền cho folder node
# filebeat ko cần mount volume logs từ node vào folder của filebeat 