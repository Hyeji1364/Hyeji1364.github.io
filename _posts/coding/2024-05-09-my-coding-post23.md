---
layout: post
title: PHP
date: 2024-05-09 22:00 +0900
description: PHP 연동하기
image: ../assets/img/php.gif
category: PHP
tags: PHP
published: true
sitemap: true
---

## PHP

### PHP 연동하기

<hr>

<hr>

### 🎈 trigger

PHP 기본 사용법
PHP는 주로 웹 서버에서 동적인 웹 페이지를 생성하기 위해 사용되는 서버 사이드 스크립트 언어입니다.

PHP 설치: PHP는 php.net에서 다운로드 받을 수 있습니다.<br>
대부분의 웹 서버에는 PHP가 이미 설치되어 있습니다.<br>
PHP 스크립트 작성: PHP 코드는 일반적으로 .php 확장자를 가진 파일에 작성합니다.<br>
PHP 코드는 <?php로 시작하고 ?>로 끝납니다.<br>
<br>
서버에 파일 업로드: 작성된 PHP 파일을 웹 서버의 적절한 디렉토리에 업로드합니다.<br>
웹 브라우저에서 실행: 웹 브라우저를 사용하여 PHP 파일이 위치한 URL을 열면, 서버는 PHP 스크립트를 처리하고 결과를 웹 브라우저로 보냅니다.<br>
<br>
데이터베이스와의 연동<br>
PHP는 데이터베이스와의 연동을 위해 여러 가지 확장 기능을 지원합니다.<br>
가장 흔히 사용되는 데이터베이스 관리 시스템은 MySQL입니다.<br>

1) 데이터베이스 연결:

````php
php
Copy code
<?php
$servername = "localhost";
$username = "username";
$password = "password";
$dbname = "database";

// Create connection
$conn = new mysqli($servername, $username, $password, $dbname);

// Check connection
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}
echo "Connected successfully";
?>
````
<br>

2) 데이터 조회:
````php
<?php
$sql = "SELECT id, firstname, lastname FROM MyGuests";
$result = $conn->query($sql);

if ($result->num_rows > 0) {
    while($row = $result->fetch_assoc()) {
        echo "id: " . $row["id"]. " - Name: " . $row["firstname"]. " " . $row["lastname"]. "<br>";
    }
} else {
    echo "0 results";
}
$conn->close();
?>
````

외부 API와의 연동<br>
PHP는 cURL 라이브러리나 file_get_contents() 함수를 사용하여 외부 API와 통신할 수 있습니다.

1) cURL을 사용한 API 요청:<br>

````php
<?php
$curl = curl_init();

curl_setopt($curl, CURLOPT_URL, "http://api.example.com/data");
curl_setopt($curl, CURLOPT_RETURNTRANSFER, 1);

$response = curl_exec($curl);
curl_close($curl);

echo $response;
?>
````

2) file_get_contents를 사용한 간단한 GET 요청:<br>
````php
<?php
$response = file_get_contents('http://api.example.com/data');
echo $response;
?>
````
이러한 기본 사항을 통해 PHP를 시작하고 다양한 서비스와 연동하는 방법을 알 수 있습니다. 
