# redis_cluster_setup
Hướng dẫn cài đặt Redis Cluster

Cài đặt 3 node Master - Slave 

Bước 1: git clone https://github.com/phamthanhnhan14/redis_cluster_setup

Bước 2: Chạy lần lượt các redis-server từ 8000-8005

cd ~/redis_cluster_setup/redis

bin/redis-server conf/8000.conf

tương tự cho các port còn lại

Bước 3: Chỉnh shebang của ruby để lấy đúng môi trường

vi redis/bin/redis-trib.rb

#!/~/redis_cluster_setup/ruby/bin/ruby

Bước 4: Khởi tạo cluster

~/redis/bin/redis-trib.rb create --replicas 1 127.0.0.1:8000 127.0.0.1:8001 127.0.0.1:8002 127.0.0.1:8003 127.0.0.1:8004 127.0.0.1:8005

Bước 5: Kiểm tra lại tình trạng 

~/redis/bin/redis-trib.rb info 127.0.0.1:8000

Hoàn thành

