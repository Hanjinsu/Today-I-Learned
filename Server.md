#EC2-Server

## 서버 setting 순서


1. AWS Instance에 들어가 Instance를 생성하고 PEM키로 접속한다.
> https://docs.aws.amazon.com/ko_kr/AWSEC2/latest/UserGuide/ec2-key-pairs.html


2. PHP, Apache, Mysql 설치 및 config 파일 수정
https://docs.aws.amazon.com/ko_kr/AWSEC2/latest/UserGuide/install-LAMP.html

IncludeOptional
Conf - Virtual host - 80 port로 DirectoryRoot에 저장
	 - Overide html All 로 변경

PHP ini  - display error ON
	       - short_open_tag ON
         
         
3. PHP 연동 및 Directory Root 수정 
>http://lhjin.tistory.com/entry/%EB%A6%AC%EB%88%85%EC%8A%A4-%EC%9B%B9%EC%84%9C%EB%B2%84httpdapache-php-%EC%97%B0%EB%8F%99%EB%B0%A9%EB%B2%95

4. Github ssh 
> https://help.github.com/articles/connecting-to-github-with-ssh/
