# DockerVueChatBack (node.js)

mysql, node.js 
(socket.io)를 이용하여 front(vue.js)로 Chatting 프로그램 구현

[DockerVueChat notion 바로가기](https://www.notion.so/DockerVueChat-ba27ae64d28e47d48b2dacaa89e81fdf?pvs=4)

## npm 준비

```
npm i 
```

### server.js랑 같은 위치에 config.json 파일 생성

example

```
{
  "database": {
    "host" :"127.0.0.1",
        "port":"3306",
        "user":"",
        "password":"",
        "database":""
  },
  "server": {
    "host": "",
    "port": 8080
  }
}
```

## 실행
```
node run server.js
```

[DockerVueChatFront 바로가기](https://github.com/seunghwan94/DockerVueChatFront)

### mysql setting

```
CREATE TABLE `tb_chat` (
	`id` INT(11) NOT NULL AUTO_INCREMENT,
	`user_id` INT(11) NULL DEFAULT NULL,
	`other_user_id` INT(11) NULL DEFAULT NULL,
	`room` VARCHAR(13) NULL DEFAULT NULL COLLATE 'utf8mb4_general_ci',
	`img` VARCHAR(50) NULL DEFAULT NULL COLLATE 'utf8mb4_general_ci',
	`insertdate` TIMESTAMP NULL DEFAULT NULL,
	PRIMARY KEY (`id`) USING BTREE
)
COLLATE='utf8mb4_general_ci'
ENGINE=InnoDB;
CREATE TABLE `tb_log_chat` (
	`id` INT(11) NOT NULL AUTO_INCREMENT,
	`user_name` VARCHAR(50) NOT NULL COLLATE 'utf8mb4_general_ci',
	`user_type` ENUM('you','me','bot') NOT NULL DEFAULT 'bot' COLLATE 'utf8mb4_general_ci',
	`other_name` VARCHAR(50) NULL DEFAULT NULL COLLATE 'utf8mb4_general_ci',
	`room` VARCHAR(13) NULL DEFAULT NULL COLLATE 'utf8mb4_general_ci',
	`msg` VARCHAR(50) NULL DEFAULT NULL COLLATE 'utf8mb4_general_ci',
	`img` VARCHAR(50) NULL DEFAULT NULL COLLATE 'utf8mb4_general_ci',
	`insertdate` TIMESTAMP NULL DEFAULT NULL,
	PRIMARY KEY (`id`) USING BTREE
)
COLLATE='utf8mb4_general_ci'
ENGINE=InnoDB;
CREATE TABLE `tb_user` (
	`id` INT(4) NOT NULL AUTO_INCREMENT,
	`user_id` VARCHAR(50) NOT NULL COLLATE 'utf8mb4_general_ci',
	`user_pw` VARCHAR(50) NOT NULL COLLATE 'utf8mb4_general_ci',
	`name` VARCHAR(50) NOT NULL COLLATE 'utf8mb4_general_ci',
	`birth` VARCHAR(50) NOT NULL COLLATE 'utf8mb4_general_ci',
	`img` VARCHAR(50) NULL DEFAULT 'user.png' COLLATE 'utf8mb4_general_ci',
	`comments` VARCHAR(50) NULL DEFAULT NULL COLLATE 'utf8mb4_general_ci',
	`insert_date` TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
	`update_date` TIMESTAMP NOT NULL DEFAULT '0000-00-00 00:00:00',
	PRIMARY KEY (`id`) USING BTREE
)
COMMENT='login'
COLLATE='utf8mb4_general_ci'
ENGINE=InnoDB;
```





# DockerVueChatFront (vue.js)
챗봇 앞단으로 socket.io 를 이용하여 화면 구성

Back단이 있어야 사용가능

[DockerVueChat notion 바로가기](https://www.notion.so/DockerVueChat-ba27ae64d28e47d48b2dacaa89e81fdf?pvs=4)

## npm setting
```
npm i
```

### .gitignore랑 같은 위치에 config.json 파일 생성

example

```
{
  "server": {
    "host": "",
    "port": 3000
  }
}

```

### 실행
```
npm run serve
```

### Back 단 바로가기
[DockerVueChatBack 바로가기](https://github.com/seunghwan94/DockerVueChatBack).

