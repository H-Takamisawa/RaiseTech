# 第6回課題

## 概要

1. CloudTrailのログを確認する
2. CloudWatchアラームを設定する
3. AWS利用料の見積を作成する
4. 現在の利用料を確認する
5. 感想

### 1 CloudTrailのログを確認する
- イベント名：StartInstances
![log-startinstances](images/lecture06/01_1_log_cloudTrail.jpg)

- イベントレコード
    ```
    {
        "eventVersion": "1.09",
        "userIdentity": {
            "type": "IAMUser",
            "principalId": "AIDA2JMYS7Y3L3YCJX372",
            "arn": "arn:aws:iam::707379002934:user/takamisawa_aws.24.03",
            "accountId": "707379002934",
            "accessKeyId": "ASIA2JMYS7Y3BTIFAKCI",
            "userName": "takamisawa_aws.24.03",
            "sessionContext": {
                "attributes": {
                    "creationDate": "2024-05-01T04:02:55Z",
                    "mfaAuthenticated": "true"
                }
            }
        },
        "eventTime": "2024-05-01T05:22:40Z",
        "eventSource": "ec2.amazonaws.com",
        "eventName": "StartInstances",
        "awsRegion": "ap-northeast-1",
        "sourceIPAddress": "126.241.105.156",
        "userAgent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/124.0.0.0 Safari/537.36",
        "requestParameters": {
                "instancesSet": {
                "items": [
                    {
                        "instanceId": "i-007dc27eb17f096f5"
                    }
                ]
            }
        },
        "responseElements": {
            "requestId": "bd9fc201-5011-4190-94aa-c35b0bb814da",
            "instancesSet": {
                "items": [
                    {
                        "instanceId": "i-007dc27eb17f096f5",
                        "currentState": {
                            "code": 0,
                            "name": "pending"
                        },
                        "previousState": {
                            "code": 80,
                            "name": "stopped"
                        }
                    }
                ]
            }
        },
        "requestID": "bd9fc201-5011-4190-94aa-c35b0bb814da",
        "eventID": "64041642-4f09-40e0-aafe-85e0af329e47",
        "readOnly": false,
        "eventType": "AwsApiCall",
        "managementEvent": true,
        "recipientAccountId": "707379002934",
        "eventCategory": "Management",
        "tlsDetails": {
            "tlsVersion": "TLSv1.3",
            "cipherSuite": "TLS_AES_128_GCM_SHA256",
            "clientProvidedHostHeader": "ec2.ap-northeast-1.amazonaws.com"
        },
        "sessionCredentialFromConsole": "true"
    }
    ```
    
- 記録内容
    - eventtime：リクエストが完了した日付と日時のこと。
    - eventSource：リクエストが行われたサービス。(今回の場合、EC2のこと)
    - responseElements：変更を行うアクションのレスポンスの要素(アクションの作成、更新、削除)が記述されている。

### 2. CloudWatchアラームを設定する
- アラーム状態
    ![state-alarm](images/lecture06/02_1_state_alarm.png)

- メール通知
    ![alarm-mail](images/lecture06/02_2_state_alarm_gmail.png)

- アラーム状態からOKに復旧
    ![state-ok](images/lecture06/02_3_state_ok.png)

- メール通知
    ![ok-mail](images/lecture06/02_4_state_ok_gmail.png)

### 3. AWS利用料の見積を作成する
- 使用ツール：AWS Pricing Calculator
- [共有URL](https://calculator.aws/#/estimate?id=aec0dea15ddbcb519cc59d8fd59491a00d80c8e2)

### 4. 現在の利用料を確認する
- 2024年4月の利用料
![利用料](images/lecture06/04_1_billing.png)

- EC2のEBSで無料利用枠の30GBを越えていたため料金が発生していた。
- Cloud9を作成してRailsアプリのデプロイ時に16GBに変更していて、第5回課題でもEC2インスタンスのEBSを20GBに変更していたので、差分の6GBが課金対象となったと考えられる。

### 5. 感想
- アラーム設定をすることで異常が発生した時や復旧したことがメールで分かるようになり、システム監視と通知を簡単なものですが実感できたのがよかった。
- AWS利用料の見積もりをすることで無料利用枠がない場合、月1万円以上はかかるのだろうということが分かった。