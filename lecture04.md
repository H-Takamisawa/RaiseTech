# 第4回課題

## 概要

1. VPCの構築
2. EC2の構築
3. RDSの構築
4. EC2からRDSへの接続確認
5. 感想

## 内容

### 1. VPCの構築

- VPCの構成

![VPCの構成](images/lecture04/01_1_vpc.png)

- サブネット一覧

- subnet_public1

![subnet_public1](images/lecture04/01_2_vpc_subnet_public1.png)

- subnet_public2

![subnet_public2](images/lecture04/01_3_vpc_subnet_public2.png)

- subnet_private1

![subnet_private1](images/lecture04/01_4_vpc_subnet_private1.png)

- subnet_private2

![subnet_private2](images/lecture04/01_5_vpc_subnet_private2.png)

### 2. EC2の構築

- EC2の構成

![EC2の構成](images/lecture04/02_1_ec2.png)

- セキュリティグループの詳細

![セキュリティグループ](images/lecture04/02_2_ec2_securitygroup.png)

- Teratermからの接続確認

![接続確認](images/lecture04/02_3_ec2_connect.png)

### 3. RDSの構築

- RDSの構成

![RDSの構成](images/lecture04/03_1_rds_db.png)

- セキュリティグループ(インバウンドルール)の詳細

![RDSのインバウンドルール](images/lecture04/03_2_rds_inbound_security.png)

- セキュリティグループ(アウトバンドルール)の詳細

![RDSのアウトバンドルール](images/lecture04/03_3_rds_outbound_security.png)

### 4. EC2からRDSへの接続確認

- EC2からRDSへの接続確認

![接続確認](images/lecture04/04_1_connect_mysql.png)

###5. 感想

- 独学で少しVPCやEC2の構築はやっていたので、内容の理解に苦しむことはありませんでした。
  復習の要領で学習を進めていました。
  
- 参考教材としてUdemyの「AWS：ゼロから実践するAmazon Web Services。手を動かしながらインフラの基礎を習得」を視聴しました。